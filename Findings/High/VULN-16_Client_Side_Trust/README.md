# VULN-16: Client-Side Trust Issues

## Severity
High

## OWASP Category
A06:2025 – Insecure Design

---

## Description

The application improperly trusts client-side supplied data without performing sufficient server-side validation. Critical parameters such as user identifiers and basket IDs can be manipulated directly in the request body.

During testing, modified values were accepted by the server, demonstrating that business logic validation is not properly enforced on the backend. This indicates over-reliance on client-side controls.

An attacker can exploit this behavior to manipulate resources, access unauthorized data, or perform actions on behalf of other users.

---

## Affected Component

Basket and user-related API endpoints

---

## Steps to Reproduce

1. Intercept a legitimate request using a proxy tool.
2. Modify sensitive parameters in the request body (e.g., user ID or basket ID).
3. Forward the modified request to the server.
4. Observe that the server processes the manipulated request successfully.

---

## Evidence

Refer to the screenshots showing:

- Original request with valid parameters  
- Modified request with tampered identifiers  
- Successful server response despite manipulation  

---

## Impact

- Unauthorized access to other users' data  
- Business logic abuse  
- Potential privilege escalation  
- Loss of data integrity  

---

## Remediation

- Perform strict server-side validation of all client inputs  
- Implement proper authorization checks for every request  
- Never trust client-controlled identifiers  
- Enforce object-level access control on the backend  

---

## OWASP Mapping

OWASP Top 10 2025 – A06: Insecure Design
