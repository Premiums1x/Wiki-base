---
concept: spi
entity_type: concept
aliases: []
sources: ["raw\\07-embedded-systems-and-iot\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-24T07:58:17Z
---

## Definition

SPI (Serial Peripheral Interface) is a synchronous serial communication interface standard that enables high-speed communication between different types of electronic circuits and devices. It is commonly used to connect microcontrollers to peripherals such as sensors, actuators, and memory chips.

## How it works

The SPI communication protocol consists of four signals: MOSI (Master Out, Slave In), MISO (Master In, Slave Out), SCK (Serial Clock), and CS (Chip Select). The MOSI and MISO lines carry the data, while SCK produces the clock pulses, and CS specifies the device active for data transmission. MCUs typically implement SPI natively, enabling them to communicate directly with SPI-compliant devices at high speeds, typically up to several megahertz. SPI is a full-duplex protocol, meaning data can be transferred both ways simultaneously. This is in contrast to UART, which is half-duplex, and I2C, which, although also full-duplex, is significantly slower and uses fewer wires.

## Variants
SPI has a few standard modes that differ according to the phase and polarity of the data relative to the clock signal. These modes are characterized by two parameters, CPOL (Clock Polarity) and CPHA (Clock Phase). CPOL determines whether the inactive state of the clock signal is low (CPOL=0) or high (CPOL=1). CPHA determines whether the data is sampled on the leading edge (CPHA=0) or trailing edge (CPHA=1) of the clock pulse. There are four possible combinations of CPOL and CPHA, each suited to different types of peripherals and timing requirements.

## Trade-offs
SPI, while fast and efficient, has some trade-offs. It requires more physical pins and a dedicated clock line compared to I2C, which uses fewer wires and is serial in nature. However, SPI's speed and simplicity can trades-off with complexity in multi-slave systems, as the separate CS line is required for each slave.

The need for dedicated hardware also means SPI can be more challenging to implement in software, especially on systems where GPIO pins are used for other tasks. Additionally, being a half-duplex protocol, SPI mandates that data transmission and reception occur in alternating intervals, or that separate MOSI and MISO lines be used for simultaneous transfer in full-duplex implementations.

## See also
- MCU
- UART
- I2C