---
concept: tls-ssl
entity_type: concept
aliases: []
sources: ["raw\\cybersecurity.md"]
confidence: high
created_at: 2026-06-23T04:12:12Z
---

## Definition
TLS (Transport Layer Security) and SSL (Secure Sockets Layer) are cryptographic protocols designed to provide secure communication over a computer network. These protocols establish an encrypted link between a server and a client, ensuring data integrity, confidentiality, and privacy. SSL was initially developed by Netscape and extended further to become TLS, which wikilink-ssl-tls-improvement improves upon SSL by fixing several security vulnerabilities and incorporating more advanced cryptographic algorithms. Both TLS and SSL use a combination of public-key and symmetric-key encryption to secure data exchanged over the internet.

## How it works
The TLS and SSL protocols operate in two main phases: the handshake phase and the application data exchange phase. 

### Handshake Phase
During the handshake phase, the client and server negotiate the cryptographic parameters they will use for the session. This involves the following steps:
1. **Client Hello**: The client initiates a connection by sending a "client hello" message, including its supported TLS/SSL versions and cipher suites.
2. **Server Hello**: The server responds with a "server hello" message, selecting one of the supported versions and cipher suites from the client's list.
3. **Server Certificate**: The server sends its digital certificate (usually an wikilink-x509-certificate), which contains its public key and is issued by a trusted wikilink-certificate-authority. This certificate verifies the server's identity to the client.
4. **Server Key Exchange**: For non-wikilink-dh-key-exchange methods, the server sends a key exchange message that includes a public key.
5. **Client Key Exchange**: The client generates a wikilink-premaster-secret, encrypts it with the server's public key from the certificate, and sends it to the server.
6. **Change Cipher Spec**: Both client and server signal to each other that subsequent messages should be encrypted using the agreed-upon parameters.
7. **Finished Messages**: Both parties exchange encrypted "finished" messages to confirm that the handshake has been completed successfully.

### Application Data Exchange
Once the handshake is completed, the client and server communicate using the established secure channel. All data exchanged during this phase is encrypted and ensures that only the intended endpoints can understand the communicated data.

## Variants
TLS has gone through several updates, evolving from TLS 1.0 to the current standard TLS 1.3, each improving over the previous versions:
- **TLS 1.0**: Introduced in 1999, based on SSL 3.0.
- **TLS 1.1**: Introduced in 2006, improved the wikilink-cbc-padding-attack vulnerability present in TLS 1.0.
- **TLS 1.2**: Introduced in 2008, added support for newer cryptographic algorithms and extended the handshake protocol for better security.
- **TLS 1.3**: Introduced in 2018, focused on performance improvements by reducing latency and enhancing security, especially by removing the concept of wikilink-cbc-cipher modes.

SSL has also seen updates but has largely been deprecated and replaced by TLS:
- **SSL 2.0**: First released in 1995, quickly deprecated due to security flaws.
- **SSL 3.0**: Introduced in 1996, served as the basis for TLS 1.0 but was officially deprecated in 2015 due to the well-known POODLE attack.

## Trade-offs
While TLS/SSL provide robust security measures, they also introduce trade-offs:
- **Performance Overhead**: The encryption and decryption processes involved in TLS/SSL impose a performance cost, especially on older or less powerful systems.
- **Compatibility**: Ensuring that all client and server software supports the latest TLS versions can be challenging, potentially limiting widespread adoption.
- **Complexity**: Implementing and maintaining TLS/SSL properly requires understanding complex cryptographic and networking concepts.

## See also
wikilink-x509-certificate, wikilink-certificate-authority, wikilink-dh-key-exchange, wikilink-cbc-padding-attack, wikilink-cbc-cipher, wikilink-premaster-secret