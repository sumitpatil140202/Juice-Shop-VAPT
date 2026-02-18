# VULN-24: Information Leakage Through Error Responses

## Severity
Medium

## OWASP Category
A10:2025 – Mishandling of Exceptional Conditions

---

## Description

The API responses expose internal technical details such as database table names, column names, and SQL error logic. These verbose error messages confirm backend behavior and provide attackers with insight into the database structure.

This significantly reduces the effort required to craft successful SQL Injection or other database-related attacks.

---

## Affected Component

API error response handling

---

## Steps to Reproduce

1. Send malformed input to an API endpoint.
2. Trigger a database-related error.
3. Observe the response returned to the client.
4. Notice disclosure of SQL syntax errors or internal database details.

---

## Evidence

Refer to the screenshots showing:

- Malformed request triggering database error  
- SQL error message returned in API response  
- Disclosure of table names or column references  

---

## Impact

- Accelerates exploitation attempts  
- Reveals internal database structure  
- Assists in crafting precise injection payloads  
- Increases overall attack surface  

---

## Remediation

- Sanitize and suppress detailed database errors  
- Implement centralized exception handling  
- Return generic error messages in production  
- Log full error details securely on the server side only  

---

## OWASP Mapping

OWASP Top 10 2025 – A10: Mishandling of Exceptional Conditions
