---
concept: tcp-ip
entity_type: technique
aliases: ["tcp"]
sources: ["raw/cybersecurity.md"]
confidence: high
created_at: 2026-06-23T03:37:25Z
---

## Definition
TCP/IP (Transmission Control Protocol/Internet Protocol) is a suite of communication protocols used to interconnect network devices on the Internet. The TCP/IP model, also known as the Internet Protocol Suite, is a four-layer conceptual model that describes how data is transmitted across the internet.

## How it works
TCP/IP operates over four layers, each with a specific task in data communication:

1. **Link Layer** (or Data Link Layer):
   - This layer deals with the physical addressing, using MAC addresses for communication on a local network segment.
   - Protocol: Ethernet, Wi-Fi

2. **Internet Layer**:
   - The main protocol at this layer is IP (Internet Protocol). It handles the addressing and routing of packets between network devices.
   - Protocol: IPv4, IPv6
   
3. **Transport Layer**:
   - This layer is responsible for ensuring reliable data transfer from one host to another. It has two primary protocols:
     - **TCP (Transmission Control Protocol)**: A connection-oriented protocol that guarantees data delivery and manages the flow control and error recovery.
     - **UDP (User Datagram Protocol)**: A connectionless protocol that provides simpler, faster, but potentially unreliable data delivery.

4. **Application Layer**:
   - This layer supports end-user applications with protocols like HTTP, FTP, SMTP, and others that facilitate specific network services.

Data travels from the higher layer (Application Layer) to the lower layers (transport, internet, and link), with each layer adding its necessary information (packets, frames, etc.) before the data is transmitted. Conversely, data is processed from the transport layer up to the application layer to be used by the application.

## Variants
Several variants and implementations of the TCP/IP model exist, such as:

- **IPv4 vs. IPv6**: IPv6 is the successor to IPv4, offering a larger address space and improved security features.
- **Multiprotocol Label Switching (MPLS)**: An additional layer that sits between the link layer and network layer; it forwards data based on shorter, fixed-length labels.
- **Transport Layer Security (TLS)**: Used on top of TCP to provide secure and encrypted communications between applications on the internet.

## Trade-offs
Key trade-offs associated with TCP/IP include:

- **Latency**: TCP generally introduces more latency than UDP due to its overhead in maintaining connections and ensuring data reliability.
- **Congestion Control**: While TCP incorporates mechanisms to manage network congestion, these can sometimes lead to suboptimal performance scenarios.
- **Address Exhaustion**: IPv4's limited address space can become exhausted in areas with high network density, necessitating the adoption of IPv6.

## See also
[[cybersecurity]], Network Protocols, TCP, UDP, IPv4, IPv6, Application Layer, Transport Layer, Internet Layer, Link Layer