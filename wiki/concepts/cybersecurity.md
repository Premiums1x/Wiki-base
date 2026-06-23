---
concept: cybersecurity
entity_type: concept
aliases: ["infosec"]
sources: ["raw/cybersecurity.md"]
confidence: high
created_at: 2026-06-23T03:37:21Z
---

## Definition

Cybersecurity refers to the practices, technologies, and processes designed to protect networks, devices, programs, and data from unauthorized access or criminal use and to defend against the wide range of threats that exist in cyberspace. It aims to maintain the confidentiality, integrity, and availability (CIA triad) of electronic information assets.

## How it Works

Cybersecurity operates on several layers, including network, application, and data levels, leveraging various security protocols and technologies:

### Network Security
Network security focuses on protecting the network infrastructure and maintaining the security of hardware, software, and firmware which enable networked communication. This involves using protocols like **TCP/IP** and **OSI** models to secure data transmission. Essential components include:
- **Physical Layer & Data Link Layer**: Ensures data transmission over physical media like cables or Wi-Fi using MAC addresses.
- **Network Layer (IP)**: Routes data packets across different networks using IP addresses.
- **Transport Layer (TCP/UDP)**: Ensures reliability (TCP) or fast delivery (UDP) of data across networks.
- **Application Layer**: Manages application-specific protocols such as HTTP, HTTPS, and DNS.

### Application Security
Application security involves measures to ensure the security of applications. It includes:
- **Web Security**: Protecting against threats like XSS, CSRF, and SQL Injection.
- **XSS (Cross-Site Scripting)**: Attackers inject malicious scripts into web pages to compromise the user's session. Defenses include escaping user input and using Content Security Policy (CSP).
- **CSRF (Cross-Site Request Forgery)**: Attackers trick a user into issuing malicious commands when they are authenticated. Defenses include using CSRF tokens and configuring cookies with `SameSite=Strict`.
- **SQL Injection**: Attackers insert malicious SQL into queries to manipulate databases. Defense includes using parameterized queries to escape and sanitize user input.

### Data Security
Data security focuses on protecting data from unauthorized access, use, modification, and destruction. Key elements include:
- **Encryption (Symmetric & Asymmetric)**: Symmetric encryption uses the same key for encryption and decryption, while asymmetric encryption uses a public key for encryption and a private key for decryption.
- **HTTPS (Hypertext Transfer Protocol Secure)**: Combines HTTP with SSL/TLS, ensuring secure data transmission through encryption and authentication.
- **Hashing**: Converts data of arbitrary size into fixed-size output, mainly for password storage and data integrity checks. Algorithms include SHA-256 and bcrypt.

## Variants
Variants of cybersecurity strategies and implementations include:
- **Network Security**: Utilizing firewalls, intrusion detection and prevention systems (IDS/IPS).
- **Application Security**: Development of secure coding practices, regular security audits, and penetration tests.
- **Data Security**: Implementation of encryption, hashing, and digital signatures.
- **User Education**: Training for employees on phishing awareness and safe internet practices.

## Trade-offs
Key trade-offs in cybersecurity include:
- **Cost vs. Security**: Implementing advanced security measures can be expensive but is crucial to protect against sophisticated threats.
- **Performance vs. Security**: Complex security protocols can affect network and application performance.
- **Usability vs. Security**: While increasing security, measures must ensure that the end-user experience remains smooth and easy-to-use.

## See also
TCP/IP protocols, XSS and CSRF attacks, SQL Injection, Encryption, HTTPS