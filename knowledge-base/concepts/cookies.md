---
concept: cookies
entity_type: concept
aliases: []
sources: ["raw\\05-fullstack-integration\\fullstack_integration.md"]
confidence: high
created_at: 2026-06-24T07:57:32Z
---

## Definition
Cookies are small pieces of data, usually stored as text, used by websites to remember information about a user’s visit. They are sent to the user’s web browser by the server and can be used to identify the user across different pages, sessions, or even visits, cookie-and-browser-sessions, which means they are persistent and session-based. The use of cookies extends beyond basic tracking and can include authentication, preferences, or tracking across websites with the use of third-party cookies.

## How it works
Cookies operate primarily by allowing a server to deliver a text file containing data to a client's browser. When a user visits a site that requires a cookie, the server creates this text file, which contains a unique identifier and possibly other relevant data. This cookie is then stored locally on the user's machine. When the user returns to the website, the server reads the cookie and uses the information stored within to identify them, restore their session, or recall preferences.

The technical process of setting and receiving cookies involves HTTP headers. When a server wants to set or modify a cookie, it includes a `Set-Cookie` header in its response that includes the cookie data as well as some metadata such as expiration date, domain, and path. The browser stores this cookie and sends it back to the server with each request to the server using the `Cookies` header in HTTP requests, cookies-and-samesite-policies which enables the server to read the stored data.

Cookies build on the concept of HTTP headers to provide the means for servers to retain information about interactions between users and the server, bypassing the stateless nature of HTTP. They are essential in maintaining application state such as authentication and user preferences across browser sessions, which is critical for websites that need to recognize returning users and provide personalized content.

Cookies depend on the `SameSite` attribute to prevent cross-site request forgery (CSRF) attacks, which can lead to security vulnerabilities. The `SameSite` attribute, when set to `Strict` or `Lax`, ensures that cookies are not sent in cross-site contexts, reducing the risk of CSRF. Conversely, for third-party cookies to function, they need to relax the `SameSite` restrictions, which has led to privacy concerns and restrictions in modern browsers.

Cookies and JWT (JSON Web Tokens) often trade off when it comes to authentication mechanisms. While cookies are simpler to implement and maintain session state over long periods, JWTs offer more secure and stateless session management that can be easily shared across multiple domains or services. Both are critical in the context of identity verification and authorization, ensuring secure access control across web applications. For example, in systems that utilize front-end frameworks like React in combination with back-end technologies like Go, cookies are frequently used for storing JWTs after user authentication jwt-authentication. The front-end confirms the user's identity by including the stored JWT in HTTP requests to the back-end, enabling seamless session management.

## Variants
Cookies come in several variants including session cookies, which are temporary and destroyed when the user's browsing session ends, and persistent cookies, which remain on a computer for a pre-defined length of time. Session cookies do not require the `Expires` or `Max-Age` directive for defining their duration, and are instead bound to the life span of the browser session. Persistent cookies, on the other hand, have an expiry date and continue to send data to the server until they reach this date.

There are also first-party and third-party cookies based on whether the website setting the cookie is the same as the website being visited by the user (first-party) or a different website (third-party). First-party cookies are essential for user identification and session management, while third-party cookies allow advertisers and external websites to track user behavior across different sites, raising significant privacy concerns.

Cookies can also be secured or not, depending on whether they are sent over HTTPS. Secure cookies, unlike non-secure, can only be sent over HTTPS, preventing man-in-the-middle attacks, making them safer for transmitting sensitive information.

The implementation of cookies can vary and depends on the complexity of the use cases, with some applications requiring more sophisticated session handling mechanisms, like JWT jwt-cookies-variant.

## Trade-offs
Cookies face several trade-offs, including security, privacy, and performance issues. The main concern with cookies is their reliance on client-side storage which can lead to vulnerabilities like session hijacking and cross-site scripting (XSS) attacks. Additionally, the increasing restrictions on third-party cookies due to heightened privacy concerns can affect the overall tracking and behavioral advertising efforts of websites.

A common trade-off between cookies and other session management techniques like JWT involves state vs. statelessness. Cookies, being session-based, can cause scalability issues in large-scale applications where maintaining state across multiple servers is required. JWTs offer stateless session management by storing all necessary information within the token itself, thus reducing the server burden.

Another trade-off is visibility and the impact on user privacy. Standard cookies, being visible to users and possibly stored in plaintext (if not encrypted), offer less privacy than the secure storage of JWTs, where tokens are encrypted and less prone to leaking sensitive data.

Cookies vs. LocalStorage also illustrates these trade-offs in terms of content and expiration. Cookies have a limited size of 4KB, whereas LocalStorage can store much more data but is limited to websites and applications that can manage data persistence in a browser with JavaScript controls.

## See also
- cookie-and-browser-sessions
- cookies-and-samesite-policies
- jwt-cookies-variant
- jwt-authentication