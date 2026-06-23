---
concept: cors
entity_type: concept
aliases: []
sources: ["raw\\fullstack_integration.md"]
confidence: high
created_at: 2026-06-23T04:13:52Z
---

## Definition
Cors (Cross-Origin Resource Sharing) is a protocol that allows a server to specify any origin from which a browser should permit making requests. It extends the [[same-origin-policy]] to enable secure cross-origin requests.

## How it works
Cors operates through the exchange of HTTP headers between the client and server. When initiating an AJAX request from the web page served from one origin, the browser automatically adds an `Origin` header to the request. If the server indicates that requests from the specified origin are allowed (by including the `Access-Control-Allow-Origin` header in the response), the browser permits the response from the server. The server includes this header in the response to indicate the origins that are authorized to access the resource.

### Technical Implementation
1. **Server Configuration**:
    - Set `Access-Control-Allow-Origin` header to the desired origin (`*` for all origins or a specific origin such as `http://localhost:5173`).
    - Optionally using frameworks like Express.js, CORS middleware automatically adds these headers.
    ```javascript
    const cors = require('cors');
    app.use(cors({
        origin: 'http://localhost:5173'
    }));
    ```
2. **Client-Side Behavior**:
    - The browser restricts cross-origin requests without proper CORS set unless the user explicitly allows installation of a plugin or if the request is categorized as a simple cross-origin request.
3. **Proxy Setup**:
    - If CORS cannot be modified or is not suitable for development, a local proxy can be set up to forward requests to the server from a different origin. This does not change the behavior of CORS but instead works around the browser restriction by modifying the request path or host.

## Variants
- **CORS-Preflight Requests**: Preflight requests are made by the client to check if cross-origin requests are allowed by the server. The browser sends an OPTIONS request to the server before sending the actual request.
- **Preflight-Time Limit**: Relates to how long preflight checks can cache results for, helping in optimizing repeated requests without needing validation every time.
- **CORS with Cookies**: CORS requests can be configured to allow cookies to be passed only if the request is marked as “with credentials”.
- **CORS Security Headers**: More security-related headers such as `Access-Control-Allow-Methods`, `Access-Control-Allow-Headers`, and `Access-Control-Expose-Headers` can be added to specify which HTTP methods, request headers, and response headers can be accessed.

## Trade-offs
- **Security vs. Usability**: While CORS significantly improves security against Cross-Site Request Forgery (CSRF) attacks by ensuring only legitimate origins can access resources, it can complicate the setup and operation of multi-origin web applications ([same-origin-policy]) that require more flexibility. Developers must carefully manage which origins are allowed.
- **Performance Overhead**: Preflight requests may introduce latency in the processing of cross-origin requests, especially in scenarios where the initial OPTIONS request introduces an additional round trip.
- **Development Complexity**: Proper setup and configuration of CORS can add complexity, especially in large-scale projects where multiple frontends connect to multiple APIs. This can relies-on careful coordination between frontend and backend developers.

## See also
- [[jwt]]
- [[swagger]]