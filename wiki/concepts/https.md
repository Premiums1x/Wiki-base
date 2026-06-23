---
concept: https
entity_type: concept
aliases: []
sources: ["raw\\cybersecurity.md"]
confidence: high
created_at: 2026-06-23T04:12:18Z
---

## Definition
HTTPS stands for Hypertext Transfer Protocol Secure. It wikilink, which is an extension of the standard HTTP protocol, builds on http by adding a layer of SSL/TLS encryption to provide secure communication over a network. This ensures that the data, including web pages, images, and videos, sent between a user's browser and a web server is protected from unauthorized access, eavesdropping, or tampering.

## How it Works
The process of HTTPS, which implements the HTTP protocol, involves several key steps ensuring that a session remains secure.

1. **Connection Establishment**: When a browser attempts to connect to a web server using HTTPS, it initiates a connection using TCP on port 443 instead of the standard 80 for HTTP.

2. **TLS Handshake**: Before data exchange, a secure channel is established through a TLS handshake where the client and server negotiate a secure connection:
    - **Certificate Exchange**: The server sends its SSL/TLS certificate to the client. This certificate, signed by a Certificate Authority (CA), verifies the identity of the server and establishes trust.
    - **SSL/TLS Cryptography**: The server and client exchange cryptographic information to generate a session key. This is where HTTPS trades off computational resources for security. The server sends its public key in the certificate and the client uses this key to encrypt a random session key using the server's public key, ensuring only the server can decrypt it with its private key.

3. **Data Transfer**: Once a secure connection is established, data (HTTP requests and responses) is encrypted and transferred over the secure connection. The data transfer process uses one of several algorithms for encryption and decryption, such as AES (Advanced Encryption Standard), combining non-symmetric encryption used during the TLS handshake and symmetric encryption used in data transfer.

4. **Session Closure**: After the completion of the data transfer, the secure session is closed, typically involving the cleanup of all session keys to prevent their reuse or interception.

## Variants
HTTPS has several versions and variants, each aiming to enhance and optimize the security measures provided by the protocol. These include:
- **TLS/SSL Versions**: Different versions have introduced enhancements, performance optimizations, and addressed security vulnerabilities. TLS 1.3 is the latest major version, known for faster handshakes and security improvements.
- **Encryption Algorithms**: Besides AES, HTTPS can use other symmetric algorithms like 3DES, RC4 (now considered weak and obsolete), and asymmetric algorithms which are used in the handshake for key exchange.

## Trade-offs
The use of HTTPS, which depends on tcp, requires additional computational overhead for encrypting and decrypting data, which can affect performance and resource usage, especially in scenarios with low bandwidth or high transaction volumes. However, the trade-off is the significant enhancement in security provided, mitigating risks of data breaches and ensuring privacy and integrity of web traffic.

## See also
- cryptography
- tcp
- http
- tls