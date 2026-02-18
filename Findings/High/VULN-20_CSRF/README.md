# VULN-20: Cross-Site Request Forgery (CSRF)

## Severity
High

## OWASP Category
A01:2025 – Broken Access Control

---

## Description

The application is vulnerable to Cross-Site Request Forgery (CSRF). The login endpoint accepts authenticated requests without verifying the origin through anti-CSRF tokens or strict same-site protections.

An attacker can craft a malicious HTML page that silently submits a login request on behalf of a victim user. Because the application does not validate request authenticity, the forged request is processed successfully.

---

## Affected Component

User authentication endpoint (/rest/user/login)

---

## Steps to Reproduce

1. Capture the login request using an interception proxy.
2. Create a CSRF proof-of-concept HTML page that auto-submits the same request.
3. Open the PoC in the victim's browser.
4. Observe that the login request is processed successfully.
5. Confirm there is no CSRF token validation.

---

## Evidence

Refer to the screenshots showing:

- Captured login POST request  
- Crafted CSRF PoC HTML file  
- Automatic request submission from external page  
- Successful server response  

PoC file available in the `poc/` directory.

---

## Impact

- Unauthorized actions performed on behalf of users  
- Account misuse and session confusion  
- Potential phishing and forced login attacks  
- Loss of user trust and application integrity  

---

## Remediation

- Implement anti-CSRF tokens for all state-changing requests  
- Use SameSite=strict cookies where appropriate  
- Validate Origin and Referer headers  
- Require re-authentication for sensitive actions  

---

## OWASP Mapping

OWASP Top 10 2025 – A01: Broken Access Control
