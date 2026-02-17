# VULN-05: Reflected Cross-Site Scripting (XSS)

## Severity
Critical

## OWASP Category
A05:2025 – Injection

---

## Description

Reflected Cross-Site Scripting (XSS) occurs when user input is immediately returned in the HTTP response without proper sanitization or output encoding.

During testing, the search functionality in OWASP Juice Shop was found to reflect user-supplied input directly into the HTML response. Because the input was not properly encoded, it allowed execution of arbitrary JavaScript in the victim’s browser.

---

## Affected Component

Search functionality (`/search`)

---

## Steps to Reproduce

1. Navigate to the search bar in the application.
2. Enter the following payload in the search field:
   ``` <img src=x onerror=alert(1)> ```
3. Submit the search request.  
4. Observe that a JavaScript alert executes in the browser.

---

## Evidence

Refer to the screenshots showing:

- Malicious payload entered in search  
- Reflected input in the response  
- JavaScript alert popup execution  

---

## Impact

- Session hijacking via stolen cookies  
- Phishing and user impersonation  
- Malicious script execution in victim browser  
- Compromise of user trust and data  

---

## Remediation

- Implement context-aware output encoding  
- Sanitize and validate user input  
- Deploy a strong Content Security Policy (CSP)  
- Avoid rendering raw user input in HTML  

---

## OWASP Mapping

OWASP Top 10 2025 – A05: Injection

