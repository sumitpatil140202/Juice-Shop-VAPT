# VULN-06: Vertical Privilege Escalation to Administrator

## Severity
High

## OWASP Category
A01:2025 – Broken Access Control

---

## Description

Vertical Privilege Escalation occurs when a user with lower privileges is able to access functionality reserved for higher-privileged roles.

During testing, it was observed that a normal authenticated user could access the `/api/Users` endpoint, which should be restricted to administrators only. The backend failed to properly enforce role-based access control and relied only on frontend restrictions.

As a result, sensitive administrative data became accessible to non-admin users.

---

## Affected Component

`/api/Users`

---

## Steps to Reproduce

1. Log in as a normal user.
2. Intercept the request using Burp Suite.
3. Send a direct request to:
```GET /api/Users```

4. Observe that the server returns the full user list including admin data.

---

## Evidence

Refer to the screenshots showing:

- Normal user session  
- Request to admin endpoint  
- Successful response containing user database  
- Presence of administrator account in response  

---

## Impact

- Exposure of sensitive user information  
- Administrator account discovery  
- Increased risk of targeted attacks  
- Complete breakdown of access control model  

---

## Remediation

- Implement strict Role-Based Access Control (RBAC)  
- Verify user role on every sensitive API request  
- Protect admin routes using server-side authorization middleware  
- Follow the principle of least privilege  

---

## OWASP Mapping

OWASP Top 10 2025 – A01: Broken Access Control
