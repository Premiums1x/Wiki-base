---
concept: osi-model
entity_type: concept
aliases: []
sources: ["raw\\09-cybersecurity\\cybersecurity.md"]
confidence: high
created_at: 2026-06-24T09:44:24Z
---

## Definition
The OSI (Open Systems Interconnection) Model is a conceptual framework that divides network communication into seven distinct layers, each with specific functions and responsibilities. It is designed to standardize the processes involved in transmitting information across a network, ensuring interoperability between different systems. It builds on the fundamentals of network protocols and is widely adopted in the design, development, and management of network systems.

## How it works
The OSI model organizes the functions of a telecommunication or computing system into seven distinct layers, from the physical network layer through to the application layer. Each layer interacts only with the layer directly above and below it, adhering to the principle known as peer-to-peer communication. This isolation facilitates troubleshooting and allows the development of a diverse range of technology within a single layer without affecting devices in the other layers. A message travels through these layers in a host device from the top layer towards the physical layer (the downward direction), and when it reaches the destination host, it travels from the physical layer back up to the top layer (the upward direction).

### Layer Breakdown
1. **Physical Layer**: Defines the physical and electrical specifications for sending data, including bits over physical means, such as twisted wire pairs, coaxial cable, optical fiber, or wireless transmission media.
2. **Data Link Layer**: Manages the transfer of data across a physical link and detects and corrects errors that occur at the physical layer. It uses hardware addresses such as mac-address, also known as physical addresses.
3. **Network Layer**: Controls the operation of the network, including aspects such as path determination and traffic switching between networks, which is dependent on the ip-address to identify and locate devices.
4. **Transport Layer**: Provides reliable data transfer services using protocols such as TCP (Transmit Control Protocol) and UDP (User Datagram Protocol). TCP guarantees reliable and ordered delivery of data, while UDP is optimized for applications where speed is more critical than reliability.
5. **Session Layer**: Establishes, manages, and terminates sessions between applications. It also defines several communication session services such as dialogue control, token management, and synchronization.
6. **Presentation Layer**: This layer is responsible for representing information in a form that can be accepted by both the sender and receiver. This includes encryption, decryption, and translation mechanisms for data representation.
7. **Application Layer**: Provides services to software applications for user data transactions. Protocols such as HTTP, dns, and ssh are found at this layer.

## Variants
While the OSI model is the theoretical framework, it is often abstracted when implementing network systems due to its complexity compared to real-world scenarios. The TCP/IP model, which extends the principles but simplifies them to four layers, is widely used in industry for practical application. This includes the combination of OSI's Network and Transport layers into the Internet layer and Transport layer in TCP/IP, respectively.

## Trade-offs
The OSI model, while ideal for academic and theoretical understanding, can be overly detailed for practical implementation purposes. It is thus at the cost of simplicity and efficiency in real deployment scenarios. Implementing the full OSI model requires an increased level of technical precision and oversight, which can be challenging in large-scale distributed systems. Conversely, models like TCP/IP, which integrates some of these layers together, are more straightforward for developers and network administrators, offering a faster development and deployment cycle.

## See also
- mac-address: Depends on for hardware addressing and error detection in the Data Link Layer.
- ip-address: Prerequisite of for traffic switching and routing in the Network Layer.
- tcp-udp-protocol: Implements the principles of the Transport Layer, ensuring reliable delivery and prioritization in different application scenarios.
- dns: Optimizes domain name resolution by mapping human-readable domain names to ip-address|IP addresses, implementing Application Layer functionality.
- ssh: Provides secure shell access to remote devices, implementing Application Layer functionality for secure and encrypted communication.