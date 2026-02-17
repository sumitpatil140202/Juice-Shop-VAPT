# VULN-12: Excessive Data Exposure

## Severity
High

## OWASP Category
A04:2025 – Cryptographic Failures

---

## Description

Excessive Data Exposure occurs when an API returns more information than is required by the client application. Instead of filtering data on the server side, the application sends the complete object and relies on the frontend to hide sensitive or unnecessary fields.

During testing, multiple API responses were observed returning additional internal fields that were not displayed in the user interface. These included metadata such as timestamps, internal identifiers, and status fields.

This behavior increases the attack surface by exposing sensitive or unnecessary information to attackers monitoring network traffic.

---

## Affected Component

API Responses

---

## Steps to Reproduce

1. Log in to the application.
2. Open **Browser Developer Tools → Network tab**.
3. Perform normal user actions (e.g., view profile or products).
4. Inspect API JSON responses.
5. Observe additional fields returned that are not required by the UI.

---

## Evidence

Refer to the screenshots showing:

- Full JSON API response in Network tab  
- Presence of extra fields (e.g., internal IDs, timestamps)  
- Comparison between UI display and backend response  

---

## Impact

- Information disclosure to attackers  
- User profiling and intelligence gathering  
- Increased attack surface  
- Potential abuse of hidden fields in future attacks  

---

## Remediation

- Implement server-side response filtering  
- Return only required fields via DTOs  
- Avoid exposing internal metadata in API responses  
- Apply strict response schema validation  

---

## OWASP Mapping

OWASP Top 10 2025 – A04: Cryptographic Failures
