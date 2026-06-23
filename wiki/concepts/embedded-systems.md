---
concept: embedded-systems
entity_type: concept
aliases: ["embedded-computing"]
sources: ["raw/embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T03:34:51Z
---

## Definition

Embedded systems are dedicated computing systems designed for specific control functions within a larger system. They are characterized by their integration into the machinery they control or monitor, with hardware and software tailored for specific applications, often with stringent requirements for performance, size, cost, and power consumption. IoT (Internet of Things) is a computing concept that extends internet connectivity beyond traditional devices such as computers and smartphones to a wide range of physical devices, vehicles, buildings, and other items, enabling them to collect and exchange data.

## How It Works

### Hardware Foundation

Embedded systems typically consist of a microcontroller unit (MCU) that integrates a CPU, memory, I/O interfaces, and peripheral devices on a single chip. This integration facilitates efficient and compact hardware designs suited for specific functions. Common communication protocols used in embedded systems include:
- **UART (Universal Asynchronous Receiver/Transmitter):** Simple, two-wire serial communication protocol.
- **I2C (Inter-Integrated Circuit):** Synchronous serial protocol using two wires, suitable for short-distance communication.
- **SPI (Serial Peripheral Interface):** Synchronous, four-wire protocol for higher-speed communication.

### Software Development

Embedded software development focuses on efficient code that can operate within the resource constraints of the hardware. Development tools primarily use languages like C/C++, known for their performance and hardware-level manipulation capabilities. More recently, languages like Rust have gained traction for their safety and security features in resource-constrained environments.

- **Bare-Metal Programming:** Direct execution without an operating system, often used for simpler control tasks.
- **RTOS (Real Time Operating System):** Provides task scheduling and management with deterministic performance, crucial for complex operations with strict timing requirements. Examples include FreeRTOS and RT-Thread.

### IoT Architecture

The IoT architecture consists of layers including sensing, networking, cloud platforms, and applications:
- **Communication Protocols:** Such as MQTT, CoAP, LoRaWAN, and NB-IoT, which enable efficient data transfer in various environments.
- **Edge Computing:** Processing data closer to where it is generated to reduce latency and bandwidth usage, supporting local decision-making and real-time responsiveness.

## Variants

Variants of embedded systems encompass a broad spectrum from simple control units to complex systems such as:
- **MCUs:** Wide range of microcontrollers like ARM Cortex-M series (e.g., STM32), Tensilica (ESP32), and Arduino.
- **RTOS Implementations:** Different versions like FreeRTOS, RT-Thread, tailored for specific performance and resource constraints.
- **IoT Protocols:** Specific implementations of communication standards to suit diverse network environments and devices.

## Trade-offs

Key trade-offs in embedded systems and IoT include:
- **Performance vs. Power Consumption:** Optimal system design must balance computational performance against power usage, crucial for battery-operated devices.
- **Complexity vs. Cost:** Simpler systems are often cheaper to produce but may not support advanced functionalities required for certain applications.
- **Security vs. Accessibility:** Enhanced security measures can restrict ease of access and maintenance, impacting the usability and deployment of embedded systems.

## See also
Real Time Operating Systems  
Internet of Things  
Microcontrollers  
Communication Protocols in Embedded Systems  
[[edge-computing]]