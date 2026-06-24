---
concept: http
entity_type: concept
aliases: []
sources: ["raw\\09-cybersecurity\\cybersecurity.md"]
confidence: high
created_at: 2026-06-24T07:59:22Z
---

## Definition

HTTP, or Hypertext Transfer Protocol, is a fundamental network-layer-protocols specification intended for distributed, collaborative, and hypermedia information systems. It is a [[application-layer]] protocol designed to enable communication between web servers and clients. HTTP functions on top of the TCP/IP transport-layer-protocols, including TCP and UDP. The protocol defines how messages should be formatted and transmitted, and what actions web servers should take in response to various commands, such as requests (tcp-ip).

## How it works

HTTP operates on top of the tcp/ip protocols and uses the transport-layer-protocols, particularly TCP, for reliable data transmission. HTTP requests and responses are text-based messages. A standard HTTP message consists of three components: start line, headers, and body. When a client, such as a web browser, wants to access a resource from a web server over HTTP, it sends a request to the server. The server, in turn, processes the request and sends back a response back to the client.

The start line includes the request type (GET, POST, etc.) and the resource path for requests, or the status code for responses. Headers in both requests and responses provide details about the request or response, such as the user-agent, content-type, or cookies. Finally, the body, if present, holds actual resource content for requests or a server response to the request.

HTTP is designed to be stateless. This means that each request from a client to a server must contain all the necessary information to understand and process the request. The server does not store any data from previous requests; each request is treated independently. Despite this design choice, user sessions can be maintained through the use of persistent connections (HTTP/1.1) and by storing session data on the server or cookies on the client's device.

Data transmitted over HTTP is unencrypted and hence subject to man-in-the-middle-attacks and data interception. To address this cybersecurity-issues, https-protocol extends HTTP with an additional layer of security, ensuring a secure connection through SSL/TLS protocols. HTTPS encrypts all communications between the client and server, protecting data integrity and confidentiality.

## Variants
There are various versions of the HTTP protocol:
- HTTP/0.9: The initial version, which only supported GET requests and lacked response headers and body content.
- HTTP/1.0: Introduced response headers, tracking the version of the document, and fixed the issues of HTTP/0.9. It began handling multiple concurrent requests.
- HTTP/1.1: A major improvement over HTTP/1.0, eliminating the need for multiple connections by allowing pooled connections. It also introduced pipelining, allowing multiple requests to be sent on a single connection before receiving the first response.
- HTTP/2: Announced in 2015; it provides a more efficient way to handle requests, significantly reducing latency by allowing for the transmission of multiple requests on one connection simultaneously. It also supports server-side push, where a server can initiate the sending of data to the client without waiting for a request.
- HTTP/3: Announced in 2020, builds on the foundation of HTTP/2 but utilizes QUIC as the transport protocol rather than TCP. QUIC provides improved connection establishment and better performance over high-latency networks, further reducing latency and increasing reliability.

## Trade-offs
HTTP offers a simple and client-server-based communication protocol, but it has several inherent drawbacks. The stateless nature of HTTP can complicate the management of user sessions, necessitating the use of cookies or persistent connections to maintain state across requests. Furthermore, HTTP operates over TCP by default, which can introduce latency due to the three-way handshake for establishing a connection and end-to-end validation. This is particularly evident in situations where the client is on a mobile network or crossing network segments with different latency characteristics.

While basic HTTP provides a lightweight and universally supported communication method, its lack of encryption and authentication capabilities makes it vulnerable to man-in-the-middle attacks and data interception. These vulnerabilities are ameliorated through the use of HTTPS, which builds on HTTP but integrates SSL/TLS for secure data transmission. However, establishing an SSL/TLS encrypted connection incurs additional overhead, potentially increasing latency and impacting performance, especially on mobile devices or less powerful systems.

In modern times, alternative request-response protocols like HTTP/2 and HTTP/3 have been introduced to improve efficiency and performance. HTTP/2 introduces multiplexing to allow multiple requests to be handled over a single connection and supports server push, but its adoption requires support for HTTP/2 from both the client and server, which is not universal. Similarly, HTTP/3 leverages QUIC, which offers lower latency and improved performance over higher-latency networks, but support is still limited, as QUIC is a relatively new technology.

## See also
tcp-ip
transport-layer-protocols
https-protocol