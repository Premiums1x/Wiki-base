---
concept: content-security-policy
entity_type: concept
aliases: []
sources: ["raw\\09-cybersecurity\\cybersecurity.md"]
confidence: high
created_at: 2026-06-24T07:59:43Z
---

## Definition
Content Security Policy (CSP) is a security standard that allows a web server to define the sources from which a web page is allowed to load web resources, such as scripts and images. CSP builds on top of the broader strategy of web security and is designed to mitigate the risk of cross-site-scripting|XSS, which is one of the web application security threats outlined in the OWASP Top 10.

## How it works
When a website enables CSP, it sets a header in its HTTP responses. This header contains a set of rules that explicitly allow certain types of content while disallowing others. For example, a CSP directive `script-src 'self'` would only permit script elements from the same domain as the web page itself.

CSP uses reporting mechanisms to provide warnings or alerts for potential risks without blocking content outright. There are two types of reports:
- **Report-only mode**: This mode does not enforce CSP directives but sends violation reports to a specified URI.
- **Enforcement mode**: This disables inline scripts and external scripts that do not come from the defined sources, providing a strict security posture.

Each CSP directive applies to specific types of content. For example, the `script-src` directive controls where the browser is allowed to fetch scripts from, while `style-src` deals with stylesheets.
Additionally, CSP supports nonce (number-used-once) and hash validation mechanisms to further restrict inline scripts and styles, ensuring that even if an attacker can inject a script, it will not execute unless meeting the specified hash or nonce criteria.

The deployment of CSP can sometimes require careful consideration to avoid breaking legitimate web functionality. It builds on top of the principles of security headers management, which includes other headers like Strict-Transport-Security for securing connections over HTTPS.

## Variants
CSP policies can be varied widely depending on the needs of web applications. For example, a simple CSP might only involve the `script-src` directive, whereas more complex policies might use a range of directives such as `style-src`, `img-src`, and `connect-src` to control images, styles, and AJAX API endpoints respectively.

HTML attributes, such as `nonce` and `integrity`, can be used within inline scripts and styles to further enhance security. The `nonce` attribute provides a unique, randomly generated token for each request that an embedded content source must include, acting as a one-time password. The `integrity` attribute uses Subresource Integrity (SRI) to ensure that resources retrieved over the web are delivered from unaltered sources.

## Trade-offs
While CSP offers significant protection against XSS, it also poses some trade-offs:
- **Complexity**: Implementing CSP requires a deep understanding of a website’s resources and their sources. This can be complex for large and dynamic websites.
- **Breakage Risks**: Incorrectly implemented CSP policies can inadvertently block legitimate resources, leading to partial or complete breakage of the web page.
- **User Experience**: While CSP enhances security, overly strict policies may affect the performance of pages or break acceptable user interactions.
- **Compatibility**: Older browsers may not support CSP, requiring fallback mechanisms for these browsers, complicating overall deployment strategies.

CSP contrasts with other security measures such as input validation, which does not directly relate to controlling content sources but instead ensures that data entered into a web page adheres to expected formats.

## See also
- cross-site-scripting
- input-validation