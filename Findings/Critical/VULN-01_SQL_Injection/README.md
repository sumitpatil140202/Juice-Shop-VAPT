#  VULN-01: SQL Injection (Authentication Bypass)

## Severity
**Critical**

## OWASP Category
A05:2025 – Injection

---

##  Description

SQL Injection occurs when user-supplied input is improperly concatenated into database queries without proper sanitization or parameterization.

During testing of the OWASP Juice Shop login functionality, the application was found vulnerable to authentication bypass. The login form directly incorporates user input into the SQL query, allowing an attacker to manipulate query logic and gain unauthorized access.

---

##  Affected Component

POST `/rest/user/login`

---

##  Steps to Reproduce

1. Navigate to the login page.
2. Intercept the login request using Burp Suite.
3. In the **email field**, inject the following payload:

' OR 1=1--


4. Forward the request to the server.
5. Observe that authentication succeeds without valid credentials.

---

##  Evidence

Refer to the screenshots showing:

- Injected login request in Burp Suite  
- Successful authentication response  
- Admin access granted  

---

##  Impact

- Complete authentication bypass  
- Unauthorized administrator access  
- Potential full database compromise  
- High risk of sensitive data breach  

---

##  Remediation

- Use parameterized queries or prepared statements  
- Implement strict server-side input validation  
- Use ORM securely with bind parameters  
- Deploy a Web Application Firewall (WAF)

---

## 🔗 OWASP Mapping

OWASP Top 10 2025 – A05: Injection
