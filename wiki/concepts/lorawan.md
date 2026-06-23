---
concept: lorawan
entity_type: concept
aliases: []
sources: ["raw\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T04:15:52Z
---

## Definition
LoRaWAN (Long Range Wide Area Network) is an open standard for devices to communicate over a large region with low power and long battery life. It builds on mac-protocols by extending traditional MAC protocols to suit low-power, long-range communication, making it a crucial technology within the realm of iot-architecture. LoRaWAN uses LoRa modulation for long-range communication, enabling it to connect millions of battery-powered devices over a large geographic area.

## How it works
LoRaWAN operates using a star-of-stars topology where gateways act as bridges between end-devices and a central network server. Devices in this network can be either class A (battery-powered end-nodes with bi-directional communication in low-duty cycle), class B (scheduled receive slots for lower latency), or class C (always listening for messages, except when sending, offering bi-directional communication without latency constraints). LoRa modulation, which is optimized for longer distance communication, allows for multi-tier spread spectrum communication. The network sometimes uses UDP as its transport protocol, extending conventional transport layer protocols to fit its operational requirements, while providing a range of data rates tailored to suit different use cases and distance needs.

In LoRaWAN, the end-devices communicate with the network server via gateways using the LoRa modulation. The network server can authorize a message for delivery and reroute it if necessary, ensuring robustness in communication over potentially unreliable long-range communications. The use of such a system ensures that messages can reach their destination despite the challenging conditions of a large-scale, wide area network. The functionality of LoRaWAN thereby greatly depends on the underlying protocol design, focusing on optimizing power consumption and transmission range.

## Variants
LoRaWAN implementations come in various configurations, which depend on the region and regulatory requirements. For instance, LoRaWAN 1.0 implements adaptive data rate (ADR) to optimize the operational parameters of the end-device based on the environment and range. Similarly, LoRaWAN 1.1 adds support for finer channel spacing, allowing for denser networks. There are also emerging versions like LoRaWAN 1.2 which improve upon the previous versions by introducing enhancements in security features and supporting enhanced data rates in specific classes of devices.

LoRaWAN is often compared to other low-power wide area network (LPWAN) protocols like NB-IoT (Narrowband Internet of Things), which is known to trade-offs with LoRaWAN by offering potentially superior network coverage and security features. NB-IoT does not extend the use of LoRa modulation and is built on the cellular infrastructure, making it more suited for scenarios where cellular network coverage is available or required.

## Trade-offs
The reliance on LoRa modulation in LoRaWAN could trade-offs with the capacity and performance of other LPWAN solutions, particularly in densely populated areas. However, it is highly optimized for long-range communication and low power consumption, which are primary considerations for LoRaWAN's design. LoRa modulation requires trade-offs in bandwidth efficiency as the extended range comes at the expense of data rates. Additionally, the network design of LoRaWAN imposes constraints on bidirectional communication frequency, which can result in higher latency or reduced availability of bidirectional communication.

In terms of security, LoRaWAN also requires a trade-off by making compromises in public key infrastructure (PKI) adoption to reduce the overhead on end-devices. Despite efforts to improve this, the security model remains trade-offs with advanced cryptographic protocols commonly seen in more resource-intensive networks.

## See also
- mac-protocols
- iot-architecture