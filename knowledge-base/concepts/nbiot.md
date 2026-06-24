---
concept: nbiot
entity_type: concept
aliases: []
sources: ["raw\\07-embedded-systems-and-iot\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-24T07:58:49Z
---

# NBIoT (Narrowband IoT)

Narrowband IoT (NBIoT) is a cellular LPWAN (Low Power Wide Area Network) communication technology that builds on the [[iot-architecture]] principles to provide greater system capacity for a large number of devices and optimized battery life. It is designed to support wide-area coverage with low throughput requirements, and operates within the licensed spectrum. NBIoT is particularly suitable for applications that require low bandwidth, long battery life, and wide coverage, such as smart meters and sensors for remote areas.

## How it Works

NBIoT extends the concept of LPWANs by operating in licensed, non-overlapping frequency bands, providing users with guaranteed Quality of Service (QoS) and support for large numbers of devices over wide geographic areas. This technology leverages the global telecom infrastructure and builds on the lo-rwan by enhancing reliability and network coverage for low-power devices. It operates in licensed spectrum but can coexist with existing 2G, 3G, and 4G networks, utilizing their idle spectrum. This makes it a preferred choice for applications that need guaranteed connectivity within a large, mobile network.

NBIoT achieves low power consumption by employing power-saving modes such as the PSM (Power Saving Mode) and the eDRX (Extended Discontinuous Reception Time) feature. These features allow devices to sleep for extended periods, thereby extending their battery life significantly.

## Variants

NBIoT itself is a standardized technology developed by 3GPP (Third Generation Partnership Project) and is not explicitly split into variants. However, standardized frequencies include the 850/900 MHz band, 1800 MHz band, and 2100 MHz bands, which are used based on the regulatory environment of the country or region.

Other LPWAN technologies, such as LoRa and Zigbee, implement similar or complementary approaches for communication across large areas or within specific environments, but they often use different frequency bands and have varying performance characteristics, primarily focusing on standards flexibility versus reliability.

## Trade-offs

While NBIoT enhances the connectivity and reliability of IoT applications, it requires the necessary infrastructure, including base stations and network coverage, which are typically provided by mobile network operators. This dependency makes it less accessible in areas where telecom infrastructure is limited. Additionally, the cost of deploying NBIoT can be higher compared to other LPWANs due to the need for ongoing subscription fees and the initial setup of the infrastructure. Thus, certain applications may find other solutions like LoRa or Wi-Fi more suitable due to lower deployment costs or the absence of existing telecom infrastructure.