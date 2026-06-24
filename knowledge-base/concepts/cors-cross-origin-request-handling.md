---
concept: cors-cross-origin-request-handling
entity_type: concept
aliases: []
sources: ["raw\\05-fullstack-integration\\fullstack_integration.md"]
confidence: high
created_at: 2026-06-24T09:46:48Z
---

## Definition
CORS, or Cross-Origin Resource Sharing, is a protocol that enables controlled access from a web page served from one origin (_e.g._, protocol, hostname, and/or port) to resources from a different origin. This protocol is essential for making sure that web applications can securely and reliably communicate with back-end services that are hosted on different domains. It extends the same-origin policy, which is a mechanism that restricts how a document or script loaded from one origin can interact with resources from another origin.

## How it works
When a browser makes an HTTP request from a web page to a server in a different origin, it can behave differently based on the method used for the request. If the method is part of the “simple” category, which includes `GET`, `HEAD`, and `POST` with an `application/x-www-form-urlencoded`, `multipart/form-data`, or `text/plain` content type, the request is sent directly. However, for methods that are not simple, the browser first sends a preflight `OPTIONS` request to ask the server if it is ok to send the actual request.

The server can then choose to allow the request by including certain response headers. Specifically, setting the `Access-Control-Allow-Origin` header to the value of the requesting origin or to ‘*’ to allow all origins is crucial. Additional headers like `Access-Control-Allow-Methods` and `Access-Control-Allow-Headers` are used to indicate which types of requests are permitted.

It's important to note that the server can also choose to support only certain types of origins to enhance security, implementing an access control list but still adhering to the broader principles of security imposed by CORS.

## Variants
There are several implementations of handling cross-origin requests across different platforms and servers:

1. **Node.js (Express) Implementation**: One can use a middleware like `cors` to handle requests coming from different origins. Setting `app.use(cors())` initializes the middleware, and it adds the necessary headers to allow cross-origin requests.

2. **Go Implementation**: In Go, one must manually set the `Access-Control-Allow-Origin` header. For example:
    ```go
    w.Header().Set("Access-Control-Allow-Origin", "http://localhost:5173")
    ```
   
3. **Frontend Proxy Configuration**: In environments like Vite, a frontend proxy can be configured in `vite.config.js` to forward requests to the backend server. This setup bypasses the security policies imposed by CORS, effectively allowing the frontend to communicate with the backend.

## Trade-offs
The primary trade-off with CORS is security versus flexibility. While CORS provides a mechanism for controlled communication between domains, it also introduces complexity in managing origins and methods allowed. This can be cumbersome in dynamic environments where origins might vary. Additionally, misconfigurations can lead to security vulnerabilities, as incorrectly allowing all origins (`*`) can expose APIs to unauthorized access. Therefore, CORS depends on careful management and understanding to avoid security risks. It also requires additional work in the backend to correctly manage headers and potentially set up preflight responses, which can add to operational complexity, especially in large-scale applications. 

## See also
jwt
same-origin policy