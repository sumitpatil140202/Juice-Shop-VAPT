# VULN-15: Weak Password Policy

## Severity
High

## OWASP Category
A07:2025 – Authentication Failures

---

## Description

The application allows users to set extremely weak passwords such as "human", "admin", or other easily guessable values. No enforcement mechanisms were observed for minimum length, password complexity, or checks against commonly used passwords.

During testing, weak credentials were successfully accepted during registration and authentication, indicating insufficient password policy enforcement.

This significantly increases the likelihood of successful brute-force and credential stuffing attacks.

---

## Affected Component

User Registration / Password Change

---

## Steps to Reproduce

1. Navigate to the user registration page.
2. Attempt to register using a weak password (e.g., "human").
3. Observe that the application accepts the password.
4. Successfully authenticate using the weak credentials.

---

## Evidence

Refer to the screenshots showing:

- Weak password entered during registration  
- Successful account creation  
- Successful login using weak credentials  

---

## Impact

- Increased risk of account compromise  
- Easier brute-force attacks  
- Reduced overall authentication security  
- Weak security posture for user accounts  

---

## Remediation

- Enforce minimum password length (≥12 characters)  
- Require complexity (uppercase, lowercase, numbers, symbols)  
- Block commonly used passwords using deny lists  
- Implement password strength validation on the server side  

---

## OWASP Mapping

OWASP Top 10 2025 – A07: Authentication Failures
