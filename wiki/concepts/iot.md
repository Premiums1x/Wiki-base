---
concept: iot
entity_type: concept
aliases: ["internet-of-things"]
sources: ["raw/embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T03:34:52Z
---

## Definition

Internet of Things (IoT) refers to the network of physical objects (devices, vehicles, home appliances, and other items) embedded with software, electronics, internet connectivity, and sensors that enable these objects to connect and exchange data. These devices can collect, send, and receive data without human intervention, contributing to a smarter, more connected world.

## How it Works

### Embedded Systems Foundation
The foundation of IoT lies in embedded systems, which are specialized computers designed for individual functional requirements. These systems include Microcontrollers (MCUs) like Arm Cortex-M, ESP32's Tensilica, and Arduino boards. These MCUs integrate key functionalities such as CPU, Memory, I/O ports, and peripherals on a single chip.

### Communication Protocols and Networks
IoT relies on communication protocols for data exchange. Commonly used protocols include UART, I2C, SPI, and GPIO for hardware communication. Communication in IoT devices also involves network protocols such as MQTT, CoAP, LoRaWAN, and NB-IoT, which are specifically designed for efficient and reliable data transmission, especially in resource-constrained environments.

### Software Development
Embedded software development languages like C/C++ and increasingly Rust, are used to develop and run applications. The application logic may be implemented either in a bare-metal environment (where code directly runs in an infinite loop interrupt-driven design) or with Real-Time Operating Systems (RTOS) such as FreeRTOS, RT-Thread, or VxWorks, which provide better task management and resource utilization.

### IoT Architecture
The architecture of an IoT system is generally layered:
1. **Sense and Identification Layer**: This involves sensors and devices that capture data from the environment.
2. **Network Transmission Layer**: Handles the transfer of data from the sensor nodes to the central processing units.
3. **Platform Support Layer**: Provides data storage, processing, analytics, and management functionalities.
4. **Application Interface Layer**: Delivers the information to the end user or systems through software applications and APIs.

### Edge Computing
Edge computing, a significant aspect of IoT, involves preliminary data processing at the network edge itself, thus reducing latency and bandwidth needs, and enhancing privacy and security.

## Variants

- **Wearable Devices**: Smartwatches, fitness trackers.
- **Home Automation**: Smart thermostats, light bulbs, security systems.
- **Industrial IoT (IIoT)**: Use of connected devices for industrial processes.
- **Smart Cities**: Devices used for transportation, infrastructure monitoring, and public safety.
- **Healthcare**: Devices used for patient monitoring and medical diagnoses.

## Trade-offs

### Key Trade-offs
- **Security and Privacy**: IoT systems often face significant security challenges due to their extensive reach and potential for data breaches.
- **Scalability**: Managing a large number of connected devices imposes challenges in scaling infrastructure to handle the volume of data and devices effectively.
- **Battery Life and Power Consumption**: Longevity and efficiency of power supply, particularly in battery-operated devices, vary widely.
- **Interoperability**: Ensuring different devices and platforms from multiple vendors can seamlessly communicate is a major hurdle.
- **Complex Deployment and Maintenance**: Wireless communication and embedded software require multiple layers of development and maintenance expertise.

## See also
[[embedded-systems]], Real-Time Operating Systems, [[cloud-computing]], [[edge-computing]], Sensors Technology