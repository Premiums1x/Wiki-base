---
concept: iic
entity_type: concept
aliases: ["i2c"]
sources: ["raw\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-23T04:15:38Z
---

## Definition
Iic stands for Inter-Integrated Circuit (I²C for short), a multi-master, multi-slave serial communication protocol that enables communication between integrated circuits. It is typically used when building circuits that need to send data from one chip to another, and it is designed to provide a simple and flexible method of connecting between multiple compatible integrated circuits. [[embedded-systems]] extensively utilize I2C for efficient communication between different components and io-devices. I2C builds on the concept of serial communication to provide a robust, two-wire interface that supports multiple slaves on the same bus. 

## How it works
I2C operates over two lines: SDA (Serial Data) and SCL (Serial Clock). The data and clock lines are pulled up to the power supply voltage with resistors, which allows for open-drain communication. Each device on the I2C bus can be a master, a slave, or both. A master initiates a communication by sending a start condition followed by a device address (7-bit or 10-bit), which is then broadcasted over the bus. Each slave is addressed uniquely by a specific address, allowing selective communication with particular devices. After addressing, the master sends read or write commands to the addressed device, and data is exchanged accordingly.

One of the key features of I2C is its support for multi-slave operation: once a device responds and acknowledges the address, the master may initiate another start condition and address a different device. This feature is implemented by the use of an acknowledge signal on every byte sent over the bus, allowing the master to determine if the operation was successful and the slave is ready for the next transaction.

The master sends a stop condition to complete the transaction. The speed of I2C can vary; common standards include Standard Mode (100 kbit/s), Fast Mode (400 kbit/s), and High-Speed Mode (3.4 Mbit/s). I2C is widely used in embedded systems due to its simplicity and reliability.

## Variants
Although I2C is a standardized protocol, some devices may implement slight variations to accommodate specific needs or enhance performance, such as clock stretching or extended addressing. These variants often provide additional features but generally remain compatible with standard I2C implementations, ensuring a wide range of interoperable devices. I2C is often implemented as an io-interface in microcontrollers and other devices to facilitate communication with peripherals such as sensors or memory chips.

## Trade-offs
While I2C offers a straightforward and widely supported method of communication, there are associated trade-offs. I2C is slower compared to alternatives like SPI (Serial Peripheral Interface). This is due to its reliance on being CPU-driven for clock generation, which can lead to performance limitations in high-speed applications. Additionally, I2C's use of open-drain signaling and pull-up resistors means it can require more power than other protocols, especially in applications where the bus is not fully powered down.

I2C also trades off simplicity for flexibility; while the two-wire interface is easy to implement, it can lead to potential bottleneck issues in highly parallel communication-protocols. However, the simplicity and wide compatibility of I2C frequently outweigh these limitations, making it a preferred choice for many embedded applications.

## See also
As mentioned, I2C is heavily integrated into [[embedded-systems]], and it depends-on the broader infrastructure of these systems, including [[mcu]]s (MCUs) and io-devices. The protocol often optimizes for ease of use and broad compatibility in constrained environments, contrasting with other, potentially faster protocols like [[spi]] which, while faster, require more interface lines, negating some of the benefits of I2C in certain applications. Understanding I2C is crucial for developers working with embedded systems and IoT, as it forms the basis of many peripheral interactions within these systems.