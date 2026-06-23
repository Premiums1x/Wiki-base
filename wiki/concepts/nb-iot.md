---
concept: nb-iot
entity_type: concept
aliases: []
sources: ["raw\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T04:15:56Z
---

## Definition
Narrowband IoT (NB-IoT), short for Narrowband Internet of Things, is a radio technology standard that builds on low-power wide-area network (LPWAN) principles, aiming to provide extensive coverage with low power consumption for Internet of Things (IoT) devices. NB-IoT is optimized for deep rural coverage, urban canyons, and indoor penetration, and is designed to operate in licensed frequency bands.

## How it works
NB-IoT operates using licensed frequency bands which ensure a higher quality of service (QoS). Its technical architecture leverages sub-GHz spectrum bands (868 MHz in Europe) where propagation characteristics are better for long range, but also supports other frequencies like 900 MHz and 1800 MHz. Devices communicate over narrow bandwidths which reduce complexity and power consumption. This technology implements a star topology where multiple devices connect directly to a base station, thereby simplifying network design and deployment costs are reduced. 

Energy efficiency is a key aspect of NB-IoT, often supporting device lifespans of over a decade on battery. It achieves this by employing energy-saving modes (PSM, Power Saving Mode) for devices to minimize radio usage, thus conserving power. NB-IoT is compatible with geographic roaming, allowing IoT devices to stay connected when moving between regions.

Enhanced battery life in NB-IoT devices is mainly due to the inclusion of several low-power techniques. LTE-M, a related technology that shares many similarities with NB-IoT, also employs similar mechanisms for battery conservation but focuses more on voice capabilities and slightly faster data rates.

## Variants
Despite being a single technology, there are different implementations of NB-IoT depending on the operator or vendor. These implementations vary based on hardware specifications, firmware versions, and supported features such as frequency bands and PSM parameters. However, the core principles and objectives remain consistent across different NB-IoT networks.

## Trade-offs
NB-IoT faces a few trade-offs and limitations, notably in terms of data throughput and connection density. Due to the narrow bandwidth, each NB-IoT cell supports around 50,000 to 100,000 devices, which is fewer compared to cellular networks with broadband. Additionally, the data upload rates are limited to 250 kbps, and download rates to 250 kbps or less, which is insufficient for high-bandwidth applications. However, for data-intensive tasks, alternative technologies like LTE-M lte-m that provide faster data rates may be required. 

NB-IoT is also more cost-effective for low-rate applications and for devices requiring long-range and deep indoor coverage where LTE-M's requirements or costs may be prohibitive.

## See also
low-power wide-area network  
lte-m