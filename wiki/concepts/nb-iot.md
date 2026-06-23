---
concept: nb-iot
entity_type: technique
aliases: []
sources: ["raw/embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T03:35:23Z
---

## Definition
Narrowband IoT (NB-IoT) is a low-power wide-area network (LPWAN) radio technology standard used to enable cellular connectivity for the Internet of Things (IoT). It is designed to connect low-cost, low-energy devices for the smart city, smart agriculture, and intelligent transportation applications in a range of industries, including manufacturing, utilities, and logistics.

## How it Works
NB-IoT operates within the LTE framework but is designed specifically to support a large number of low-bandwidth devices that require low data rates and long battery life. It can be deployed in bands currently used by non-LTE technology, utilizing unused LTE carriers, or in dedicated bands.

Technical details include:

- **Narrow Band Channel**: The primary feature is the use of a narrower radio channel (200 kHz) compared to standard LTE, allowing higher concentration of devices in a single cell.
- **Low Transmission Power**: NB-IoT devices can operate at much lower transmission powers, extending battery life and reducing the need for frequent charging or battery replacement.
- **Extended Coverage**: Due to its design, it can provide better coverage, especially in indoor and hard-to-reach areas, by taking advantage of the robust architecture of cellular networks.
- **Optimized Data Transmission**: Data transmission is optimized for low throughput requirements, thus maintaining device connectivity and reducing latency.

## Variants
There are several implementations and extensions of NB-IoT:
- **3GPP Release 13**: The initial standard for NB-IoT.
- **3GPP Release 14 and beyond**: Enhancements include further improvement in device power consumption, latency reduction, and support for additional frequency bands, providing a more robust and flexible LPWAN technology.

Alternatives to NB-IoT include other LPWAN technologies such as:
- **LoRaWAN**: Utilizes unlicensed spectrum and is known for its long range and low power consumption.
- **Sigfox**: Another LPWAN technology that supports bi-directional communication at a low data rate and long range with very low energy consumption.

## Trade-offs
### Key Trade-offs
- **Spectrum Usage**: NB-IoT utilizes the licensed spectrum which ensures better quality and reliability, but it is more expensive and requires coordination from mobile network operators.
- **Latency and Throughput**: While it is optimized for low-bandwidth applications, there are limitations in handling data-heavy or real-time applications.
- **Coverage and Standby Time**: Provides extensive coverage and prolonged battery life, critical for sensors or devices operating in remote or hard-to-reach locations, but at the cost of lower data rates and slower throughput.

### Limitations
- **Data Rate**: Limited to very low data rates, which may not be suitable for applications requiring more extensive data transmission.
- **Cost**: NB-IoT network deployment and operation are often dependent on the availability and policies of cellular operators.
- **Bandwidth**: The narrowband nature limits the number of devices that can be efficiently connected without added complexity or cost.

## See also
- MQTT
- LoRaWAN
- IoT Architecture
- [[edge-computing]]
- RTOS