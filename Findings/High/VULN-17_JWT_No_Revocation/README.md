# VULN-17: JWT Mismanagement (No Revocation)

## Severity
High

## OWASP Category
A07:2025 – Authentication Failures

---

## Description

The application uses JSON Web Tokens (JWT) for session management but does not implement proper token revocation or invalidation mechanisms. Once issued, the JWT remains valid until its expiration time, even after user logout or session termination.

During testing, it was observed that previously issued tokens continued to grant access to protected endpoints. This indicates improper session lifecycle management.

An attacker who obtains a valid JWT (via XSS, token leakage, or other means) can continue to access the application until the token naturally expires.

---

## Affected Component

JWT-based authentication mechanism

---

## Steps to Reproduce

1. Authenticate to the application and obtain a valid JWT.
2. Log out from the application.
3. Replay the previously captured JWT in an authenticated request.
4. Observe that access is still granted.

---

## Evidence

Refer to the screenshots showing:

- Valid JWT obtained after login  
- Logout action performed  
- Reuse of old JWT in request  
- Successful authenticated response  

---

## Impact

- Session hijacking risk  
- Unauthorized persistent access  
- Inability to force user logout  
- Increased risk after token leakage  

---

## Remediation

- Implement token revocation or blacklist mechanism  
- Use short-lived access tokens with refresh tokens  
- Invalidate tokens on logout and password change  
- Consider server-side session tracking for sensitive operations  

---

## OWASP Mapping

OWASP Top 10 2025 – A07: Authentication Failures
