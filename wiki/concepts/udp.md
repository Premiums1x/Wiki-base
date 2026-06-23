---
concept: udp
entity_type: technique
aliases: []
sources: ["raw/cybersecurity.md"]
confidence: high
created_at: 2026-06-23T03:37:35Z
---

## Definition

UDP, or User Datagram Protocol, is a transport layer communication protocol used for sending messages, called datagrams, between computers on a network. Unlike TCP, UDP is connectionless, meaning it does not require a connection to be established before data is sent. UDP is considered unreliable because it does not guarantee the delivery of datagrams or the order in which they are received.

## How it Works

UDP operates as a best-effort delivery protocol. When a sender application wants to send data over UDP, it places the data in a datagram, which includes the destination IP address and port number. The datagram is then sent directly to the destination network interface without first establishing a connection. 

On the receiving end, the operating system's protocol stack decapsulates the datagram and delivers its payload to the appropriate application. The lack of connection means there are no handshakes or checks for packet loss or reordering. This makes UDP faster and less complex than TCP but also less reliable.

## Variants

UDP has several variants and implementations that add specific features or optimizations:

- **Datagram Congestion Control Protocol (DCCP):** Balances some aspects of both TCP and UDP. DCCP introduces congestion control similar to TCP but with the stateless nature of UDP.
- **Multipath UDP (MP-UDP):** Extensions to UDP that allow data to be sent over multiple paths between endpoints, improving reliability and performance.
- **Lite UDP (Lite-UDP):** Designed for constrained environments where the overhead of UDP needs to be minimized further.

## Trade-offs

UDP offers speed and simplicity at the cost of reliability:

- **Speed vs Reliability:** UDP's simplicity in not establishing a connection or managing flow control allows for very fast data transfer, making it suitable for real-time applications like VoIP or online gaming. However, this trade-off means it does not ensure that every datagram will be received or that they will be received in the order they were sent.
- **Statelessness:** The stateless nature of UDP reduces the complexity but also means there is no inherent error recovery or congestion control. Implementations that require reliability must provide these features at the application level.
- **Firewall Considerations:** Because UDP does not establish a predefined connection, certain types of network traffic and firewall configurations may block or selectively throttle UDP traffic.

## See also

TCP, Transmission Control Protocol, Network Layer, Datagram Congestion Control Protocol (DCCP), Multipath UDP (MP-UDP)