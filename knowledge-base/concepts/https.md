---
concept: https
entity_type: concept
aliases: []
sources: ["raw\\09-cybersecurity\\cybersecurity.md"]
confidence: high
created_at: 2026-06-24T09:44:46Z
---

## Definition
HTTPS (HyperText Transfer Protocol Secure) is a protocol that extends the http protocol by adding a layer of ssl-tls for secure communication over a network. This ensures that the data exchanged over the web is encrypted and secure from unauthorized access or eavesdropping. The protocol is critical for protecting user data such as passwords, payment information, and personal details online.

## How it works
HTTPS works by implementing SSL/TLS over HTTP, providing a secure connection between the client (usually a web browser) and the web server. This process involves several steps to establish a secure connection:

1. **Client Connects to Server**: The client initiates a connection to the server via a URL starting with "https".
2. **Server Sends SSL/TLS Certificate**: Upon receiving the request, the server sends its SSL/TLS certificate to the client. This certificate is signed by a trusted certificate certificate-authority, ensuring the server's authenticity.
3. **Client Verifies the Certificate**: The client checks the certificate to confirm the server's identity and that it is valid and issued by a trusted certificate authority.
4. **Key Exchange**: If the certificate is verified, the client and server exchange encryption keys using a process known as key exchange. This exchange is facilitated through cryptographic algorithms that ensure the secrecy of the keys.
5. **Session Establishment**: Once the keys are safely exchanged, a secure session is established, and data transmission can begin. The server and client encrypt all communications using symmetric [[symmetric-encryption]] keys, which are secure and fast for data transfer.
6. **Data Transmission**: The client and server communicate securely using SSL/TLS, encrypting all data sent through the connection using the established symmetric encryption keys.

This protocol ensures that data remains confidential and is not intercepted by unauthorized users during transmission. Furthermore, HTTPS supports additional features such as HTTP Strict Transport Security (HSTS), which forces browsers to communicate only over HTTPS, and Content Security Policy (CSP), which helps prevent XSS attacks by specifically allowing or disallowing script execution based on security contexts.

## Variants
While HTTPS remains the standard secure protocol for web communications, there are evolving security practices and features that enhance its implementation:

- **HTTP/2 and HTTP/3**: These newer versions of HTTP can also be secured using HTTPS, improving performance and security through new encryption algorithms and multiplexing techniques.
- **HSTS (HTTP Strict Transport Security)**: This mechanism ensures that a web application is always accessed securely by communicating only over HTTPS, adding an additional layer of security.
- **QUIC (Quick UDP Internet Connections)**: QUIC is a transport layer protocol that builds on HTTPS, offering faster and more secure connections by combining TCP and SSL/TLS functionalities into a single protocol. QUIC improves on the latency and reconnection times within HTTPS/SSL.
- **Forward Secrecy**: This technique, also known as Perfect Forward Secrecy (PFS), ensures that even if a single session is compromised in the future, past sessions remain safe because new keys are generated for each session. It is an implementation that optimizes the security of communication sessions.

## Trade-offs
Implementing HTTPS requires balancing between performance and security.

- **Performance Overhead**: HTTPS can introduce additional latency due to the need for SSL/TLS handshakes and asymmetric and symmetric encryption. This extra computation can be resource-intensive, especially on resource-constrained devices or during peak times.
- **Security vs. Performance**: While secure, HTTPS can be less efficient compared to standard HTTP due to the overhead of cryptography. Implementation can improve performance through techniques like session resumption, which allows quick re-establishment of secure connections using established keys.
- **Complexity and Maintenance**: Implementing and maintaining HTTPS can be complex and costly, requiring regular updates to certificate security and key management. This also includes dealing with certificate authority validation and renewals.

## See also
- network-protocols
- tcp
- ssl-tls
- http