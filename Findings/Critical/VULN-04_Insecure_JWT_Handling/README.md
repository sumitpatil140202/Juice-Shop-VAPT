# VULN-04: Insecure JWT Token Handling

## Severity
Critical

## OWASP Category
A04:2025 – Cryptographic Failures

---

## Description

Insecure JWT handling was identified in the application. The issued JSON Web Token (JWT) contains sensitive user information such as email address and internal user ID within the token payload.

Additionally, the token is stored in LocalStorage or accessible client-side storage, making it vulnerable to theft through Cross-Site Scripting (XSS) attacks. Since JWT payloads are only Base64 encoded and not encrypted, any intercepted token can be easily decoded.

---

## Affected Component

Authentication Token Mechanism

---

## Steps to Reproduce

1. Log in to the application with valid credentials.
2. Capture the JWT from LocalStorage or the authentication response.
3. Decode the JWT using any online decoder or Burp Suite.
4. Observe sensitive user information inside the token payload.
5. Confirm that the token is accessible via client-side scripts.

---

## Evidence

Refer to the screenshots showing:

- Captured JWT token  
- Decoded JWT payload  
- Exposure of user email and internal ID  
- Token stored in client-accessible storage  

---

## Impact

- Exposure of Personally Identifiable Information (PII)  
- Session hijacking risk if token is stolen  
- Increased impact of XSS attacks  
- Potential unauthorized account access  

---

## Remediation

- Avoid storing sensitive data inside JWT payloads  
- Store tokens in HttpOnly, Secure, SameSite cookies  
- Implement short token expiration with refresh mechanism  
- Consider using encrypted tokens (JWE) where appropriate  

---

## OWASP Mapping

OWASP Top 10 2025 – A04: Cryptographic Failures
