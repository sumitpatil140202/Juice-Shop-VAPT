# VULN-21: Verbose Error Messages Disclosure

## Severity
Medium

## OWASP Category
A10:2025 – Mishandling of Exceptional Conditions

---

## Description

The application returns overly detailed error messages to the client. These responses expose internal implementation details such as stack traces, file paths, and framework information.

Such verbose errors provide attackers with valuable reconnaissance data that can assist in crafting targeted attacks.

---

## Affected Component

API error handling

---

## Steps to Reproduce

1. Send malformed or unexpected input to an API endpoint.
2. Observe the server response.
3. Notice detailed error information returned to the client.

---

## Evidence

Refer to the screenshots showing:

- Triggered application error  
- Verbose stack trace in response  
- Internal framework or path disclosure  

---

## Impact

- Information disclosure to attackers  
- Easier vulnerability discovery  
- Increased attack surface visibility  

---

## Remediation

- Disable verbose errors in production  
- Implement centralized exception handling  
- Return generic user-friendly error messages  

---

## OWASP Mapping

OWASP Top 10 2025 – A10: Mishandling of Exceptional Conditions
