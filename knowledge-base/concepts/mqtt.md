---
concept: mqtt
entity_type: concept
aliases: []
sources: ["raw\\07-embedded-systems-and-iot\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-24T07:58:45Z
---

## Definition
MQTT (Message Queuing Telemetry Transport) is a lightweight publish-subscribe-based messaging protocol that is well-suited for Internet of Things (IoT) applications. It operates over TCP/IP-based networks, providing a way for devices with limited network bandwidth and high-latency connections to communicate with back-end IoT cloud platforms. MQTT extends the embedded-systems premise by ensuring that IoT devices can reliably transmit data in resource-constrained environments. 

## How it works
MQTT operates on a publish-subscribe model, where devices can both publish and subscribe to topics. Topics are logical channels that help categorize and organize data streams. When an IoT device publishes data to a specific topic, any subscribing device that is listening to that topic receives the published data. This decoupling allows for a scalable architecture, where publishers and subscribers do not need to be actively connected at the same time.

### Connection Types
- **Clean session**: A device can initiate a connection with or without a clean session flag. If a clean session is established, the server will not retain any messages for the client should the session be interrupted and reconnected. Conversely, if the session is dirty, the server will retain messages for the client even if the connection is lost.
- **QoS levels**: MQTT supports three quality of service levels:
  - **QoS 0 - At most once**: Data is delivered at most once. No acknowledgment is received, meaning there is no guarantee that the message will be delivered.
  - **QoS 1 - At least once**: Data is delivered at least once, with an acknowledgment and retry mechanism if the message cannot be confirmed.
  - **QoS 2 - Exactly once**: Data is delivered exactly once, ensuring that the message is sent and confirmed exactly once, avoiding duplicates and omissions.

### Connectivity
Due to wireless network constraints, MQTT can be used with optional intermediaries, such as MQTT Brokers, which are crucial for reliability, security, and scalability. The Broker acts as a go-between for IoT devices by storing messages temporarily until they are delivered.

In contrast to MQTT, CoAP (Constrained Application Protocol) is an alternative protocol designed for constrained networks. While CoAP is based on REST principles and HTTP-like semantics, it is optimized for resource-constrained IoT devices, making it a viable but distinct choice for certain types of IoT implementations.

## Variants
Over the years, the MQTT protocol has seen several versions:
- **MQTT v3.1.1**: Released in 2014, this version introduced the WILL and AUTH options, enhancing session management and authentication capabilities.
- **MQTT v5.0**: Announced in 2018, this version includes more flexible connection parameters, improved error-handling, and extended usability features, extending and improving upon the capabilities of MQTT v3.1.1.

## Trade-offs
While MQTT is highly beneficial for IoT applications due to its low overhead and reliability, it does have limitations:
- **Scalability**: While MQTT is designed to be scalable with the help of brokers, the architecture relies heavily on central servers, which can become a single point of failure.
- **Device complexity**: Implementing MQTT can increase software complexity, especially when compared to other protocols like CoAP that are simpler in design and have lower implementation complexities.
- **Security**: Basic MQTT only provides rudimentary security measures like username/password authentication. More advanced security measures may require additional components, such as TLS encryption, which can add overhead and complexity.

## See also
mqtt-broker, mqtt-implementation, mqtt-optimization, mqtt-dependency