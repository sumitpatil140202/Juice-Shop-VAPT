# VULN-13: DOM-Based Cross-Site Scripting (XSS)

## Severity
High

## OWASP Category
A05:2025 – Injection

---

## Description

DOM-Based Cross-Site Scripting occurs when client-side JavaScript processes user-controlled input and writes it to the DOM using unsafe methods such as `innerHTML` or `document.write`.

During testing of OWASP Juice Shop, the search functionality was found to read user input from the URL and inject it directly into the page DOM without proper sanitization. This allows an attacker to craft a malicious payload that executes in the victim’s browser.

Unlike reflected XSS, the payload execution happens entirely in the browser and may not be visible in server responses.

---

## Affected Component

Client-Side Search Logic

---

## Steps to Reproduce

1. Open the application in a browser.
2. Modify the search query in the URL with a crafted payload.
3. Load the modified URL.
4. Observe that JavaScript executes in the browser context.

---

## Evidence

Refer to the screenshots showing:

- Malicious payload inserted via URL  
- DOM reflecting the injected payload  
- JavaScript alert popup execution  

---

## Impact

- Session hijacking  
- Phishing and user impersonation  
- Unauthorized actions on behalf of the user  
- Full compromise of user trust and browser session  

---

## Remediation

- Avoid unsafe DOM sinks like `innerHTML`  
- Use safe methods such as `textContent` or `innerText`  
- Implement proper client-side input sanitization  
- Deploy a strong Content Security Policy (CSP)  

---

## OWASP Mapping

OWASP Top 10 2025 – A05: Injection
