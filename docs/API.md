---
title: API
---

# **Application Programming Interface (API)**

## **Overview**

This document defines how Shaurya's subsystem communicates using **UART-based messaging** in the updated **Team 309A project**. It uses a simplified 2-person communication model between Shaurya (Sensor) and Aadish (Motor Driver).

---

## **User ID Assignments**

| User     | User ID |
|----------|---------|
| Shaurya  | 0xFC    |
| Aadish   | 0xFD    |

---

## **Message Structure**

Each message consists of **8 bytes** in the following format:

| Byte # | Field Name     | Data Type | Description                   |
|--------|----------------|-----------|-------------------------------|
| 1–2    | Prefix         | uint16_t  | Message start identifier      |
| 3      | Sender ID      | uint8_t   | Identifies sender             |
| 4      | Receiver ID    | uint8_t   | Identifies recipient          |
| 5–6    | Data           | uint16_t  | Message-specific data         |
| 7–8    | Suffix         | uint16_t  | Message end identifier        |

---

## **Message Types**

### **Type 1 – Motor Direction Command (Sent from Shaurya to Aadish)**

| Condition            | Message ID | Meaning             |
|----------------------|------------|---------------------|
| Temp > 25°C          | 0x0040     | Motor Forward       |
| Temp ≤ 25°C          | 0x0041     | Motor Reverse       |

### **Type 2 – Acknowledgment (Sent from Aadish to Shaurya)**

| Message ID | Meaning          |
|------------|------------------|
| 0x00AF     | Command Received |

---

## **Serial Message Format**

| Byte # | Field         | Example (Forward) |
|--------|---------------|-------------------|
| 1–2    | Prefix        | 0x0001            |
| 3      | Sender ID     | 0xFC              |
| 4      | Receiver ID   | 0xFD              |
| 5–6    | Data          | 0x0040 or 0x0041  |
| 7–8    | Suffix        | 0x00EE            |

---

## **MPLAB X Code (XC8 UART Handler)**

```c
#include <xc.h>
#include <stdint.h>
#include <stdbool.h>

#define UART_BUFFER_SIZE 10
#define PREFIX_CMD       0x0001
#define PREFIX_ACK       0x0002
#define SUFFIX           0x00EE

#define CMD_FORWARD      0x0040
#define CMD_REVERSE      0x0041
#define ACK              0x00AF

volatile uint8_t uartBuffer[UART_BUFFER_SIZE];
volatile uint8_t bufferIndex = 0;

void UART_Init(void);
void UART_Send(uint8_t *message, uint8_t length);
void Process_Message(uint8_t *message, uint8_t length);
void UART_Receive_Handler(void);

void UART_Init(void) {
    SPBRG = 25; // 9600 baud @ 4MHz
    TXSTAbits.BRGH = 1;
    RCSTAbits.SPEN = 1;
    RCSTAbits.CREN = 1;
    TXSTAbits.TXEN = 1;
    PIE1bits.RCIE = 1;
    INTCONbits.PEIE = 1;
    INTCONbits.GIE = 1;
}

void UART_Send(uint8_t *message, uint8_t length) {
    for (uint8_t i = 0; i < length; i++) {
        TXREG = message[i];
        while (!TXSTAbits.TRMT);
    }
}

void Process_Message(uint8_t *message, uint8_t length) {
    uint16_t prefix = (message[0] << 8) | message[1];
    uint16_t suffix = (message[6] << 8) | message[7];
    
    if (prefix == PREFIX_ACK && suffix == SUFFIX) {
        // ACK received from Aadish
        LATBbits.LATB0 = 1; // Light up LED as acknowledgment
    }
}

void UART_Receive_Handler(void) {
    if (PIR1bits.RCIF) {
        uint8_t receivedByte = RCREG;

        if (bufferIndex == 0 && receivedByte != 0x00) {
            uartBuffer[bufferIndex++] = receivedByte;
        } else if (bufferIndex > 0) {
            uartBuffer[bufferIndex++] = receivedByte;
            if (bufferIndex >= 8) {
                Process_Message(uartBuffer, bufferIndex);
                bufferIndex = 0;
            }
        }
    }
}
```

---

## **Summary**

Shaurya reads temperature using the TC74A4-3.3VCTTR sensor. If temperature is above 25°C, a **forward** command is sent to Aadish. If 25°C or below, a **reverse** command is sent. Upon receiving an ACK from Aadish, Shaurya turns on an LED for confirmation.
