---
concept: embedded-systems-iots
entity_type: concept
aliases: []
sources: ["raw\\07-embedded-systems-and-iot\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-24T07:58:16Z
---

## Definition

Embedded Systems embedded-systems are application-oriented computer systems designed to perform specific tasks within constrained environments. These systems are characterized by their tailored nature, integrating software and hardware specifically for optimized performance, reliability, cost, size, and power consumption. The Internet of Things (IoT) internet-of-things extends and builds on embedded systems by providing a network framework that connects these systems to exchange data and enable intelligent management. IoT is composed of numerous embedded devices and sensors that interact over the internet, creating a distributed computing environment where objects can sense their surroundings, communicate with each other, and make automated decisions.

## How it works

Embedded systems consist of minimalistic hardware components tailored for specific tasks and may include microcontrollers (MCUs) microcontrollers, central processing units (CPUs), memory (RAM/Flash), and I/O interfaces. To manage communication between different devices and systems, embedded systems utilize various protocols such as UART, I2C, and SPI. These communications protocols allow for the exchange of data in different configurations, supporting ranging from simple serial connections to more complex multi-device networks.

For software development, developers often use C/C++ due to their support for low-level operations and resource control, necessary in environments with limited memory and power. Software development may involve writing code directly at the hardware level (Bare-Metal) or using Real-Time Operating Systems (RTOSes) for more structured task management. RTOSes are critical for handling complex logic by providing features like hard real-time scheduling, predictability, and responsiveness.

IoT integrates these embedded devices into a larger network where they can communicate and utilize various protocols and communication technologies like LoRaWAN/[[mqtt]], [[coap]], and NB-IoT to ensure connectivity even under challenging conditions. IoT applications are structured in layers: the Sensor and Identification Layer, Network Transmission Layer, Platform Support Layer, and Application Interface Layer. Edge Computing, a concept that leverages the computing capacity of devices closer to the data source, is crucial for processing large data volumes locally, reducing latency and bandwidth usage.

## Variants

Embedded systems exhibit a wide range of architectures depending on their application domain. They can be simple MCUs for controlling devices like a washing machine or more complex systems involving custom chips for specialized scientific equipment. IoT systems can comprise everything from an array of sensors in a smart home to industrial IoT (IIoT) solutions for agricultural or manufacturing processes. Variants of IoT communication protocols include MQTT, CoAP, LoRaWAN, and NB-IoT, which are selected based on the specific performance and connectivity needs of the devices and the network topology.

## Trade-offs

The primary trade-offs in embedded systems design lie in balancing between performance, resource utilization, reliability, and power consumption. Systems that require high precision and low latency often need to be designed with optimized RTOSes or bare-metal approaches, which can be complex to develop and maintain. On the other hand, systems focused on ease of use and rapid development might opt for more abstract software development environments that could consume more resources.

In IoT, trade-offs are primarily associated with choosing the right communication protocol, battery life, and network coverage, impacting the viability of deployment in specific environments. For instance, MQTT’s message publish/subscribe model is efficient for low-bandwidth situations but may not be ideal for point-to-point communication where direct message delivery is preferred. Similarly, LoRaWAN and NB-IoT are classified under low-power wide area network (LPWAN) technologies, offering extended battery life and broad coverage, at the cost of reduced bandwidth and latency. Therefore, choosing between these technologies involves weighing their trade-offs based on specific application needs and environmental constraints.

## See also
microcontrollers
internet-of-things
[[mqtt]]
[[coap]]
real-time-operating-systems
loalwan
[[nbiot]]