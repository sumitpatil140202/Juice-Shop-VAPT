# VULN-07: Insecure Direct Object Reference (IDOR) on Basket Items

## Severity
High

## OWASP Category
A01:2025 – Broken Access Control

---

## Description

Insecure Direct Object Reference (IDOR) occurs when an application exposes internal object identifiers and fails to properly verify whether the authenticated user is authorized to access the requested resource.

During testing, the basket functionality relied directly on the `BasketId` supplied in the request. The server did not validate whether the requesting user actually owned the basket being accessed.

By modifying the basket ID, it was possible to view or interact with another user's basket.

---

## Affected Component

`/api/BasketItems`

---

## Steps to Reproduce

1. Log in as a normal user.
2. Add an item to your basket.
3. Intercept the basket request using Burp Suite.
4. Modify the `BasketId` value to another valid ID.
5. Forward the request.
6. Observe that data belonging to another user is returned.

---

## Evidence

Refer to the screenshots showing:

- Original request with valid BasketId  
- Modified request with tampered BasketId  
- Successful response showing another user's basket data  

---

## Impact

- Unauthorized access to other users’ data  
- Privacy violation  
- Potential manipulation of other users’ carts  
- Loss of trust in application integrity  

---

## Remediation

- Enforce server-side ownership validation  
- Bind basket access strictly to the authenticated user  
- Use indirect object references (UUIDs instead of sequential IDs)  
- Implement centralized access control checks  

---

## OWASP Mapping

OWASP Top 10 2025 – A01: Broken Access Control
