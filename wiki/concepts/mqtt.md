---
concept: mqtt
entity_type: concept
aliases: []
sources: ["raw\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T04:15:48Z
---

## Definition
**MQTT (Message Queuing Telemetry Transport)** is a pubsub-messaging-protocol that is designed for use with small wireless networks and the Internet of Things (IoT). MQTT is based on a publisher/subscriber model, where any number of clients can publish messages to topics, and other clients can subscribe to those topics to receive the relevant messages. It is a lightweight protocol that requires minimal network bandwidth and can tolerate weak or intermittent network connections.

## How it works
MQTT is a real-time-communication (RTComm) protocol that uses a publish/subscribe model. The architecture of MQTT involves three major components:

1. **Broker**: The MQTT broker acts as a central hub that processes the messages. Published messages are delivered to subscribers or queued for later delivery if a subscriber is offline.
2. **Publisher**: A client that sends messages to a topic on the broker.
3. **Subscriber**: A client that listens for messages on specified topics and receives them from the broker.

Each message published by a client includes a topic name. Clients can subscribe to specific topics or use wildcard subscriptions to match multiple topics. The broker routes messages according to the topic hierarchy. To ensure data integrity and security, MQTT provides the options for encryption and authentication between clients and the broker.

### Connection and Message Lifecycle
When a client connects to an MQTT broker, it goes through a connection handshake process, during which authentication and encryption settings can be negotiated. The communication that follows can be either persistent or non-persistent. Persistent connections allow for message queuing and delivery when clients come back online, ensuring messages are not lost.

## Variants
- **MQTT versions**: The latest standard is MQTT 5.0, which added features for Quality of Service (QoS) options, message retry algorithms, and more robust error handling. It builds on previous versions 3.1 and 3.1.1 by extending the core functionality.
- **Twisted MQTT**: An attempt to optimize MQTT for high-performance Python applications by using the Twisted network engine, allowing for faster message handling and connection management.
- **Alternatives**: Protocols like CoAP (Constrained Application Protocol) and 6LoWPAN (IPv6 over Low Power Wireless Personal Area Networks) can be used in environments where the constraints of MQTT are too restrictive.

## Trade-offs
Implementing MQTT comes with several trade-offs that need to be considered:

- **Scalability**: While MQTT can handle large numbers of clients, performance can degrade at extreme scale. This depends largely on the broker's capabilities and connection-handling strategies.
- **Setup Complexity**: The underlying network setup and broker setup can be complex, especially when implementing on [[embedded-systems]] for IoT devices.
- **Control Over Network**: MQTT's use in embedded systems can depend on existing network infrastructure or IoT gateways to manage connectivity, which can be a bottleneck in certain installations.
- **Security**: Although MQTT supports TLS for encryption, the complexity of managing certificates and ensuring a secure connection can be significant. This is particularly relevant for ensuring data privacy and mitigating security risks in IoT setups.

## See also
- mqtt-extensions
- mqtt-use-cases