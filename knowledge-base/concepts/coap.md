---
concept: coap
entity_type: concept
aliases: []
sources: ["raw\\07-embedded-systems-and-iot\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-24T07:58:41Z
---

## Definition
constrained-application-protocol ([CoAP]) is a specialized version of the HTTP protocol designed for use in embedded-systems-and-iot|embedded systems and IoT. It operates over the User Datagram Protocol (UDP) and is designed to be lightweight, making it suitable for environments with limited resources and low-bandwidth constraints, extending the principles of embedded-systems-and-iot|embedded systems and IoT communication.

## How it works
CoAP operates on a request-response model similar to HTTP, but leveraging UDP instead of TCP. This protocol enables client-server communication in resource-constrained environments. A server can be queried for content or can push content to a client upon request. A key aspect of CoAP is its support for HTTP-compatible methods like GET, POST, PUT, and DELETE, which allows for a familiar interaction model for developers accustomed to building web applications. However, due to its usage over UDP, CoAP introduces mechanisms like observation (subscribe) for supporting asynchronous push notifications, which is essential for IoT applications.

### Packet Structure
CoAP messages consist of three main components: the header, options, and payload. The header is just four bytes, which allow for a simple and efficient structure. Options can extend the header to specify various message lengths and request types, and the payload contains the actual content of the message. This design keeps the communication minimal yet robust, enhancing its suitability for embedded environments.

### Multicast
Another significant feature of CoAP is its support for multicast messages, allowing a single request to reach multiple devices. This capability is particularly useful in IoT scenarios where numerous devices need to be queried or monitored simultaneously, representing a trade-off between network bandwidth and efficiency.

## Variants
- CoAP relies on a non-blocking, asynchronous communication model, which is preferred over synchronous methods in embedded systems due to their time-sensitive nature and the need for efficient use of available resources.
- CoRE (Constrained RESTful Environments) is a group that is responsible for furthering the standards and practices around CoAP, promoting its use and extension in edge computing scenarios and IoT devices.

## Trade-offs
While CoAP offers significant advantages in terms of minimal overhead and ease of use, it has its limitations. It operates over UDP, which means it lacks the reliability features of TCP, such as guaranteed packet delivery and retransmission. This can lead to challenges in environments requiring high reliability, especially in critical or high-usage scenarios, where the lack of built-in reliability mechanisms can be a significant drawback. Thus, it trades off reliability for efficiency, optimizing data transfer in constrained environments at the cost of robust error handling.

## See also
[[mqtt]], [[http]], [[udp]], embedded-systems-and-iot