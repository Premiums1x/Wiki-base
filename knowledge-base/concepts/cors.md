---
concept: cors
entity_type: concept
aliases: []
sources: ["raw\\05-fullstack-integration\\fullstack_integration.md"]
confidence: high
created_at: 2026-06-24T07:56:49Z
---

## Definition
CORS, or Cross-Origin Resource Sharing, is a mechanism that enables many resources (e.g., fonts, JavaScript, etc.) on a web page to be requested from another domain outside the domain from which the resource originated. CORS is a solution to the problem of same-origin policy|same-origin-policy, which is a security feature implemented by web browsers to prevent web pages from making requests to a different domain than the one that served the web page.

## How it works
CORS operates by introducing new HTTP headers that provide permissions to make requests from one domain to another, using a client (usually a web browser) and a server (a web server running a backend application). The same-origin policy restricts the loading and modifying of resources from different origins than the current document's origin. However, when one site (A) wants to allow another site (B) to request resources, CORS establishes a way for site B to make requests to APIs or other resources hosted on site A.

To enable CORS, the server hosting the resource must include specific HTTP headers in its responses that indicate whether the requested resource should allow cross-origin requests, effectively opting into CORS. These headers generally include the `Access-Control-Allow-Origin` header, which specifies the origin(s) that are allowed to access the resource, and the `Access-Control-Allow-Methods` header, which indicates which HTTP methods are permitted. If the browser observes a request that comes from a different domain than the one it originally loaded, it intercepts the request to prevent malicious operations that could leak sensitive data. If the server includes the correct CORS headers, allowing the requested domain, then it allows the cross-origin request to proceed.

*   **Server-Side Setup with CORS Middleware**: In environments like Node.js (using Express) or in Go, developers need to configure CORS to enable cross-origin requests. In Node.js with Express, this involves installing the `cors` middleware and configuring it to allow specific origins or all origins (`*`). In Go, the developer can manually set the CORS headers in the HTTP response.

    ```go
    w.Header().Set("Access-Control-Allow-Origin", "http://localhost:5173")
    ```

*   **Proxy Setup with Client-Side Configuration**: To bypass the origin restrictions in development environments, developers can configure a proxy in their build tools like Vite via `vite.config.js`, allowing the client-side application to send requests transparently to a different server. This is particularly useful for local development when web services are hosted on different ports.

## Variants
- **CORS-Preflight**: CORS preflight requests are used when the client is using methods, headers, or credentials in the actual request that might not be safe from a web security perspective. The browser sends an OPTIONS request that probes the server for the required `Access-Control` headers before the actual request is made. This request allows the server to check whether the request is safe and should be allowed.

- **CORS vs. JSONP**: JSONP (JSON with Padding) is another method for allowing web pages to request data from another domain. However, it is designed for `GET` requests and relies on the server returning JSON wrapped in a specific callback, bypassing the same-origin policy. Although JSONP is older, it has its usage limitations compared to CORS because it does not support new HTTP methods like `POST`, `PUT`, and others, and does not offer the flexibility and security benefits that CORS brings.

## Trade-offs
Implementing CORS involves trade-offs, primarily the security vs. functionality balance. While CORS significantly enhances web application functionality by allowing cross-origin requests between databases and JavaScript, it can also introduce significant security risks if not properly configured. Misconfiguration of CORS can lead to undesired CORS policy violations, where an attacker could exploit the policy by injecting malicious data into the response headers. Therefore, ensuring secure configurations of CORS headers is critical to preventing security breaches. CORS also imposes certain performance overhead, as each cross-origin request requires additional HTTP headers and possibly preflight OPTIONS checks, which can increase the latency of client-server communication.

## See also
Many modern web practices and security standards depend on and interact with CORS, such as setting up HTTP request and response headers to secure data transmission and interactions between servers and clients. Understanding CORS is essential for maintaining a secure development environment, particularly when implementing measures like JWT (JSON Web Tokens) for secure communication and authentication.