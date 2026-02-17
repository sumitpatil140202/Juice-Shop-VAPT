# VULN-02: Weak Authentication Enforcement

## Severity
Critical

## OWASP Category
A07:2025 – Authentication Failures

---

## Description

Weak Authentication Enforcement occurs when the application fails to properly validate authentication tokens. During testing, the OWASP Juice Shop application was observed accepting tokens without strict verification checks.

The backend did not consistently validate token signature strength and expiration, which could allow attackers to use forged or expired tokens to gain unauthorized access.

---

## Affected Component

API Authorization Mechanism

---

## Steps to Reproduce

1. Authenticate as a normal user and capture the JWT token.
2. Modify or reuse an expired/weak token.
3. Send a request to a protected endpoint using the manipulated token.
4. Observe that the server accepts the token without proper validation.

---

## Evidence

Refer to the screenshots demonstrating:

- Captured authentication token  
- Request sent with weak/expired token  
- Successful server response  

---

## Impact

- Authentication bypass  
- Session hijacking risk  
- Unauthorized account access  
- Increased attack window due to zombie sessions  

---

## Remediation

- Strictly verify JWT signature on every request  
- Enforce token expiration (`exp` claim) validation  
- Allow only strong signing algorithms (e.g., RS256)  
- Reject tokens using the "none" algorithm  

---

## OWASP Mapping

OWASP Top 10 2025 – A07: Authentication Failures
