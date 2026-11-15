
# Adaptive-Vehicle-Dashboard-Simulator

## Project Overview

An embedded systems-based automotive dashboard simulation developed using two LPC2129 microcontroller communicating through the CAN  protocol.

The system monitors vehicle speed, fuel level, engine temperature, and indicator status. Node A collects sensor data and transmits it to Node B through CAN communication. Node B processes the received data and displays the vehicle information on a serial terminal using UART.

## Key Features

- Vehicle speed monitoring using a potentiometer.
- Fuel-level monitoring using an ultrasonic sensor (HC-SR04).
- Engine temperature monitoring using LM35.
- Left and right indicator status detection.
- Headlight status monitoring.
- ADC-based sensor data acquisition.
- External interrupt handling.
- CAN interrupt-based communication.
- UART-based real-time dashboard monitoring.
- Bitwise data packing and unpacking.

## Hardware Components

- 2 × LPC2129 ARM7 Microcontrollers
- LM35 Temperature Sensor
- HC-SR04 Ultrasonic Sensor
- Potentiometer
- Push Buttons / Switches
- CAN Transceivers
- LEDs

## Software and Tools

- Embedded C
- Keil µVision IDE
- Flash Magic
- ADC, GPIO, Timer, EINT
- CAN Protocol
- UART Communication

## System Architecture

**Node A – Transmitter**
- Reads temperature and speed through ADC.
- Measures fuel level using an ultrasonic sensor.
- Detects indicator and headlight switch inputs.
- Packs the collected information into an 8-byte CAN frame.
- Transmits data to Node B.

**Node B – Receiver**
- Receives CAN data through interrupts.
- Decodes sensor values and switch statuses.
- Controls indicator LEDs.
- Displays vehicle information through UART serial communication.

## Communication Configuration

- Microcontroller : LPC2129 ARM7 
- CAN Protocol    : CAN  
- CAN Baud Rate   : 125 kbps 
- CAN Identifier  : 0x123 
- CAN Data Length : 8 Bytes 
- UART Baud Rate  : 9600 

##  How to Run

1. Open Node A and Node B projects in Keil µVision.
2. Build both projects.
3. Generate HEX files.
4. Flash the respective HEX files using Flash Magic.
5. Connect both CAN transceivers (CAN_H and CAN_L).
6. Open the Node B UART serial terminal at 9600 baud.
7. Run both nodes and monitor the dashboard data.

##  Learning Outcomes

- LPC2129 ARM7 programming.
- Sensor interfacing using ADC and GPIO.
- Timer and external interrupt programming.
- CAN protocol configuration and communication.
- UART serial communication.
- Interrupt-driven embedded system development.
- Multi-node microcontroller communication.

##  Future Enhancements

- LCD/OLED dashboard integration.
- Low-fuel and high-temperature alerts.
- Buzzer-based warning system.
- Bluetooth/Wi-Fi monitoring.

##  Disclaimer
This project is developed for educational and simulation purposes. It is not intended for direct use in real vehicles or safety-critical automotive applications.
