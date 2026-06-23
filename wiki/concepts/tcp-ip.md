---
concept: tcp-ip
entity_type: concept
aliases: []
sources: ["raw\\cybersecurity.md"]
confidence: high
created_at: 2026-06-23T04:12:21Z
---

## Definition
TCP/IP (Transmission Control Protocol/Internet Protocol) is a suite of communication protocols used to interconnect network devices on the internet or on a private network. It is the foundation for data transmission over many different types of networks. ip-layer builds on TCP/IP by providing the network layer functionality, focusing specifically on the routing and addressing necessary to deliver data to its destination.

## How it works
TCP/IP operates in a layered model, with each layer responsible for specific tasks and interactions. The system is organized into four layers: the link layer, internet layer, transport layer, and application layer.

### Link Layer
The link layer (or data link layer) handles the transmission and reception of individual data frames over a physical transmission medium. It ensures reliable delivery of data and contains two sublayers: Media Access Control (MAC) and Logical Link Control (LLC).

### Internet Layer
ip-layer implements the internet layer, which is responsible for routing packets to their destination through a network. It uses IP addresses to identify and locate networked devices. IP addresses are crucial for directing packets to their intended destinations.

### Transport Layer
The transport layer ensures that data is transferred from source to destination. It includes the TCP and UDP protocols:
- **Transmission Control Protocol (TCP)**: A connection-oriented protocol that guarantees reliable transmission of data. TCP establishes a connection with the recipient and then sends and acknowledges packets until all packets have been received correctly. It supports flow control and error recovery, making it suitable for applications requiring low error rates, such as web browsing (http-protocol) and email.
- **User Datagram Protocol (UDP)**: A connectionless protocol that provides a fast, best-effort delivery service without guaranteed delivery. UDP is used in situations where speed is more important than reliability, such as streaming media, online gaming ([udp-protocol]), and DNS queries.

### Application Layer
At the application layer, data is formatted in a way that can be understood by the end user. Application protocols such as HTTP, FTP, Telnet, DNS, SMTP, and others are used to exchange data between applications. This layer directly interacts with the end-user applications.

## Variants
There are multiple variants of TCP/IP protocols that are used in specific contexts:
- **TCP/IPv4**: The older version of IP, which is still widely used but is being gradually replaced by IP version 6 (IPv6) due to address limitations.
- **TCP/IPv6**: A newer version of IP designed to increase the address space significantly. IPv6 addresses are twice as long as IPv4 addresses, allowing for a substantially larger number of available IP addresses and better addressing in a globally connected world.
- **TCP/TLS**: While not strictly a variant of TCP/IP, the use of TCP over TLS (Transport Layer Security) provides an encrypted tunnel for TCP-based communications, enhancing security for data transmission. TLS uses the TCP protocol to establish a secure connection before transmitting data.

## Trade-offs
TCP/IP has several trade-offs and considerations:
- **Latency**: TCP's reliability introduces additional latency due to its handshaking and retransmission mechanisms. This can be a significant drawback in real-time applications, where low latency is critical (real-time-communication) and quick delivery is more important than perfect transmission.
- **Scalability**: The efficiency and performance of TCP/IP can vary with network traffic and complexity. In large-scale networks, TCP/IP may need optimizations and enhancements to maintain performance and reliability with very high data rates or a large number of simultaneous connections.