---
concept: xss
entity_type: technique
aliases: ["cross-site-scripting"]
sources: ["raw/cybersecurity.md"]
confidence: high
created_at: 2026-06-23T03:37:38Z
---

## Definition

Cross-Site Scripting (XSS) is a type of security vulnerability typically found in web applications where an attacker can inject malicious scripts into a trusted website via unvalidated user input. When another user visits the compromised page, the malicious script executes in their browser, potentially hijacking user sessions, stealing cookies or other sensitive data, or performing unauthorized actions on behalf of the user.

## How it works

### Attack Vector
An attacker exploits XSS vulnerabilities by injecting a script tag containing malicious payload into a web page that other users will visit. The injected script is typically written in JavaScript and executed by the victim's browser assuming the script is part of the legitimate content. This can occur due to user input not being properly validated or sanitized on the server side.

### Types of XSS
1. **Stored XSS**: The malicious script is permanently stored on the target servers, such as in a database, in a message forum, visitor log, comment field, etc. The victim unknowingly accesses the stored XSS content when visiting the page.
2. **Reflected XSS**: The malicious script comes from the web server in response to a request that contains the malicious payload, and the payload is included in the web server's response. If the reflected script is returned and the victim's browser executes it, a successful attack occurs.
3. **DOM-based XSS**: This type occurs purely in the client side and is the result of code on a page not properly validating and sanitizing data that is used in generating the DOM. The attacker provides data to the client-side script, which then creates a new script element that is used to carry out the attack.

### Exploitation
The specific exploits target various browser functionalities, thus enabling the attacker to take over browser sessions, deface websites, or redirect users to malicious sites. The impact depends on the sensitivity of the data and actions available to the compromised session.

## Variants

- **Persistent XSS**: Also known as Stored XSS, this variant involves real-time attacks where the malicious script is stored in the application's database.
- **Non-persistent XSS**: Also known as Reflected XSS, where the malicious script is exploited with the immediate request and returned within the server's response.
- **DOM-based XSS**: This occurs strictly within the DOM environment of a web application, where JavaScript manipulates the document in a way that allows for an XSS payload.

## Trade-offs

### Key Trade-offs and Limitations
- **False Positives/Negatives**: Detection mechanisms for XSS vulnerabilities must be carefully tuned to avoid blocking legitimate input (false positives) while still catching actual XSS attacks (false negatives).
- **User Experience**: Strict input validation can sometimes interfere with user experience if the rules for permitted input are too restrictive.
- **Implementation Complexity**: Enhanced security measures against XSS can increase the complexity and maintenance overhead of web applications.

## See also

Related concepts include CSRF (Cross-Site Request Forgery) and SQL Injection as they pertain to common web application vulnerabilities.