# VULN-23: Improper Exception Handling (HTTP 500 Error)

## Severity
Medium

## OWASP Category
A10:2025 – Mishandling of Exceptional Conditions

---

## Description

The application fails to properly handle unexpected input and returns HTTP 500 Internal Server Error responses. This indicates insufficient exception handling and input validation.

Improper handling of exceptions may lead to application instability and potential information leakage.

---

## Affected Component

Backend exception handling

---

## Steps to Reproduce

1. Send malformed or unexpected input to the application.
2. Observe the server response.
3. Notice HTTP 500 Internal Server Error returned.

---

## Evidence

Refer to the screenshots showing:

- Malformed request  
- HTTP 500 response  
- Application crash behavior  

---

## Impact

- Application instability  
- Potential information disclosure  
- Increased attack surface  

---

## Remediation

- Implement robust exception handling  
- Validate and sanitize all inputs  
- Return controlled error responses  
- Log errors securely on the server side  

---

## OWASP Mapping

OWASP Top 10 2025 – A10: Mishandling of Exceptional Conditions
