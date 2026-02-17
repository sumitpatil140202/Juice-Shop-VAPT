# VULN-10: Horizontal Privilege Escalation (Basket Takeover)

## Severity
High

## OWASP Category
A01:2025 – Broken Access Control

---

## Description

Horizontal Privilege Escalation occurs when a user is able to access or modify resources belonging to another user with the same privilege level.

During testing, it was observed that the application trusts the `BasketId` supplied by the client. By intercepting the request and modifying the BasketId to another valid value, the application allowed manipulation of another user's basket.

The server failed to verify whether the authenticated user actually owns the referenced basket.

---

## Affected Component

`/api/BasketItems`

---

## Steps to Reproduce

1. Log in as a normal user.
2. Add any product to your basket.
3. Intercept the request in Burp Suite.
4. Locate the `BasketId` parameter.
5. Modify the BasketId to another valid value.
6. Forward the request.
7. Observe that another user's basket is affected.

---

## Evidence

Refer to the screenshots showing:

- Original request with valid BasketId  
- Modified request with tampered BasketId  
- Successful server response  
- Basket manipulation reflected in the application  

---

## Impact

- Unauthorized modification of other users' carts  
- Potential financial manipulation  
- Loss of data integrity  
- Broken access control enforcement  

---

## Remediation

- Validate basket ownership on the server side  
- Derive BasketId from the authenticated session  
- Reject client-supplied object identifiers  
- Implement centralized access control checks  

---

## OWASP Mapping

OWASP Top 10 2025 – A01: Broken Access Control
