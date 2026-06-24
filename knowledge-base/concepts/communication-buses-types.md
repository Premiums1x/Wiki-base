---
concept: communication-buses-types
entity_type: concept
aliases: []
sources: ["raw\\07-embedded-systems-and-iot\\embedded_systems_iot.md"]
confidence: high
created_at: 2026-06-24T09:43:39Z
---

## Definition
Communication buses are essential infrastructure within embedded systems, enabling the transmission of data between different components or systems. These buses facilitate the exchange of commands, data, and control signals, allowing devices to interact efficiently and perform their designated functions. Examples of communication buses include UART, i2c, and spi, each designed to meet specific requirements in terms of speed, reliability, and simplicity.

## How it works
Communication buses operate by transmitting data through a series of predefined protocol rules, which dictate how information is packaged, sent, and received. The protocol defines signals for setting up communication, such as start and stop conditions, as well as error detection mechanisms to ensure data integrity.

### UART
Universal Asynchronous Receiver/Transmitter (UART) is one of the most basic serial communication protocols, requiring only two data lines: TX for transmitting and RX for receiving data. UART operates asynchronously, meaning no clock signal is needed between the communicating devices. It is commonly used for simple point-to-point communication, and it does not require complex master/slave setups.

### I2C
i2c (Inter-Integrated Circuit) is a multi-device serial communication protocol that uses two bidirectional lines: SDA (Serial Data) and SCL (Serial Clock). This protocol supports multiple devices connected to a single bus, allowing for more complex interactions. The controller or master device initiates and controls data transfer, while slave devices respond. I2C simplifies connection wiring and can support many more devices on a single bus compared to UART.

### SPI
Serial Peripheral Interface (SPI) is another synchronous communication protocol that requires four lines: clock (SCK), master out slave in (MOSI), master in slave out (MISO), and slave select (SS). Unlike UART and i2c, SPI operates in a master-slave configuration, where the master initiates data transfers by generating clock pulses. SPI is faster than i2c, making it suitable for applications requiring high-speed data transfer, such as interfacing with high-speed peripherals.

Each communication bus protocol builds on the basic principles of serial communication but introduces unique characteristics to suit specific application requirements. For instance, the spi protocol requires more lines for data transfer compared to UART and I2C but offers higher throughput due to its synchronous nature, which reduces overhead related to clock signal transmission.

## Variants
The fundamental designs of communication buses can vary based on the requirements of the application, including the need for higher data rates, increased flexibility, or enhanced error detection capabilities.

- **Serial Communication**: Both UART and I2C are forms of serial communication, where data is transmitted bit by bit over a single channel. These are useful in applications requiring minimal signal lines, such as embedded systems where space and cost are critical factors.
- **Parallel Communication**: While not discussed here, it contrasts with the serial methods like spi, i2c, and UART by transferring multiple bits simultaneously over multiple wires. Parallel communication can increase bandwidth but requires more physical connections and can be less compatible with longer distances.

### Implementations
- **UART**: Hardware implementations of UART can typically be found integrated into microcontrollers (MCUs) such as STM32, ESP32, and Arduino boards.
- **I2C and SPI**: Similar to UART, these protocols are also implemented in hardware within MCUs. Additionally, peripheral devices such as sensors and memory chips often include integrated I2C and SPI interfaces to facilitate communication with host controllers.

## Trade-offs
The choice of communication bus relies heavily on the specific needs of the application. Each protocol has its own set of trade-offs:
- **Latency and Throughput**: SPI generally offers the highest data throughput, making it ideal for high-speed applications where minimizing latency is crucial.
- **Complexity of Wiring and Design**: UART and I2C simplify the wiring requirements compared to spi, making them suitable for designs where the number of signal lines is limited.
- **Number of Addressable Device Nodes**: I2C supports a larger number of devices per bus compared to SPI, which can be a limitation in applications needing intricate control over multiple peripherals. SPI, however, due to its master-slave configuration, simplifies the protocol configuration compared to a multi-master setup.

## See also
- embedded-systems
- iot
- microcontroller
- interrupts