---
concept: https
entity_type: concept
aliases: []
sources: ["raw\\09-cybersecurity\\cybersecurity.md"]
confidence: high
created_at: 2026-06-24T07:59:27Z
---

## Definition
HTTPS (Hypertext Transfer Protocol Secure) is a secure version of HTTP that extends HTTP by adding a security layer through SSL/TLS to ensure that data transferred between a client and a server cannot be intercepted or modified through [[cybersecurity]] techniques such as eavesdropping or man-in-the-middle attacks. This protocol is a critical component in securing web transactions and interactions, ensuring confidentiality and integrity of data in transit.

## How it works
HTTPS works by utilizing SSL/TLS, which establishes a secure connection between the client (browser) and the server. The protocol consists of two phases. First, during the handshake phase, the client and the server use asymmetric cryptography to exchange a pre-master secret. This is done by leveraging the non-symmetric-encryption algorithm, commonly RSA or ECC, to ensure that the pre-master secret, which will be used to derive the session keys, is securely shared. The client sends a client hello message containing information about the supported protocols and ciphers. The server replies with a server hello message that includes a certificate chain. This chain is a series of certificates, with the last one being the server's certificate and the one before it being an intermediary certificate that can verify the server's certificate and so on until the root certificate. The server also sends a ServerKeyExchange message if necessary to provide the client with additional parameters for key generation. Each of these exchanges is secured using a digital signature, which is a method for verifying the identity and authenticity of the sender.

After the handshake, the client verifies the server’s certificate and extracts the server’s public key. If the server's certificate is verified as valid, the client generates a PreMasterSecret and encrypts it with the server’s public key. This encrypted PreMasterSecret is then sent back to the server. The server uses its own private key to decrypt the PreMasterSecret, and both the client and server use the decrypted PreMasterSecret to calculate the session keys to be used for subsequent communication. These session keys are the actual keys used to encrypt and decrypt the data transfer between the client and the server, utilizing symmetric encryption algorithms such as AES.

The second phase involves the use of these session keys for encrypting the actual data exchanged between the client and the server, ensuring the confidentiality and integrity of the data.

## Variants
There are no variants of HTTPS in the traditional sense, but there are differing configurations and implementations. For example, the variant can refer to the specific version of SSL/TLS being used (such as TLS 1.2 or TLS 1.3). Each version has its own set of recommended algorithms and ciphersuites to ensure security. Additionally, different web servers and clients may implement HTTPS with varying configurations such as static key generation, dynamic key exchange, and selective cipher suite support.

## Trade-offs
The use of HTTPS introduces certain trade-offs. While it significantly improves security, it can also introduce latency and reduce performance, especially in environments with limited bandwidth or high load. This is largely due to the computational overhead required to perform the SSL/TLS handshake and the increased number of bytes transmitted in each message to accommodate encryption and integrity checks. The increased latency can be substantial, particularly during the initial handshake phase, which requires multiple round-trip communications between the client and the server.

HTTPS also requires additional computational resources and can scale less efficiently than non-secured HTTP due to the overhead of cryptographic operations. From a maintenance perspective, HTTPS necessitates managing certificates and keys, which can add complexity and operational costs.

## See also
[[cybersecurity]]