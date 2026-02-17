# VULN-03: Sensitive Data Exposure via API Response

## Severity
Critical

## OWASP Category
A04:2025 – Cryptographic Failures

---

## Description

Sensitive Data Exposure occurs when an application unintentionally reveals confidential information in API responses. During testing, the `/rest/user/whoami` endpoint returned the complete user record without proper filtering.

The response included highly sensitive fields such as the password hash (MD5), TOTP secret, and internal identifiers. This indicates improper response sanitization and excessive data exposure.

---

## Affected Component

/rest/user/whoami

---

## Steps to Reproduce

1. Log in as a valid user.
2. Capture the authenticated request to `/rest/user/whoami`.
3. Send the request via proxy (e.g., Burp Suite).
4. Observe the API response.
5. Notice that sensitive fields are exposed in the JSON response.

---

## Evidence

Refer to the screenshots showing:

- Authenticated request to `/rest/user/whoami`  
- API response containing password hash  
- Exposure of TOTP secret and internal user data  

---

## Impact

- Offline password cracking possible  
- MFA bypass risk via exposed TOTP secret  
- User data confidentiality breach  
- Increased risk of account takeover  

---

## Remediation

- Implement Data Transfer Objects (DTOs) to control response fields  
- Exclude sensitive fields (password, totpSecret) from API responses  
- Apply principle of least privilege to returned data  
- Perform server-side response filtering  

---

## OWASP Mapping

OWASP Top 10 2025 – A04: Cryptographic Failures
