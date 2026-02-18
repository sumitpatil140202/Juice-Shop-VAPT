# VULN-22: Missing / Weak Security Headers

## Severity
Medium

## OWASP Category
A05:2025 – Security Misconfiguration

---

## Description

The application response is missing important security headers such as Content Security Policy (CSP), HTTP Strict Transport Security (HSTS), and X-Frame-Options.

Absence of these headers weakens the browser's built-in security protections and increases exposure to client-side attacks.

---

## Affected Component

HTTP response headers

---

## Steps to Reproduce

1. Intercept application responses using a proxy.
2. Inspect response headers.
3. Observe missing or weak security header configuration.

---

## Evidence

Refer to the screenshots showing:

- Captured HTTP response  
- Missing security headers  
- Header analysis results  

---

## Impact

- Increased risk of XSS and clickjacking  
- Reduced transport security enforcement  
- Weakened browser-side protections  

---

## Remediation

- Implement Content Security Policy (CSP)  
- Enable HTTP Strict Transport Security (HSTS)  
- Add X-Frame-Options and X-Content-Type-Options  
- Regularly audit security headers  

---

## OWASP Mapping

OWASP Top 10 2025 – A05: Security Misconfiguration
