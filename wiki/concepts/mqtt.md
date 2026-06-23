---
concept: mqtt
entity_type: technique
aliases: []
sources: ["raw/embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T03:35:03Z
---

## Definition
MQTT (Message Queuing Telemetry Transport) is a lightweight, publish-subscribe-based messaging protocol designed for constrained devices and low-bandwidth networks. It operates on the application layer of the TCP/IP model and enables efficient and reliable message transmission in IoT environments where device resources and network bandwidth are often limited.

## How it works
### Basic Components
- **Broker**: Central hub that manages all communications between publishers and subscribers. It acts as the message router, forwarding messages from publishers to subscribers based on topic subscriptions.
- **Publisher**: Device or application that sends messages along with a topic name to the broker.
- **Subscriber**: Device or application that receives messages via subscription to a particular topic.

### Message Flow
1. **Publish**: A publisher sends a message to the broker, including a topic name, QoS (Quality of Service) level, and payload. The broker receives the message and checks its subscription list.
2. **Broker Role**: The broker then forwards this message to all subscribers who have subscribed to that specific topic, adhering to QoS levels.
3. **Subscribe**: Subscribers receive the message if they are subscribed to the topic and follow QoS rules. Each message must be delivered, delivered once, or delivered at least once depending on the QoS level.

### Quality of Service (QoS)
- **QoS 0 (At most once)**: Best effort delivery, no acknowledgments. The message is lost if the broker, client, or network fails.
- **QoS 1 (At least once)**: Ensures delivery at least once, with acknowledgment from the receiver.
- **QoS 2 (Exactly once)**: Ensures delivery exactly once through a multi-step handshake protocol, providing the highest reliability but with increased overhead.

## Variants
- **Mosquitto**: An open-source MQTT broker widely used due to its simplicity and lightweight nature.
- **Eclipse Paho**: An official MQTT client library providing bindings for multiple programming languages.
- **VerneMQ**: A distributed MQTT broker designed for high availability and scalability.
- **IBM MessageSight**: A scalable MQTT broker with enterprise features such as security and monitoring.
- **EMQ**: Open-source MQTT broker known for performance tuning and complex IoT scenarios.

## Trade-offs
### Advantages
- **Efficiency**: Suits constrained environments by minimizing message payload sizes and network overhead.
- **Scalability**: Well-suited for大规模物联网部署，支持大量设备连接。
- **可扩展性**：适合大规模物联网部署，支持大量设备连接。
- **LoRaWAN兼容性**：可以在低功耗广域网中有效运行。

### 缺点
- **高QoS级别时的通信开销**：较高的QoS级别会增加消息传递的复杂性和带宽需求。
- **中继器单点故障**：依赖于中间的中继服务器，如果中继器故障，可能影响所有连接的设备。
- **安全性**：默认MQTT传输不加密，需要附加安全层如TLS来确保通信安全。

## See Also
嵌入式系统与物联网
实时操作系统
CoAP协议
LoRaWAN