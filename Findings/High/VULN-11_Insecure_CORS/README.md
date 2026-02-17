# VULN-11: Insecure Cross-Origin Resource Sharing (CORS)

## Severity
High

## OWASP Category
A02:2025 – Security Misconfiguration

---

## Description

Cross-Origin Resource Sharing (CORS) controls how web applications allow resources to be requested from another domain.

During testing, the application was found to return the header:

Access-Control-Allow-Origin: *

This wildcard configuration allows any external domain to make cross-origin requests and read responses from the API. Such permissive CORS settings significantly weaken the Same-Origin Policy (SOP) protection.

---

## Affected Component

Global API Configuration

---

## Steps to Reproduce

1. Intercept any API response using Burp Suite.
2. Inspect the response headers.
3. Observe the presence of:
   
   Access-Control-Allow-Origin: *

4. Confirm that requests from arbitrary origins are allowed.

---

## Evidence

Refer to the screenshots showing:

- API response headers in Burp Suite  
- Presence of wildcard `Access-Control-Allow-Origin: *`  
- Successful cross-origin request behavior  

---

## Impact

- Unauthorized cross-origin data access  
- Increased risk of data exfiltration  
- Expansion of application attack surface  
- Potential abuse by malicious third-party websites  

---

## Remediation

- Replace wildcard (*) with a strict origin whitelist  
- Allow only trusted domains in CORS policy  
- Avoid using wildcard for sensitive endpoints  
- Implement proper CORS configuration at server level  

---

## OWASP Mapping

OWASP Top 10 2025 – A02: Security Misconfiguration
