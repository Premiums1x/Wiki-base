---
concept: xss-cross-site-scripting
entity_type: concept
aliases: ["cross-site-scripting"]
sources: ["raw\\09-cybersecurity\\cybersecurity.md"]
confidence: high
created_at: 2026-06-24T09:44:10Z
---

## Definition
XSS (Cross Site Scripting) is a wikilink-web-security-threat where an attacker injects malicious client-side scripts into a web page viewed by other users. XSS extends from web security threats, building on wikilink-top-10-owasp|OWASP Top 10 vulnerabilities to exploit vulnerabilities in web applications.

## How it works
XSS attacks occur when an attacker manages to insert malicious scripts into web pages or dynamic content that gets served to benign users. These scripts run in the user's browser context, often permitting actions such as session hijacking (through stolen cookies) when the scripts窃取用户的会话令牌。

攻击的具体实现可以分为三种类型，根据恶意脚本能在什么时间点注入并执行来分类：
1. **存储型 XSS (Persistent/Stored XSS)**：恶意脚本被存储到长期存储空间中，如数据库、会话存储或操作日志，当合法用户访问该储存内容时，浏览器就会执行这些脚本。
2. **反射型 XSS (Reflected XSS)**：直接将用户输入的脚本反射回浏览器的响应结果中。用户点击某些链接或输入带有恶意脚本的输入框后，服务器将这些数据未经适当校验或转义直接返回给用户。
3. **基于DOM的XSS (DOM-based XSS)**：不涉及服务器端响应变更，而是直接利用网页脚本中的动态元素注入攻击脚本。攻击者操纵页面自身行为或数据流生成恶意行为。

## Variants
XSS攻击的变体包括但不限于存储型、反射型以及基于DOM的XSS。此外，XSS攻击还可能利用iframe重定向、恶意图片或Flash等手段发起攻击。这些变体分别优化与改进了原始XSS攻击方法，使其更加隐蔽或更难防护。

## Trade-offs
有效防护XSS需要综合多种手段。一方面，前兆检查（input sanitization）是阻止恶意脚本传播到用户视图的一个直接方法，但这一方法取决于开发者的编码习惯，且无法全面覆盖所有类型的攻击。另一方面，启用CSP（Content Security Policy，内容安全策略）则提供了更为广泛的保护，它通过对传送至浏览器的内容设置安全策略，从而更有效地阻止了跨站脚本攻击。这一方法要求服务器配置更加严格，增加了对网站前端设计者的技术依赖。因此，如何权衡开发复杂度和安全性成为了实施XSS防护时的重要考量因素。

## See also
- wikilink-xss-protection-mechanisms
- wikilink-cross-site-request-forgery-csrf