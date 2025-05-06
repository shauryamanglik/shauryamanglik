---
title: Block Diagram
---
## Temperature Sensor Subsystem

![BLOCKDIAGRAM_314 (1)](https://github.com/user-attachments/assets/194f34f3-c77b-4563-855b-09d9bd219ef9)




[Download PDF](https://github.com/user-attachments/files/20053269/BLOCKDIAGRAM_314.1.pdf)




### **Block Diagram – Decision-Making Process & Alignment with Product Requirements (Individual Subsystem)**

The design of this block diagram began with identifying the key responsibilities of my subsystem within the broader Team 309A project: to measure temperature, determine the appropriate motor behavior (forward, reverse, or off), and communicate that decision to the motor driver subsystem via UART. Additionally, my system needed to respond to confirmation messages from the actuator and reflect motor status using on-board LEDs.

To accomplish this, I selected the **PIC18F27Q10 microcontroller**, which supports both **I²C** and **UART** protocols. It interfaces with the **AHT21 temperature sensor** over I²C to read real-time ambient temperature data. I²C was chosen due to its simple two-wire communication, low pin usage, and native compatibility with both components. UART is used to send formatted motor control messages to the actuator subsystem and receive acknowledgments in return.

The **AP63203WU-7 voltage regulator** was used to provide a stable 3.3V power rail to both the sensor and MCU, ensuring compatibility with low-power digital components.

GPIO pins (specifically RB0 and RB4) are used to control LEDs that blink to indicate motor direction (forward, reverse, off) based on acknowledgment messages received over UART. This visual feedback ensures that even without external debugging tools, the user can verify communication and action execution.

This modular, clearly segmented block diagram reflects not only the subsystem’s function but also how it aligns with our product requirement to:

* React to environmental input (temperature).

* Control another subsystem (motor) via logical thresholds.

* Confirm actions visually for debugging and usability.

By simplifying the architecture to use just one microcontroller, sensor, and UART interface, the system maintains low complexity while fulfilling its defined role effectively.
