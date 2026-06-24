---
concept: lorawan
entity_type: concept
aliases: []
sources: ["raw\\07-embedded-systems-and-iot\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-24T07:58:53Z
---

## Definition
LoRaWAN is a **low-power wide-area network** (LPWAN) protocol designed to allow long-range communications at a low data rate. It extends the lora technology by implementing a network architecture specifically tailored for Internet of Things (IoT) deployments. LoRaWAN is built to support battery-powered devices operating in harsh environments, and it ensures bidirectional communication over a broad area while consuming minimal energy.

## How it works
LoRaWAN operates by dividing the network into layers known as the stack, which essentially mimics the OSI model but is customized for IoT requirements. It consists of a physical layer (LoRa) that leverages radio waves for communication, providing long-range capabilities with minimal power consumption. The key difference comes from the network layer, where the protocol establishes a hierarchical structure comprising end devices, gateways, and the central network server. 

In this architecture, end devices are the battery-powered sensors or actuators that communicate periodically with the network. They can operate in three different modes:
- **Class A**: Devices that communicate bi-directionally but only at certain intervals, optimizing power efficiency by limiting dedicated receive windows.
- **Class B**: Like Class A but adds scheduled receive slots, which are predefined for device-to-network communications, with additional control channels.
- **Class C**: Offers the most extended receive windows. In Class C devices, the devices remain in the receive state for almost all times, except for brief periods of transmission and sleep.

The network’s gateways are responsible for receiving and relaying the end devices’ messages to the network server, which handles tasks such as applying security measures, routing messages, and performing general management functions. The architecture of LoRaWAN is designed around the concept of lightweight, bidirectional communications; it achieves this via the use of a star-of-stars topology in which gateways act as transparent bridges, forwarding frames between end nodes and a central network server.

LoRaWAN's approach to network security is robust, implementing a hierarchical model that ensures different layers of security are applied from the node level to the network infrastructure. It uses 128-bit AES encryption keys at the device level (AppSKey and NwkSKey) to secure the application payload and network traffic, respectively. The high-level security infrastructure also supports over-the-air (OTA) activation, enabling a device to securely join the network after being made operational.

## Variants
LoRaWAN is primarily aimed at smart city applications, industrial IoT, and rural IoT deployments. However, there are specific regional LoRaWAN implementations that vary in their design due to different regulatory constraints. For example, in North America, LoRaWAN 1.0 adopts 902–928 MHz for communication, while in Europe, LoRaWAN 1.0 usually uses 868 MHz or 433 MHz. The variations in regional LoRaWAN implementations primarily relate to the frequency bands used and the number of available channels within those bands, as determined by regional spectrum regulations. These variants aim to optimize LoRaWAN for regional deployments, balancing regulatory limitations with the protocol's flexible nature.

## Trade-offs
While LoRaWAN is highly beneficial for IoT applications due to its long-range and low-power capabilities, it does come with certain trade-offs:
- **Latency**: Due to the semi-determinism of the protocol and the need to schedule transmissions, LoRaWAN experiences higher latency compared to real-time protocols like [[rtos]].
- **Data Rate**: LoRaWAN is designed for applications requiring limited data throughput, making it less suitable for high-bandwidth applications. The low data rate is a deliberate trade-off for achieving longer battery life and wider coverage.
- **Network Capacity**: Despite its robustness, LoRaWAN has limited network capacity due to its scarcity of channels and the protocol's approach to frequency reuse. This can become a bottleneck in dense deployments.
- **Complexity**: Implementing LoRaWAN can be more complex for developers due to its infrastructure requirements, including the need for gateways and network servers, as well as the need for maintaining strict network security.

## See also
- [[mqtt]]
- iee802-11
- [[coap]]