---
concept: udp
entity_type: concept
aliases: []
sources: ["raw\\09-cybersecurity\\cybersecurity.md"]
confidence: high
created_at: 2026-06-24T07:59:06Z
---

## Definition
UDP (User Datagram Protocol) is a connection-less network-protocol that provides an unreliable, connectionless datagram service over ip-addresses. Unlike tcp which ensures reliable data transmission, UDP does not guarantee delivery, ordering, or error checking of packets. UDP is a lighter and faster alternative to TCP because it does not maintain a state or acknowledges received packets, which makes it the preferred protocol for applications that require speed and do not need guaranteed packet delivery.

## How it works
UDP operates at the transport layer of the tcp-ip-4-layer-model and uses port numbers to identify specific applications or services on a device. When a UDP packet is sent, it is encapsulated into a ip datagram and forwarded to the destination IP address. The IP datagram is then carried over the network, potentially traversing multiple network devices until it reaches the destination. Upon receiving a UDP datagram, the receiving application checks the port number and processes the payload.

Compared to TCP, UDP does not initiate a connection with a three-way handshake or handle out-of-order packets and lost packets through retransmission or flow control mechanisms. As a result, UDP is faster and more efficient for real-time applications where speed is more critical than reliability, such as online gaming, media streaming, and VoIP services.

## Variants
There are no variants of UDP that significantly diverge from its core functionality. However, the User Datagram Protocol can be extended or optimized for specific applications. For instance, reliable UDP (RUDP) introduces mechanisms for retransmission, acknowledgement, and flow control that mimic TCP's behavior while maintaining some of UDP's low latency benefits. RUDP is often used in applications where data integrity and reliability are paramount, but the overhead of TCP is too high.

## Trade-offs
The primary trade-off with UDP is between speed and reliability. Since UDP does not implement any error-checking or retransmission mechanisms, it cannot guarantee that all data packets will be delivered correctly and in the proper order. This can lead to issues such as packet loss or out-of-order packets, which are critical for applications that require timely and reliable data transmission like financial transactions or file transfers. Conversely, UDP's lack of connection setup and overhead promotion allows it to deliver data quickly, making it highly suitable for real-time applications where speed is essential, such as online gaming or live video streaming.

UDP also does not include congestion control mechanisms found in TCP, which can result in network congestion if not managed properly. Applications using UDP need external mechanisms for congestion control to avoid overwhelming the network or causing network instability.

## See also