---
concept: sql-injection
entity_type: technique
aliases: ["sql-attack"]
sources: ["raw/cybersecurity.md"]
confidence: high
created_at: 2026-06-23T03:37:44Z
---

## Definition

SQL Injection is a type of security vulnerability in web applications that occurs when an attacker injects malicious SQL statements into application inputs that are directly used in a database query. This can result in unauthorized access to or manipulation of sensitive data, or even the complete compromise of the database.

## How it Works

### Steps of Attack
1. **Input Injection**: The user input, typically from web forms, is incorporated directly into an SQL query without proper sanitization.
2. **Execution of Malicious Query**: The database executes the SQL query as intended, but the crafted input alters the original query or executes additional commands.
3. **Data Access/Misuse**: The attacker can retrieve data, modify records, or gain elevated permissions within the database system.

### Example of Attack
Consider an SQL query intended to filter data based on user input:

```sql
SELECT * FROM users WHERE username = '$user_input';
```

If `$user_input` is set by an attacker to `' OR '1'='1`- the query becomes:

```sql
SELECT * FROM users WHERE username = '' OR '1'='1';
```

Since '1'='1' is always true, this query would return all rows in the users table.

### Prevention
Using *parameterized queries* (prepared statements) is a core recommendation to prevent SQL injection. Parameters are treated as literal values rather than executable code, ensuring that user input is not directly included in the SQL query.

## Variants

### Second-order SQL Injection
This occurs when user input is initially stored in a database and later used in a query within a form that supports direct inclusion of input into the SQL code. This can happen when the input data is considered safe during initial validation but then becomes part of a query in its second usage.

### Blind SQL Injection
When the database response is not visible to the attacker, blind SQL injection involves manipulating boolean queries (true or false) to extract information. This relies on conditional responses (like time delays or content changes) to infer the structure and data.

## Trade-offs

### Procedural SQL Statements vs. Parameterized Queries
While procedural statements can offer better performance in complex queries due to their direct execution capabilities, they are more vulnerable to SQL injection unless meticulously encoded to prevent malicious inputs.

### Complexity of Queries vs. Security
Simpler queries are generally easier to secure against SQL injection, but complex queries that require multiple dynamic elements pose greater security challenges, particularly in maintaining strict sanitization and validation.

## See also
XSS (Cross Site Scripting)  
CSRF (Cross Site Request Forgery)  
Security in Web Applications  
Web Security Threats (OWASP Top 10)