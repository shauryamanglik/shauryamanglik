# **Application Programming Interface (API)**

---

## **Overview**

This document defines how Shaurya's subsystem communicates using UART-based messaging in the updated Team 309A project. It uses a simplified 2-person communication model between Shaurya (Sensor) and Aadish (Motor Driver).

## **User ID Assignments**

| User | User ID |
| :---- | :---- |
| Shaurya | 0xFC |
| Aadish | 0xFD |

## **Message Structure**

| Byte \# | Field Name | Data Type | Description |
| :---- | :---- | :---- | :---- |
| 1–2 | Prefix | uint16\_t | Message start identifier |
| 3 | Sender ID | uint8\_t | Identifies sender |
| 4 | Receiver ID | uint8\_t | Identifies recipient |
| 5–6 | Data | uint16\_t | Message-specific data |
| 7–8 | Suffix | uint16\_t | Message end identifier |

---

## **Message Types**

### **Type 1 – Motor Direction Command (Sent from Shaurya to Aadish)**

| Condition | Message ID | Meaning |
| :---- | :---- | :---- |
| Temp ≤ 25°C | 0x01 | Motor Forward |
| 25°C \< Temp ≤ 30°C | 0x02 | Motor Reverse |
| Temp \> 30°C | 0x03 | Motor Off |

### **Type 2 – Acknowledgment (Sent from Aadish to Shaurya)**

| Message ID | Meaning |
| :---- | :---- |
| 0x01 | Motor Forward Confirmation – Blink RB0 |
| 0x02 | Motor Reverse Confirmation – Blink RB4 |
| 0x03 | Motor Off Confirmation – Blink RB0 & RB4 |

## **Serial Message Format**

| Field | Example (Motor Forward) |
| :---- | :---- |
| Prefix | FS |
| Sender ID | S |
| Receiver ID | A |
| Data | 01 (Forward) |
| Suffix | FS |

---

## **MPLAB X Code (XC8 UART Handler)**

    \#include "mcc\_generated\_files/system/system.h"
    
    \#define AHT21\_ADDR 0x38
    
    void send\_uart\_message(const char\* msg) {
    
        for (uint8\_t i \= 0; i \< 8; i++) {
    
            while (\!EUSART1\_IsTxReady());
    
            EUSART1\_Write(msg\[i\]);
    
        }
    
    }
    
    void blink\_led(uint8\_t cmd) {
    
        if (cmd \== '1') LATBbits.LATB0 \= 1;
    
        if (cmd \== '2') LATBbits.LATB4 \= 1;
    
        if (cmd \== '3') { LATBbits.LATB0 \= 1; LATBbits.LATB4 \= 1; }
    
        \_\_delay\_ms(200);
    
        LATBbits.LATB0 \= 0;
    
        LATBbits.LATB4 \= 0;
    
    }
    
    int main(void)
    
    {
    
        SYSTEM\_Initialize();
    
        INTERRUPT\_GlobalInterruptEnable(); 
    
        INTERRUPT\_PeripheralInterruptEnable(); 
    
        ANSELBbits.ANSELB0 \= 0;  // Make sure RB0 is digital
    
        ANSELBbits.ANSELB4 \= 0;  // Make sure RB4 is digital
    
        TRISBbits.TRISB0 \= 0;    // Set RB0 as output
    
        TRISBbits.TRISB4 \= 0;    // Set RB4 as output
    
        LATBbits.LATB0 \= 0;      // Ensure RB0 starts LOW
    
        LATBbits.LATB4 \= 0;      // Ensure RB4 starts LOW
    
        uint8\_t cmd\[3\] \= {0xAC, 0x33, 0x00};
    
        uint8\_t data\[6\];
    
        char rx\_buf\[8\] \= {0};
    
        while (1)
    
        {
    
            // Send measurement trigger
    
            I2C1\_Write(AHT21\_ADDR, cmd, 3);
    
            \_\_delay\_ms(80);
    
            // Read data
    
            if (I2C1\_Read(AHT21\_ADDR, data, 6\) && \!(data\[0\] & 0x80))
    
            {
    
                uint32\_t raw\_temp \= ((uint32\_t)(data\[3\] & 0x0F) \<\< 16\) | ((uint32\_t)data\[4\] \<\< 8\) | data\[5\];
    
                float temperature \= ((float)raw\_temp / 1048576.0f) \* 200.0f \- 50.0f;
    
                printf("Temperature: %.2f C\\r\\n", temperature);  // ? Added line
    
                char command \= '3'; // Default to off
    
                if (temperature \<= 25\) command \= '1'; // Forward
    
                else if (temperature \<= 30\) command \= '2'; // Reverse
    
                char msg\[8\] \= { 'F', 'S', 'S', 'A', '0', command, 'F', 'S' };
    
                send\_uart\_message(msg);
    
            }
    
            // Check for UART confirmation from A
    
            if (EUSART1\_IsRxReady()) {
    
                char byte \= EUSART1\_Read();
    
                for (uint8\_t i \= 0; i \< 7; i++) rx\_buf\[i\] \= rx\_buf\[i \+ 1\];
    
                rx\_buf\[7\] \= byte;
    
                if (rx\_buf\[0\] \== 'F' && rx\_buf\[1\] \== 'S' &&
    
                    rx\_buf\[2\] \== 'A' && rx\_buf\[3\] \== 'S' &&
    
                    rx\_buf\[4\] \== '0' && rx\_buf\[6\] \== 'F' && rx\_buf\[7\] \== 'S') {
    
                    blink\_led(rx\_buf\[5\]);
    
                }
    
            }
    
            \_\_delay\_ms(1000);
    
        }
    
    }

---

## **Summary**

Shaurya's subsystem uses the AHT21 sensor to read temperature. Based on the reading:  
\- If ≤ 25°C, it sends command 01 (motor forward)  
\- If between 25°C and 30°C, it sends command 02 (motor reverse)  
\- If \> 30°C, it sends command 03 (motor off)  
The command is sent to Aadish's subsystem using the message format FSSA0xFS.  
Upon executing the command, Aadish responds using FSAS0xFS. When Shaurya receives this response:  
\- '01' makes Shaurya blink RB0 LED  
\- '02' blinks RB4 LED  
\- '03' blinks both RB0 and RB4 for 200 ms
