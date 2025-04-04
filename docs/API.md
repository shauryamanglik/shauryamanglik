---
title: API
---
# **Application Programming Interface (API)**

## **Overview**

This document defines how my subsystem communicates using **UART-based daisy chain messaging** in **Team 309’s project**. It follows the agreed **message structure** used by all team members.

---

## **User ID Assignments**

Each team member has a unique **User ID** for message routing:

| User | User ID |
| ----- | ----- |
| Bruce | 0xFF |
| Baron | 0xFE |
| Aadish | 0xFD |
| **Shaurya** | **0xFC** |

---

## **Message Structure**

Each message consists of **8 bytes** in the following format:

| Byte \# | Field Name | Data Type | Description |
| ----- | ----- | ----- | ----- |
| 1-2 | **Prefix** | uint16\_t | Message start identifier |
| 3 | **Sender ID** | uint8\_t | Identifies who sent the message |
| 4 | **Receiver ID** | uint8\_t | Identifies who should receive the message |
| 5-6 | **Data** | uint16\_t | Message-specific data |
| 7-8 | **Suffix** | uint16\_t | Message end identifier |

---

## **Messages Shaurya Sends & Receives**

### **Message Type 2 – Update Motor Speed (Sent to Aadish)**

| Byte | Variable Name | Data Type | Min Value | Max Value | Example |
| ----- | ----- | ----- | ----- | ----- | ----- |
| 1-2 | prefix | uint16\_t | 0x0002 | 0x0002 | 0x0002 |
| 3 | sender\_id | uint8\_t | 0xFC | 0xFC | 0xFC |
| 4 | receiver\_id | uint8\_t | 0xFD | 0xFD | 0xFD |
| 5-6 | motor\_speed | uint16\_t | 0 | 255 | 120 |
| 7-8 | suffix | uint16\_t | 0x0021 | 0x0021 | 0x0021 |

**Function:** Tells Aadish to adjust the motor speed.

---

### **Message Type 3 – Rotational Velocity (Sent to Bruce)**

| Byte | Variable Name | Data Type | Min Value | Max Value | Example |
| ----- | ----- | ----- | ----- | ----- | ----- |
| 1-2 | prefix | uint16\_t | 0x0003 | 0x0003 | 0x0003 |
| 3 | sender\_id | uint8\_t | 0xFC | 0xFC | 0xFC |
| 4 | receiver\_id | uint8\_t | 0xFF | 0xFF | 0xFF |
| 5-6 | rotational\_velocity | uint16\_t | 0 | 65535 | 1500 |
| 7-8 | suffix | uint16\_t | 0x0022 | 0x0022 | 0x0022 |

**Function:** Sends rotational velocity data to Bruce for display.

---

## **Message Handling Code (For MPLAB X \- XC8)**

    #include <xc.h>
    #include <stdint.h
    #include <stdbool.h>
    
    #define UART_BUFFER_SIZE 10
    #define MSG_PREFIX_2 0x0002  // Motor Speed Update
    #define MSG_PREFIX_3 0x0003  // Rotational Velocity
    #define MSG_SUFFIX_2 0x0021
    #define MSG_SUFFIX_3 0x0022
    
    // UART Receive Buffer
    volatile uint8_t uartBuffer[UART_BUFFER_SIZE];
    volatile uint8_t bufferIndex = 0;
    
    // Function Prototypes
    void UART_Init(void);
    void UART_Send(uint8_t *message, uint8_t length);
    void Process_Message(uint8_t *message, uint8_t length);
    void UART_Receive_Handler(void);
    void UART_Init(void) {
    
        // Configure UART for 9600 baud, 8-N-1
        SPBRG = 25; // Adjust for different baud rates
        TXSTAbits.BRGH = 1;
        RCSTAbits.SPEN = 1; // Enable UART
        RCSTAbits.CREN = 1; // Enable Reception
        TXSTAbits.TXEN = 1; // Enable Transmission
        
        // Enable Interrupts
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
        if (prefix == MSG_PREFIX_2 && suffix == MSG_SUFFIX_2) {
        
            // Process Motor Speed Update
            uint8_t motor_speed = message[4];
            // Apply speed control logic here
        }
        
        else if (prefix == MSG_PREFIX_3 && suffix == MSG_SUFFIX_3) {
        
            // Process Rotational Velocity
            uint16_t velocity = (message[4] << 8) | message[5];
            // Store velocity data
        }
        
        // Send Acknowledgment
        uint8_t ack_msg[] = {message[0], message[1], 0x01};
        UART_Send(ack_msg, 3);
    }
    
    void UART_Receive_Handler(void) {
        if (PIR1bits.RCIF) {
            uint8_t receivedByte = RCREG;
            
            if (bufferIndex == 0 && receivedByte != 0x00) {
                uartBuffer[bufferIndex++] = receivedByte;
            } else if (bufferIndex > 0) {
                uartBuffer[bufferIndex++] = receivedByte;
                if (bufferIndex >= UART_BUFFER_SIZE) {
                    Process_Message(uartBuffer, bufferIndex);
                    bufferIndex = 0; // Reset buffer
                }
            }
        }
    }

