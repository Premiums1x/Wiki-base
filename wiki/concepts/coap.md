---
concept: coap
entity_type: technique
aliases: []
sources: ["raw/embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T03:34:56Z
---

## Definition
Constrained Application Protocol (CoAP) is a lightweight application layer protocol designed for use with constrained nodes and constrained (low-power, lossy) networks in the Internet of Things (IoT). CoAP is commonly used for machine-to-machine (M2M) applications such as smart energy and building automation.

## How it works
CoAP operates over UDP (User Datagram Protocol) to minimize the overhead and enable efficient communication in resource-constrained environments. It employs a RESTful architecture, similar to HTTP, with GET, PUT, POST, and DELETE methods, facilitating a request-response relationship. 

Key Components and Features:
- **Request-Response Model**: Clients send requests to servers to perform resource operations.
- **Observe Operation**: Listen for updates to resources.
- **Block-wise Transfer**: Handle large payloads by breaking them into smaller chunks.
- **Acknowledgment Fields**: Ensure reliable delivery over UDP, improving reliability in lossy networks.
- **Optionality**: Minimize size and complexity through optional extensions.

## Variants
CoAP protocol variations and implementations are supported by various embedded systems and IoT platforms:
- **CoRE (Constrained RESTful Environments)**: Extends CoAP for use in highly constrained environments.
- **Observe**: An extension to CoAP that supports real-time applications by continuously updating resources.
- **CoAP-over-TCP**: Implementation of CoAP over TCP instead of UDP to provide a more reliable connection over high-bandwidth networks.

## Trade-offs
**Advantages**:
- **Low Data Overhead**: Efficient for constrained network environments.
- **Lightweight**: Suitable for devices with limited computational power and memory.
- **Scalability**: Supports a large number of devices in network deployments.
- **Flexibility**: Can be adapted for a wide range of application protocols and services.

**Disadvantages**:
- **Complexity**: Requires careful handling of options and mechanisms due to optional features.
- **Compatibility**: Not directly compatible with HTTP, requiring gateways or bridging solutions for integration with web services.
- **Latency**: UDP can lead to lower reliability in certain environments without proper configuration.

## See also
- MQTT
- IoT Architecture
- [[edge-computing]]
- LoRaWAN / NB-IoT
- Real-Time Operating System (RTOS)