---
concept: same-origin-policy
entity_type: concept
aliases: []
sources: ["raw\\05-fullstack-integration\\fullstack_integration.md"]
confidence: high
created_at: 2026-06-24T07:57:07Z
---

## Definition
The Same-Origin Policy is a key security mechanism enforced by web browsers to restrict how a document or script loaded from one origin can interact with resources from another origin. An origin is defined by the combination of the scheme (http, https), host (domain), and port number. This policy is designed to prevent malicious websites from accessing sensitive information from other websites or manipulating their content.

## How it works
The Same-Origin Policy operates by examining the origin of both the application and the resource being requested. If these origins do not match, the browser will restrict or completely deny access to the resource. For example, if a script running in `http://example.com` (origin 1) attempts to make an XMLHttpRequest to `http://example.org` (origin 2), the request will be blocked because the origins do not match.

To bypass this restriction, developers can use techniques such as setting appropriate CORS headers on the server side to explicitly allow cross-origin requests. This requires the server's response to include an `Access-Control-Allow-Origin` header that specifies the allowed origin or sets it to `*` to allow any origin. Alternatively, developers can configure a proxy in the frontend to proxy requests to the backend, wikilink-proxy-configuration, effectively tricking the browser into thinking both sides are from the same origin.

## Variants
While the core principle of Same-Origin Policy is universally applied by web browsers, the implementation details and configurations can vary among different browsers and web servers. For instance, the default behavior of certain headers such as `Access-Control-Allow-Credentials` may differ. In addition, modern web applications often introduce additional security controls that extend beyond the basic Same-Origin Policy, such as Content Security Policy (CSP).

## Trade-offs
While Same-Origin Policy is essential for maintaining security in a web application, it can also pose challenges that must be carefully managed. The primary challenge is balancing security with the practical need for different parts of an application to communicate securely over the internet. For example, the need for secure cross-origin communication often leads to CORS being enabled, which may slightly increase the risk if not properly configured. Another trade-off is the additional overhead and complexity introduced into the development process, particularly when dealing with CORS and CORS policies.

## See also
- wikilink-cross-origin-requests
- wikilink-content-security-policy