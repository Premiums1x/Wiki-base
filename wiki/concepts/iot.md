---
concept: iot
entity_type: concept
aliases: []
sources: ["raw\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T04:15:24Z
---

## Definition
The Internet of Things (IoT) refers to a network of physical devices, vehicles, home appliances, and other objects embedded with electronics, software, sensors, and connectivity which enables these objects to connect and exchange data. IoT builds on [[embedded-systems]] to provide smart management and interconnectivity. It extends the concept of embedded systems by adding network communication and data processing capabilities to enable remote monitoring and control.

## How it works
IoT leverages embedded systems to integrate physical devices into a digital network. Each device is equipped with microcontrollers ([[mcu]]) and sensors to collect data about the physical environment and its internal states. The collected data is processed by the devices locally or on cloud servers and can be transmitted over various communication protocols.

### Embedded Hardware and IoT
Embedded hardware forms the backbone of IoT. **MCUs** such as STM32 and ESP32 are crucial as they integrate multiple system components into a single chip and manage data collection, processing, and communication tasks. The choice of MCU depends largely on the device's power requirements, memory constraints, and computational needs.

### Communication Protocols
In the IoT context, MCUs utilize communication protocols like UART, I2C, and SPI for local connectivity within devices. For network communication, IoT devices leverage MQTT for lightweight message-based communication, and LoRaWAN for low-power long-range connectivity, both of which are optimized for constrained environments often found in IoT applications.

### Software and IoT
The software layer in IoT mostly relies on C and C++ due to their efficiency and low memory overhead necessary for embedded computing. Real-time operating systems (RTOS), such as FreeRTOS and RT-Thread, are frequently used to manage the embedded device's functionality and ensure consistent performance. These RTOS packages enable the efficient management of device tasks and operations in real-time, critical for responding to user interactions or environmental changes swiftly.

### IoT Architecture
The architecture of an IoT system typically consists of four layers: the Sense and Identify layer which captures data, the Network Layer which transmits this data, the Platform Layer which manages and processes the data, and the Application Layer which provides end-user functions. Edge computing plays a crucial role by processing data locally at the network edge to reduce latency and bandwidth requirements while enhancing security.

## Variants
There are multiple variants of IoT, each tailored for different applications or environments. For instance, LoRaWAN is specifically designed for wide-area networks with low bandwidth and long-range capabilities, ideal for rural or remote deployments. In contrast, NB-IoT focuses on creating narrowband IoT suitable for densely populated urban settings where many devices require consistent connection at a lower bandwidth.

## Trade-offs
IoT systems necessitate a careful balancing of several trade-offs:
- **Scalability vs. Complexity**: Expanding an IoT network from a few devices to thousands or millions can increase complexity in managing the network and ensuring secure communication. 
- **Battery Life vs. Communication Speed**: Low-power devices designed for long battery life often sacrifice communication speed, which is a critical consideration for IoT deployments in remote locations.
- **Data Security vs. Convenience**: Ensuring secure data transmission and storage in IoT environments can often come at the cost of convenience for both users and manufacturers. 
- **Edge Computing vs. Cloud Computing**: Edge computing reduces latency and bandwidth usage by processing data at the source but may lack the computational resources of cloud computing when more complex analysis is required.