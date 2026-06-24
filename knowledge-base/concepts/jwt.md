---
concept: jwt
entity_type: concept
aliases: []
sources: ["raw\\05-fullstack-integration\\fullstack_integration.md"]
confidence: medium
created_at: 2026-06-24T07:57:04Z
---

## Definition
JSON Web Token (JWT) is an open standard (RFC 7519) for securely transmitting information between parties as a JSON object. It is typically used for authentication and information exchange purposes api-cors. JWTs are designed to support multiple signing algorithms and come in a compact, URL-safe representation. They are widely adopted due to their simplicity and effectiveness in enabling stateless authentication across different platforms.

## How it works
The JWT authentication flow is a stateless process which relies on the exchange and verification of tokens. Here is a detailed breakdown:

1. **Token Issuance**: When a user logs into an application, the backend performs an authentication check using the provided credentials. If the user is successfully validated, the backend generates a JWT which includes claims. Claims are portions of the token that carry information about the user (the subject), the issuer, the issue time, the expiration time, etc. The data is signed using a secret key known only to the issuer, and this signature prevents tampering and ensures the authenticity of the token.

2. **Storage and Retrieval**: Once generated, the JWT is sent back to the client in the response body or set in a cookie. The client then stores this token, usually in local storage or session storage, depending on the desired lifetime and security policies.

3. **Request and Verification**: On subsequent requests for authenticated endpoints, the client sends the JWT as part of the Authorization header with the scheme 'Bearer'. When the server receives such a request, it extracts and verifies the JWT to ensure that it was issued by a trusted issuer (valid signature) and has not expired.

4. **Security Claims**: A JWT must contain at least a header and a payload. The header typically specifies the type of token (JWT) and the signing algorithm used to ensure the token is not tampered with in transit. The payload is where the claims are stored.

5. **Token Refresh**: To prolong the session, an additional refresh token might be used alongside the access token. This refresh token can be used by the client to obtain a new access token once the current token expires, without needing to re-authenticate.

## Variants
While JWT is the most common method for implementing stateless authentication in web applications, there are alternatives such as session-based authentication, which the server manages. Session-based tokens require storing a unique identifier (ID) on the server side and matching it with the client-side token to verify the user. However, this approach introduces state to the application, which can complicate scaling and fault tolerance.

## Trade-offs
JWTs offer several advantages, including simplicity, statelessness, and cross-platform support. However, they also come with certain trade-offs:

1. **Token Size**: JWTs can grow to significant sizes, especially when many claims are included. This could increase the bandwidth used by applications, which is particularly problematic for mobile applications.

2. **Security Risks**: There is a risk of replay attacks if JWTs are not properly signed or if they are transmitted securely. Implementing proper security practices is critical to mitigate these risks.

3. **Statelessness**: The stateless nature of JWTs requires servers to verify the token on every request, which might add latency. In some scenarios, maintaining a stateful backend (through sessions or cookies) could offer performance benefits.

## See also
For more information on how HTTP requests can be made stateless through token-based systems, see the concept of no-state-token. The importance of handling cross-origin requests properly when implementing JWT-based authentication is further explained in the context of api-cors.