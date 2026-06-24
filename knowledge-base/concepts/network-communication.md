---
concept: network-communication
entity_type: concept
aliases: []
sources: ["raw\\09-cybersecurity\\cybersecurity.md"]
confidence: high
created_at: 2026-06-24T07:59:14Z
---

## Definition
Network Communication refers to the transmission and reception of data between different devices or applications over a network. It involves the use of protocols to encapsulate, transmit, and decode information across distances, enabling the sharing of resources and services among connected devices. This concept network-architecture builds on the foundational principles of computer networking and extends itself into various layers, from the physical network cables to the applications running on endpoints, as outlined by the TCP/IP model or the OSI model.

## How it Works
Network communication relies on a layered architecture known as the network stack, which operates through specific protocols designed to handle various aspects of data transmission and reception. The TCP/IP model, which is essential in modern network communication, comprises four layers: the physical layer, the internet layer, the transport layer, and the application layer. Each layer in the stack is responsible for certain functions and implements specific protocols to ensure efficient and reliable communication.

### Physical Layer & Data Link Layer
The physical layer deals with the physical means of sending and receiving data, such as electrical signals, radio waves, or light pulses. The data link layer is responsible for the reliable transfer of data from one node to another. It handles hardware addressing, such as MAC addresses, and ensures that data is sent without errors. Specific protocols within this layer include Ethernet and Wi-Fi.

### Network Layer
The network layer, also known as the internet layer, manages the transfer of data between different nodes in a network. It uses IP addresses to route data across different networks, ensuring that packets of data are delivered to the correct destination. Functions within this layer include IP (Internet Protocol), which is responsible for delivering data packets between hosts, and ICMP (Internet Control Message Protocol), which is used for error reporting messages and network status queries.

### Transport Layer
The transport layer ensures that data is sent from the source to the destination accurately and without corruption. It can either establish a connection-oriented session using TCP or a connectionless session using UDP:

- TCP (Transmission Control Protocol) provides a reliable, ordered, error-checked delivery of data. It is a protocol that builds on the concept of a "stream," where data is composed into a continuous flow from a sender to a recipient. Before any data is transmitted over TCP, a connection must be established, known as the "three-way handshake." Following the exchange of data, the connection is terminated through a "four-way handshake." TCP includes mechanisms like sequence numbers and acknowledgment numbers to ensure reliable delivery and windowing to moderate data flow and support traffic pacing.
- UDP (User Datagram Protocol) sends packets over the network with no acknowledgments, so packet loss and corruption must be handled at higher layers. This protocol is faster, making it suitable for applications like video conferencing and online gaming where efficiency is more important than reliability.

### Application Layer
The application layer is where network applications run. It provides users with services and interfaces to access information from remote machines. Examples of application-layer protocols include HTTP (HyperText Transfer Protocol) for web browsing, HTTPS (secure version of HTTP) for secure communication, FTP (File Transfer Protocol) for transferring files, and SMTP (Simple Mail Transfer Protocol) for sending emails. These protocols are fundamental for web applications and networked services, implementing the various capabilities needed for communication beyond the basic movement of data packets.

## Variants
Network communication can be implemented in numerous ways depending on the application and environment. For instance, the choice between TCP and UDP depends on whether a reliable channel or faster delivery is preferred. Similarly, the selection of the transport mechanism (such as TCP/IP over Ethernet) might vary based on requirements, like long-distance WAN (Wide Area Network) communications versus short-range, high-speed LAN (Local Area Network) setups. Protocols like ICMP and ARP (Address Resolution Protocol) further extend the functionalities of the network layer, adding capabilities like error reporting and address resolution, respectively.

## Trade-offs
In implementing network communication, there are several trade-offs and considerations that must be made. For example, adopting TCP for data transfer introduces complexities such as sequence numbering, retransmission of lost packets, and congestion control. These features ensure data integrity but introduce latency and resource consumption. Conversely, UDP, while more straightforward and faster, lacks the reliability and security features that TCP offers, making it less suitable for applications where data integrity is critical. Additionally, network communication protocols like TLS (Transport Layer Security) depend on complex cryptographic operations, which can be computationally expensive, impacting performance but enhancing security. The implementation of these protocols [[cybersecurity]] depends on the balance between security needs and efficiency requirements.

## See also
tcp-ip-model
osi-model