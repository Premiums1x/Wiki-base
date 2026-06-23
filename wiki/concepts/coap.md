---
concept: coap
entity_type: concept
aliases: []
sources: ["raw\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T04:15:47Z
---

## Definition
Constrained Application Protocol (CoAP) is a lightweight, application layer communication protocol designed for use with constrained nodes and low-power IoT devices. CoAP operates over the User Datagram Protocol (UDP) to allow for the seamless exchange of information between devices and sensors over resource-constrained environments, providing a mechanism for agents connecting via the Internet such as web browsers or existing HTTP infrastructure to interact with such devices web-protocols.

## How it works
CoAP builds on top of udp for transmission, offering both request-response and observe modes to facilitate a messaging exchange model similar to http. Unlike HTTP, CoAP over UDP enables minimal overhead and reduced power consumption, which is critical for IoT devices with limited computational resources and energy constraints. This protocol uses a request-response architecture, where clients send requests to a server to perform operations such as reading, creating, updating, or deleting resources. The CoAP server receives these requests and returns appropriate responses.

A key feature of CoAP is its ability to handle resource-constrained environments efficiently hardware-constraints. It operates using fewer bytes, meaning less data needs to be sent over the network, thus consuming less power and conserving bandwidth. Additionally, CoAP's confirmable (CON) and non-confirmable (NON) messages enable flexibility in communication structures. Confirmable messages require acknowledgment from the recipient, ensuring reliability but coming with a slight overhead, whereas non-confirmable messages do not necessitate acknowledgments, prioritizing speed and efficiency.

Another notable aspect is the use of the observe option, which allows a client to set up a subscription for changes in resources, enabling efficient monitoring without the need for ongoing polling.

CoAP also supports block-wise transfer for retrieving large objects, thus preventing the transmission of overly large packets which could exceed the resources of a device in constrained environments.

## Variants
CoAP can be extended with various options such as observe, block-wise transfer, etc., depending on the specific needs of the application. There are no significant variants of CoAP to date that are widely adopted, but it is worth noting that CoAP-Lite, a version that uses even fewer bytes and is designed for extremely constrained environments, exists but is not as commonly implemented as standard CoAP.

## Trade-offs
CoAP trades off the reliability and security provided by tcp and http for reduced overhead in both data size and processing power, making it particularly suitable for low-power, high-latency networks. However, this trade-off means that CoAP cannot guarantee message delivery or confidentiality assured by TCP-based protocols; instead, it relies on application-layer mechanisms to handle reliability and encryption.