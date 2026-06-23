---
concept: spi
entity_type: concept
aliases: []
sources: ["raw\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T04:15:37Z
---

## Definition
SPI (Serial Peripheral Interface) is a synchronous serial communication interface used for short-distance communication, uart, [[iic]], and other similar interfaces connected to the same microcontroller (MCU). SPI communicates with different devices by transferring data over multiple parallel channels, typically four lines including MOSI (Master Out Slave In), MISO (Master In Slave Out), SCK (Serial Clock), and CS (Chip Select).

## How it works
SPI facilitates high-speed data communication with a controller at one end and a peripheral device at the other. It consists of four wires: MOSI and MISO for data transmission in two different directions, SCK for the clock signal, and CS to specify which device peripheral is selected mosi, miso, sck, cs. A master device typically initializes the lines and generates the SCK signal, synchronizing data transfers with slave devices. The master controls when data is sent and sampled on the SCK, making SPI highly suitable for applications requiring fast data transfer such as multimedia data exchange multimedia-data-exchange, due to its higher throughput compared to I2C.

SPI operates in either full-duplex mode, where data can be sent and received simultaneously, or half-duplex mode, where data can be sent or received at a time but not both. The master typically drives the clock and all three lines connected to the slave device. The master sends data on MOSI and receives data on MISO. Slave devices can handle multiple masters if they have dedicated lines for each master. The chip select (CS) pin allows the master to select which slave device to communicate with on a shared bus.

The control protocol in SPI has manual parity checking but does not have a checksum or cyclic redundancy check (CRC). Any disadvantages are not outweighed by the need for error-checking because the CLK clock will resend erroneously received data until the requesting master accepts the data.

SPI communication is highly efficient and fast due to its hardware-based parallel communication. However, it has a fixed speed and lacks the automated error-checking mechanisms that protocols like [[mqtt]], [[coap]] might offer, making it less suitable for long-distance or unreliable network conditions.

## Variants
Most variants of SPI focus on different configurations of the SPI interface rather than significantly altering the core SPI protocol. Commonly, microcontrollers can be configured to enable or disable CS for controlling multiple slaves on a single bus, or to change the direction and state of the lines. There are also specific implementations of SPI in different devices that may set standards such as the SPI 4.0 Protocol by Freescale offering half-duplex synchronous serial interface, which is now underlined as General-Purpose-SPI (gspi) specifications, allowing for more flexibility and efficiency in device operations.

## Trade-offs
The primary trade-off of SPI is its hardware dependency. To use SPI, devices must support the necessary hardware lines (MOSI, MISO, SCK, CS) and the protocol itself. This makes it less flexible than software-defined protocols like MQTT or CoAP. Additionally, each added device on a SPI bus increases the hardware requirements on the bus, meaning that each additional device requires its own CS line, thus adding to the complexity of managing different peripheral devices on a single bus.

The higher speed of SPI relative to I2C comes at the cost of greater pin and wiring needs; SPI demands four lines per device, whereas I2C only needs two, which makes it simpler for devices with limited pinout availability but also means that SPI can often handle larger data volumes more efficiently due to its two-wire data transmission capability versus the single-wire used by I2C.