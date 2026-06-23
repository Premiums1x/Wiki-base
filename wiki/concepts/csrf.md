---
concept: csrf
entity_type: technique
aliases: ["cross-site-request-forgery"]
sources: ["raw/cybersecurity.md"]
confidence: high
created_at: 2026-06-23T03:37:45Z
---

## Definition

Cross-site request forgery (CSRF) is a type of attack that tricks a victim into performing an unwanted action on a website where they are authenticated, without their knowledge. In a CSRF attack, the victim visits a malicious site which contains a crafted request that would induce the web application to perform an action in the context of the authenticated user's session (e.g., change password, transfer money).

## How it works

CSRF attacks leverage user trust and session management vulnerabilities. When a user is logged into a web application, the session information (often stored in a session cookie) identifies the user and the session state. An attacker crafts a malicious web page that triggers a malicious HTTP request—such as a form submission or an AJAX request—that the victim’s browser will send to the vulnerable web application. Since the victim’s browser already has an established session active with the web application, the request is authenticated and could perform actions that the attacker desires. 

For example, an attacker may embed a form submission on a webpage that when visited by an authenticated user unintentionally submits a form to the victim’s bank account to transfer money. If the user has an active session on the bank website, the request will appear legitimate and perform the action, hence the attack.

## Variants

### Direct CSRF Attacks
- Directly include crafted requests within a malicious web page, such as form submissions or AJAX requests, that target the victim’s session.

### Indirect CSRF Attacks
- Use social engineering techniques or injection methods to embed crafted requests, and trick the user into executing them through a series of actions such as clicking on a link.

### Stored CSRF Attacks
- Exploit vulnerabilities in web applications that allow saving scripts, such as forum posts or JavaScript stored in databases, that trigger CSRF attacks when viewed.

## Trade-offs

### Key Trade-offs and Considerations
- **CSRF Token Implementation**: Adding random tokens to forms and validating them on the server side is a strong defense but requires additional development effort and management.
- **SameSite Cookie Attribute**: The `SameSite` attribute can prevent CSRF attacks effectively when set to `Strict` or `Lax`. However, a strict setting may cause usability issues, especially for third-party interactions.
- **Complexity vs. Security**: Implementing CSRF defenses can add complexity to web applications, but neglecting them can lead to significant security vulnerabilities.

### Limitations
- **User Compliance**: Users must be aware of risks and avoid potentially malicious sites and links.
- **Backward Compatibility**: In certain legacy systems, some CSRF protections may require changes that are not compatible with older browsers or systems.

## See also

- XSS (Cross-site scripting)
- Session Management
- Web Security
- OWASP Top 10
- HTTPS