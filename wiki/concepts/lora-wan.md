---
concept: lora-wan
entity_type: technique
aliases: []
sources: ["raw/embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T03:35:20Z
---

## Definition

LoRaWAN (Long Range Wide Area Network) is a Low-Power Wide-Area Network (LPWAN) protocol designed specifically for the long-range transmission of data at a low bitrate among battery-powered Internet of Things (IoT) devices. LoRaWAN is an open standard maintained by the LoRa Alliance that enables the connection of these devices to the internet via a gateway to backend servers.

## How it Works

LoRaWAN utilizes the long-range, lower-power radio frequency modulation LoRa (Long Range) to transmit data over long distances while consuming minimal power, making it ideal for IoT devices that need to operate for years on a single battery charge. The network consists of:

- **End devices**: IoT devices that communicate with the gateways, typically using a LoRa transceiver.
- **Gateways**: Bridges between the end devices and the back-end network infrastructure. They can connect to multiple end devices and forward the messages to a network server.
- **Network Server**: Manages connections between gateways and end devices, performs network operations like joining and message forwarding.
- **Application Server**: Manages the application-specific logic and data storage.

LoRaWAN supports both bi-directional communication for firmware updates and sensor data reporting. Encryption is built into the standard, providing security for both the network sessions and device applications.

### Frequency Bands

LoRaWAN operates on sub-GHz ISM bands, which vary based on region:
- **EU 868 MHz**: Used in Europe, Russia, and other countries.
- **US 915 MHz**: Used in the United States and Canada.
- **Asia 915-928 MHz**: Used in Japan, Australia, India, and other countries.
- **China 470-510 MHz**: A specific band used in China.

These low-frequency bands enable long-range communications with minimal interference and deep indoor coverage.

### Network Topology

LoRaWAN supports a star-of-stars topology:
- **Star Network**: A single gateway manages multiple devices, facilitating data aggregation and transmission.
- **Multi-Gateway Network**: Devices can communicate with multiple gateways redundantly, improving reliability.

## Variants

- **Class A**: Basic LoRaWAN class with uplink and downlink slots triggered by uplink transmissions, adhering to battery-saving principles.
- **Class B**: Incorporates additional downlink slots synchronized via periodic beacons from the gateway, reducing latency for downlink communication.
- **Class C**: Continuous reception window for downlink transmissions whenever possible, excluding power-saving for specific use cases.
- **Custom Network Topologies**: Some implementation strategies may involve custom gateways or network servers to meet specific deployment requirements or augment network coverage.

## Trade-offs

### Key Trade-offs
- **Power vs. Range**: LoRaWAN sacrifices data rate for extended range and battery life. Devices operate at lower data rates to maximize battery life and improve signal reception.
- **Latency vs. Reliability**: Class C provides the lowest latency due to its constant reception window, but increases power consumption; Class A minimizes power usage but at the cost of higher downlink latency.
- **Privacy and Security**: Encryption provides strong security, but the necessity of a dedicated server increases initial setup complexity and cost.
- **Deployment Complexity**: Deploying LoRaWAN requires setting up gateways, network servers, and application servers, which can be complex compared to simpler, cellular alternatives.

## See also

[[embedded-systems]]IoTMQTTFreeRTOSESP32