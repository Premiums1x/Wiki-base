---
concept: jwt
entity_type: concept
aliases: ["json-web-token"]
sources: ["raw\\fullstack_integration.md"]
confidence: high
created_at: 2026-06-23T04:13:54Z
---

## Definition
JWT stands for JSON Web Token, which is a compact and self-contained mechanism for securely transmitting information between parties as a JSON object. It is often used for stateless authentication and authorization session over HTTP. JWT consists of three parts: Header, Payload, and Signature, each separated by a dot. A client application acquires a JWT upon successful authentication, usually via a login request, and includes it in subsequent requests to the server to gain access to protected resources.

## How it works
### Header
The header typically consists of two parts: the token type (which is always 'JWT'), and the signing algorithm that was used to sign the token. The most common algorithms include HS256, a symmetric algorithm that uses HMAC, and RS256, a public-key/private-key algorithm that uses RSA.

### Payload
The payload contains claims. Claims are statements about an entity (typically, the user) and additional data. There are three types of claims: registered, public, and private claims. Registered claims are defined by JWT and should be used when possible for consistency. Some examples include `iss` (issuer), `sub` (subject), `aud` (audience), `exp` (expiration time), and `nbf` (not before time). Public claims can be defined at will, but they should be registered in a public registry, such as the IANA JSON Web Token Claims registry, to avoid conflicts. Private claims can be defined by the developers for any use not covered by registered or public claims.

### Signature
The signature is created by combining the encoded header and the encoded payload with a secret, or a private key. The HMAC (HS256) or a public/private key pair (RS256) are commonly used to verify the authenticity of the token and to ensure that the token was not tampered with. When the JWT is sent to the server, it is verified using either the same secret (in the case of HMAC) or the public key.

### Authentication with JWT
Once the user is authenticated successfully, the backend generates a JWT and returns it to the frontend. This typically involves encoding to Base64URL, combining it with the secret, and then encoding it. The client stores the token, usually in cookies or local storage, securely. On every protected route call, the client includes the JWT in the HTTP Authorization header. The server decodes the JWT, verifies its signature, and checks its expiration and other necessary claims to determine if the user is authenticated and authorized to access the resource.

## Variants
JWT can be issued and signed using different algorithms, such as HMAC (HS256), RSA (RS256), and Elliptic Curve Cryptography (ES256). Each algorithm provides a different level of security and complexity. HMAC provides the least complexity but requires a shared secret, while RSA and Elliptic Curve offer asymmetric encryption, where the secret key used to sign the token must be kept private, and the public key can be shared. This fits the model of key distribution in public/private systems, providing more security and flexibility.

## Trade-offs
The main trade-offs of using JWT include token size and security concerns. JWTs can be rather large compared to other authentication mechanisms, posing challenges for mobile applications and API call optimization. Additionally, while JWTs are more secure due to encryption, the system is vulnerable to man-in-the-middle attacks if transmitted via HTTP, which can be mitigated by using HTTPS.

JWT also depends on HTTP sessions for storing the state of authentication; however, this stateless-design to some extent optimizes the system since the server does not need to store session states, reducing the amount of necessary server-side computation and storage. This is a significant improvement over traditional sessions, but it means that any information that is required outside of the initial JWT payload has to be stored elsewhere, such as in a database.