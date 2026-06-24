---
concept: xss
entity_type: concept
aliases: ["Cross-Site Scripting"]
sources: ["raw\\09-cybersecurity\\cybersecurity.md"]
confidence: high
created_at: 2026-06-24T07:59:33Z
---

## Definition
Cross-Site Scripting (XSS) is an web-security vulnerability that enables an attacker to inject malicious client-side scripts into a web page viewed by other users, contradicts the security measures designed to protect users from executing untrusted input. The injected script runs within the context and permissions of the victim's browser session, allowing potential access to sensitive information such as session cookies or details used for user authentication.

## How it works
XSS vulnerabilities arise when an application includes input from a malicious user in an output that is subsequently served to other users without proper validation or sanitization. This input can take the form of malicious scripts, typically written in JavaScript, which exploit functions such as the `document.write` method, `innerHTML`, or event handlers like `onload` and `onmouseover`.

To understand the impact, consider the workflow of a typical XSS attack:

1. An attacker injects script, potentially using vulnerabilities in the input handling of the web application.
2. The server inadvertently serves this script to a victim visiting the same page.
3. The victim's browser executes the script as part of the web page, often under the security context of the visited site.
4. The harmful script then interacts with the site or sensitive data, such as cookies and session information, while the user remains logged in.

To mitigate XSS, it is critical to implement a defense mechanism that depends on secure coding practices, including input validation and sanitization. These measures ensure that any untrusted input is treated as data and not executable code. Techniques such as HTML entity encoding are recommended to encode special characters, such as `<`, `>`, `"`, `'`, and `&`, to prevent the browser from interpreting them as part of the script.

Another safeguard against XSS attacks involves the use of Content Security Policy (CSP) headers, which provide a declarative way to control the sources from which scripts are allowed to run and can help mitigate even sophisticated XSS attacks.

## Variants
XSS vulnerabilities can manifest in several known variants, each targeting different scenarios within a web application:

1. **Stored XSS**: This variant occurs when a web application stores user input (e.g., comments, forum postings) without proper sanitization. The malicious script gets stored on the server, and when other users access these stored data, the script is executed in their browsers. This makes the attack persistent and affects all subsequent users who visit the stored content.
2. **Reflected XSS**: In this case, the malicious script is included in a request URL (usually through a search field query or link) and is immediately served to the user's browser from that request itself, without being stored on the server. This type of attack relies on tricking users into following an attacker-controlled URL or input vector.
3. **DOM-Based XSS**: This type of attack injects client-side script into a vulnerable application through the Document Object Model (DOM). Unlike the stored and reflected types, the malicious script is not stored on the server or transmitted from the attacker's URL. Instead, the script is injected by the application itself, based on input that manipulates the DOM. This makes it invisible to the user and can be executed from the client's storage mechanisms like `localStorage` or `sessionStorage`.
4. **Cross-Domain XSS**: This involves exploiting vulnerabilities across different domains to execute malicious scripts. This variant can be complex due to the same-origin policy that restricts document and script elements from loading content from other origins, unless specific permissions are granted via Cross-Origin Resource Sharing (CORS).

Each variant of XSS attacks has different characteristics and requires tailored defense strategies, such as appropriate input validation and the implementation of secure coding guidelines, to mitigate risks effectively.

## Trade-offs
Implementing defenses against XSS attacks involves trade-offs and considerations:

- **Performance vs. Security**: Implementing rigorous input validation and escaping mechanisms can enhance security against XSS but may also introduce performance overhead. Adjustments might be necessary to find the right balance between security and responsiveness, especially in high-traffic applications. This depends on the application's architecture and resource availability.
- **User Experience**: Traditional measures against XSS can sometimes lead to a less enjoyable user experience, as they simplify or remove functionalities that are potentially risky, such as JavaScript content. Enhancements such as Content Security Policy (CSP) headers can mitigate this problem by allowing more refined control over which scripts can execute.
- **Complexity of Implementation**: Ensuring that every kind of user input is properly sanitized can be complex and error-prone. Comprehensive XSS protection often requires deep integration into the application's development lifecycle and demand for specialized knowledge in security practices.
- **Dependency on Browser Support**: The effectiveness of certain XSS defenses, such as CSP headers, depends on the specific browser in which the web application is being viewed. Not all browsers support the latest CSP directives, which affects the overall protection.

Understanding these trade-offs is essential for developers to prioritize and implement appropriate security measures against XSS attacks without compromising the usability or performance of their applications.

## See also
- csrf
- sql-injection