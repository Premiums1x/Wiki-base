---
concept: tls
entity_type: technique
aliases: ["https"]
sources: ["raw/cybersecurity.md"]
confidence: high
created_at: 2026-06-23T03:38:09Z
---

## Definition

Transport Layer Security (TLS) is a cryptographic protocol designed to provide communications security over a computer network. Developed as an upgrade to the Secure Sockets Layer (SSL), it is widely used to secure internet communications and ensure that data transmitted between applications or devices remains private and untampered.

## How it works

### TLS Handshake Process

1. **Client Hello**: The client sends a "Client Hello" message to the server, indicating the highest version of TLS it supports, a list of cipher suites (the algorithms for key exchange, encryption, and message authentication), and a random number. This random number is used to uniquely identify the session.
2. **Server Hello**: The server responds with its own "Server Hello" message, acknowledging the client's details and selecting the highest version of TLS and a cipher suite that it can support. It also provides another random number.
3. **Certificate Exchange**: The server sends its digital certificate to the client. This certificate includes the public key, which the client will use to encrypt the session's secret key.
4. **Server Hello Done**: The server sends a message indicating that it has finished sending its parameters.
5. **Client Key Exchange and Change Cipher Spec**: The client generates a random number, the "pre-master secret," encrypts it with the server's public key from the certificate, and sends it to the server. The client also sends two "Change Cipher Spec" messages, indicating a switch to the chosen cipher suite and starting the secure communication.
6. **Client Finish**: The client sends a "Finish" message. It combines the pre-master secret, the server and client randoms, and the server's certificate to compute the master secret. The server does the same calculation and responds with its "Finish" message encrypted using the new keys.
7. **Start of Encrypted Session**: With all handshake messages complete and the Master secret computed, the client and server can now start sending encrypted data using the agreed-upon cipher suite.

## Variants
### SSL vs. TLS
SSL (Secure Sockets Layer) was the predecessor to TLS and is considered less secure. Versions of SSL (1.0, 2.0, and 3.0) have various vulnerabilities, making TLS the standard for secure web communication.

### TLS 1.0, TLS 1.1, TLS 1.2, TLS 1.3
- **TLS 1.0**: Introduced by Netscape in 1999 and significantly different from its SSL predecessor.
- **TLS 1.1, 1.2, 1.3**: Focuses on further improving security and performance. TLS 1.1 and 1.2 resolve many of the cryptographic weaknesses found in TLS 1.0, and TLS 1.3 simplifies the protocol and removes some of the older ciphers, making it faster and more secure.

## Trade-offs
### Security vs. Performance
- **Security**: TLS 1.3, for example, uses more robust cryptographic techniques and streamlined handshake procedures, which enhance security.
- **Performance**: While TLS 1.3 arguably improves performance through quicker handshakes and the removal of some aged algorithms, it requires both the client and the server to support it, which might not always be the case. TLS can have some overhead on network communication.

### Compatibility Issues
- **Compatibility**: Older and less modern software or devices might not support the latest versions of TLS, affecting interoperability.

### Complexity
- **Maintenance**: Updating to newer TLS versions requires configuration updates, certificate management, and ensuring endpoint and server compatibility.

## See also
Symmetric Encryption, Asymmetric Encryption, HTTPS,
SSL