---
concept: json-web-token
entity_type: concept
aliases: ["JWT"]
sources: ["raw\\05-fullstack-integration\\fullstack_integration.md"]
confidence: high
created_at: 2026-06-24T07:57:20Z
---

## Definition
A Json Web Token (JWT) is a compact, URL-safe method for transmitting information between parties as a JSON object. JWTs are usually used for secure information exchange between browser and server. They consist of three parts: Header, Payload, and Signature. The Header typically contains metadata about the token, such as the type of token and the hashing algorithm being used; the Payload generally contains claims, which are statements about a user; and the Signature is used to ensure that the data sent could not be modified or used by another entity.

## How it works
JWTs work by encoding a set of claims into a token that is securely signed using a secret key or a public-private key pair. When a user logs in, the following process is initiated:
- **Login Process**: The client sends a request to the server with credentials (typically, a username and password). If the credentials are valid, the server generates a JWT and returns it to the client.
- **Storage**: The frontend receives this JWT and stores it temporarily, usually in local storage or in a cookie.
- **Authorization**: In subsequent requests, this token is included in the HTTP Authorization header, specifically with the "Bearer" keyword preceding the token value. The server uses this token to authenticate each request.
- **Verification**: With each received request, the server verifies the JWT’s signature and timestamp to ensure that the request is coming from a trusted source and that the token is still considered valid. If the token is deemed invalid, access to the resource is denied by returning a `401 Unauthorized` response.

The verification step requires decoding the token, inspecting its signature based on the signing algorithm specified in the header, and comparing the serialized token against a trusted copy. At this point, it uses the stored secret key or the private key of the key pair that created the token for verification, ensuring that the token has not been tampered with.

JWTs can be signed using several algorithms, including HS256 (HMAC SHA-256) for secrets and RS256 (RSA SHA-256) for asymmetric key pairs. These http-protocol signatures underpin the reliability of JWTs as a secure method of transmitting data.

## Variants
- **At-Header JWTs** ([at-header-jwts]) add an additional level of complexity by integrating the JWT directly within the Authorization header of an HTTP request, extending the JWT system's functionality to enhance security and user session management.
- **JWTs with Refresh Tokens** implement an additional mechanism for token renewal, where a refresh token is provided to the client in addition to the JWT. This refresh token is used to obtain new JWTs without requiring the user to log in again, improving the user experience by reducing the number of required logins.
- **JWT Blacklisting**: In this mechanism, a list of invalid or compromised tokens is maintained, and any request containing a token on this list is rejected. This variant builds on the JWT system by adding an additional layer of security to combat token theft.

## Trade-offs
The trade-off with JWTs is primarily the balance between security and performance. JWTs can be gzipped or base64 encoded to reduce their size, and signing them is reasonably fast; however, verifying a large number of tokens quickly can become a performance bottleneck for heavily loaded web servers. Additionally, if the token is compromised, all issued tokens must be invalidated, as they can be used repeatedly until their expiration, even if they are not actually on the server. This method relies on the fact that the token serves as a short-lived, high value passkey and, cookies and local-storage vulnerabilities must be mitigated to prevent these tokens from being exposed. Moreover, complex JWTs can contain vast amounts of data, making them less efficient for large-scale systems where data size and speed are critical.

## See also
http-protocol, cookie, local-storage