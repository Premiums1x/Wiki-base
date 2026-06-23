---
concept: cybersecurity
entity_type: concept
aliases: []
sources: ["raw\\cybersecurity.md"]
confidence: high
created_at: 2026-06-23T04:12:03Z
---

## Definition
Cybersecurity is the practice of protecting internet-connected systems, including hardware, software, and data, from digital attacks, damage, or unauthorized access. It builds on network-theory to develop methods and processes that ensure the confidentiality, integrity, and availability of information resources on the internet.

## How it works
Cybersecurity works through a combination of technologies, processes, and practices designed to defend against a wide range of threats. These threats include identity theft, surveillance, fraud, and any misuse of information systems. It extends data-security principles, which focus on protecting the data itself, by incorporating additional layers such as network security to safeguard the pathways through which data travels and application security to address vulnerabilities in software applications themselves. The infrastructure of internet-connected systems relies on the TCP/IP model, which facilitates data communication over the internet. This model comprises four layers: the physical layer & data link layer, network layer, transport layer, and application layer. Each layer plays a crucial role, with the transport layer and its protocols, such as TCP and UDP, being particularly significant for cybersecurity. TCP, a connection-oriented protocol, ensures reliable data transmission through mechanisms including three-way handshakes to establish connections and four-way handshakes to close them, while UDP, a connectionless protocol, prioritizes speed, frequently used in real-time applications like video streaming and online gaming.

## Variants
Cybersecurity comprises many variants, each tailored to different types of threats and contexts. For web-applications, common threats include Cross-Site Scripting (XSS), Cross-Site Request Forgery (CSRF), and SQL injection attacks. XSS occurs when an attacker injects malicious scripts into web pages viewed by other users. This can be mitigated by escaping user inputs and enabling Content Security Policies (CSP). CSRF targets authenticated users, tricking them into performing unintended actions on websites they access while logged in, and can be defended against using CSRF tokens and configuring cookies with the SameSite directive. SQL injection represents a serious risk where unsanitized user inputs might alter database queries, compromising data integrity or even accessing confidential information. These variants build on or implement specific [[web-security]] standards and best practices to protect information integrity and confidentiality. Another variant is the use of cryptographic techniques, which include symmetric encryption, where the same key is used for both encryption and decryption, and asymmetric encryption, which employs a pair of keys—one public and one private. HTTPS, a protocol that integrates HTTP with SSL/TLS for secure data exchange, utilizes these encryption methods to ensure data integrity during transmission.

## Trade-offs
Cybersecurity involves various trade-offs, particularly between security and usability. For instance, implementing strict authentication measures can enhance security but might also complicate user workflows. Ensuring the confidentiality of data through encryption can slow down data transfer rates, impacting application performance. This trade-off scenario is a critical aspect when balancing data-availability and security measures, as overly stringent security protocols can hinder the seamless flow and accessibility of information. Furthermore, cybersecurity measures often require updates and patch management, which can introduce vulnerabilities if not managed properly. There is also a trade-off when deploying cybersecurity solutions at different layers of the network infrastructure. Strengthening certain layers might expose weaknesses in others. Therefore, a comprehensive approach that balances these trade-offs is necessary to ensure effective cybersecurity.

## See also
- network-theory
- data-security
- web-applications