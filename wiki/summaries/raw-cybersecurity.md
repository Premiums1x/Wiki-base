---
source: raw\cybersecurity.md
source_type: article
source_hash: sha256:1b419638b2141e8bb80098c25b5065282871f4f5055edec43e5dc37f8a244692
compiled_at: 2026-06-23T03:25:25Z
chunk_count: 1
---

## Key claims
- Cybersecurity is fundamental to protecting distributed systems, web applications, hardware, software, and data from unauthorized access and digital attacks.
- Network communication relies on standardized layered architectures (TCP/IP and OSI), where TCP ensures reliable, connection-oriented data delivery, while UDP prioritizes speed for real-time applications.
- Common web vulnerabilities (XSS, CSRF, SQL Injection) exploit client-side execution, session cookie misuse, and unsanitized database queries, respectively, and require specific technical mitigations.
- Data confidentiality, integrity, and authentication are achieved through cryptographic techniques, including symmetric/asymmetric encryption, TLS-secured HTTPS, and salted hashing.

## Methodology
- The document functions as a technical reference and educational overview. It employs a descriptive, categorical structure to explain foundational networking models, enumerate prevalent web application threats, and outline cryptographic defense mechanisms. No empirical research, experimental design, or quantitative analysis is presented.

## Results
- Effective cybersecurity requires integrating network layer awareness, input validation, and cryptographic protocols to prevent exploitation.
- HTTPS secures communications by using asymmetric encryption for initial key exchange and symmetric encryption for subsequent data transmission, mitigating eavesdropping and tampering.
- Secure password storage necessitates the use of salted hash functions (e.g., bcrypt, SHA-256) to neutralize precomputed lookup attacks.
- Defending against web threats relies on strict input sanitization (HTML escaping, CSP), request validation (CSRF tokens, `SameSite` cookies), and database parameterization to block SQL injection.

## Concepts
TCP/IP model, OSI model, Physical layer, Data link layer, Network layer, IP address, Transmission layer, TCP, UDP, Application layer, HTTP, HTTPS, DNS, SSH, OWASP Top 10, XSS, CSRF, SQL injection, CSP (Content Security Policy), SameSite attribute, Prepared statements, Symmetric encryption, Asymmetric encryption, AES, RSA, ECC, SSL/TLS, Hash function, Salt, SHA-256, bcrypt, MAC address, Packet routing, Session token, Rainbow table attack