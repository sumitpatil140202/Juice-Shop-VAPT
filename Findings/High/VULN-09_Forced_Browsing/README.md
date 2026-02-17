# VULN-09: Forced Browsing (Sensitive Directory Exposure)

## Severity
High

## OWASP Category
A01:2025 – Broken Access Control

---

## Description

Forced Browsing occurs when sensitive files or directories are accessible directly via URL without proper authorization checks.

During testing, the `/ftp` directory was discovered to be publicly accessible. The directory listing was enabled, allowing anyone to browse files including backups and the `/ftp/quarantine` folder. These resources were not linked in the UI but remained reachable through direct URL access.

This indicates missing access controls on sensitive server paths.

---

## Affected Component

`/ftp`  
`/ftp/quarantine`

---

## Steps to Reproduce

1. Open the Juice Shop application.
2. Manually browse to: ```http://localhost:3000/ftp```


3. Observe directory listing is enabled.
4. Navigate into: `/ftp/quarantine`


5. Confirm sensitive files are accessible.

---

## Evidence

Refer to the screenshots showing:

- Direct access to `/ftp` directory  
- Directory listing enabled  
- Access to `/ftp/quarantine`  
- Sensitive files visible to unauthenticated user  

---

## Impact

- Exposure of sensitive internal files  
- Possible leakage of backups or malware samples  
- Increased reconnaissance opportunities for attackers  
- Violation of least privilege principle  

---

## Remediation

- Disable directory listing on the web server  
- Restrict access to sensitive folders  
- Remove test and backup files from production  
- Implement proper authorization checks  

---

## OWASP Mapping

OWASP Top 10 2025 – A01: Broken Access Control
