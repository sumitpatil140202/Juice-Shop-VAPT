# VULN-14: Rate Limiting Failure (Brute Force Susceptibility)

## Severity
High

## OWASP Category
A07:2025 – Authentication Failures

---

## Description

The application does not implement rate limiting or account lockout mechanisms on the login endpoint. This allows an attacker to perform unlimited authentication attempts against user accounts.

During testing, multiple rapid login attempts were sent to the `/rest/user/login` endpoint using automated tools. The server continued to respond without any blocking, delay, CAPTCHA, or account lockout, confirming the absence of brute-force protection.

This significantly increases the risk of credential stuffing and password guessing attacks.

---

## Affected Component

`/rest/user/login`

---

## Steps to Reproduce

1. Intercept the login request using a proxy tool.
2. Send multiple login attempts with different passwords.
3. Observe that all requests are processed normally.
4. No rate limiting, delay, or account lockout is triggered.

---

## Evidence

Refer to the screenshots showing:

- Burp Suite Intruder attack in progress  
- Multiple failed login attempts  
- Server continuing to respond with HTTP responses  
- No blocking or throttling observed  

---

## Impact

- High risk of account compromise  
- Enables credential stuffing attacks  
- Allows automated password guessing  
- Potential service degradation due to high request volume  

---

## Remediation

- Implement rate limiting on authentication endpoints  
- Enforce temporary account lockout after multiple failures  
- Introduce CAPTCHA after repeated failed login attempts  
- Monitor and alert on brute-force patterns  

---

## OWASP Mapping

OWASP Top 10 2025 – A07: Authentication Failures
