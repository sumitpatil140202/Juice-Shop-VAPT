# OWASP Juice Shop – Vulnerability Assessment & Penetration Testing (VAPT)

![Security](https://img.shields.io/badge/Domain-Web%20Security-blue)
![Project Type](https://img.shields.io/badge/Type-VAPT-red)
![Methodology](https://img.shields.io/badge/Method-OWASP%20Testing%20Guide-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

A comprehensive **manual web application security assessment** of the OWASP Juice Shop application.  
This project demonstrates real-world penetration testing skills including vulnerability discovery, exploitation, and professional reporting.

> All testing was performed ethically in a controlled lab environment on an intentionally vulnerable application.

---

## Project Overview

This repository contains a full **Vulnerability Assessment and Penetration Testing (VAPT)** of the OWASP Juice Shop application — a deliberately vulnerable web application used for security training.

### Objectives

- Identify security weaknesses in the application  
- Simulate real-world attacker behavior  
- Validate vulnerabilities through proof-of-concept (PoC) testing  
- Map findings to **OWASP Top 10 (2025)**  
- Produce a professional penetration testing report  

This project forms part of my cybersecurity portfolio and highlights my practical skills in **web application security testing and manual penetration testing**.

---

## Lab Environment

- **Target Application:** OWASP Juice Shop  
- **Testing Approach:** Black-box manual testing  
- **Environment:** Local controlled lab setup  
- **Testing Focus:** OWASP Top 10 vulnerabilities  
- **Validation Method:** Manual exploitation with supporting evidence  

---

## Tools Used

For full details see: `Tools_Used/README.md`

**Primary tools:**

- **Burp Suite (Community Edition)** – HTTP interception, request manipulation, brute force testing  
- **Chrome Developer Tools** – DOM analysis, client-side testing, network monitoring  
- **npm audit** – Third-party dependency analysis  
- **Manual Testing Techniques** – IDOR enumeration, CSRF testing, forced browsing, parameter tampering  

---

## Testing Methodology

For detailed methodology see: `Methodology/README.md`

### Assessment Flow

1. **Reconnaissance**  
   - Application mapping  
   - Endpoint discovery  
   - Attack surface identification  

2. **Vulnerability Identification**  
   - Manual testing  
   - Proxy-based analysis  
   - Client-side inspection  

3. **Exploitation & Validation**  
   - Proof-of-concept development  
   - Impact verification  
   - False positive elimination  

4. **Documentation & Reporting**  
   - Severity classification  
   - OWASP Top 10 mapping  
   - Professional report preparation  

---

## Vulnerability Findings

The assessment identified multiple security weaknesses across different severity levels.

### Critical Risk Issues

- SQL Injection (Authentication Bypass)  
- Vertical Privilege Escalation to Administrator  
- Weak Authentication Enforcement  
- Sensitive Data Exposure via API  
- Insecure Third-Party Dependencies  

### High Risk Issues

Includes:

- IDOR vulnerabilities  
- Horizontal privilege escalation  
- CSRF vulnerability  
- Insecure CORS configuration  
- DOM & Reflected XSS  
- Rate limiting failures  
- JWT mismanagement  
- Monitoring and logging gaps  

### Medium Risk Issues

Includes:

- Verbose error messages  
- Missing security headers  
- Improper exception handling  
- Information leakage through error responses  

---

## Vulnerability Summary

The following table provides a consolidated view of all identified vulnerabilities.

| ID | Vulnerability | Severity | OWASP Category |
|----|--------------|----------|----------------|
| VULN-01 | SQL Injection (Authentication Bypass) | Critical | A05:2025 – Injection |
| VULN-02 | Vertical Privilege Escalation to Administrator | Critical | A01:2025 – Broken Access Control |
| VULN-03 | Weak Authentication Enforcement | Critical | A07:2025 – Authentication Failures |
| VULN-04 | Sensitive Data Exposure via API Response | Critical | A02:2025 – Cryptographic Failures |
| VULN-05 | Insecure Third-Party Dependencies | Critical | A06:2025 – Vulnerable Components |
| VULN-06 | Insecure Direct Object Reference (IDOR) | High | A01:2025 – Broken Access Control |
| VULN-07 | Forced Browsing (Sensitive Directory Exposure) | High | A05:2025 – Security Misconfiguration |
| VULN-08 | Horizontal Privilege Escalation (Basket Takeover) | High | A01:2025 – Broken Access Control |
| VULN-09 | Insecure Cross-Origin Resource Sharing (CORS) | High | A05:2025 – Security Misconfiguration |
| VULN-10 | Insecure JWT Token Handling | High | A07:2025 – Authentication Failures |
| VULN-11 | Excessive Data Exposure | High | A02:2025 – Cryptographic Failures |
| VULN-12 | Reflected Cross-Site Scripting (XSS) | High | A05:2025 – Injection |
| VULN-13 | DOM-Based Cross-Site Scripting (XSS) | High | A05:2025 – Injection |
| VULN-14 | Rate Limiting Failure | High | A07:2025 – Authentication Failures |
| VULN-15 | Weak Password Policy | High | A07:2025 – Authentication Failures |
| VULN-16 | Client-Side Trust Issues | High | A04:2025 – Insecure Design |
| VULN-17 | JWT Mismanagement (No Revocation) | High | A07:2025 – Authentication Failures |
| VULN-18 | No Logging of Failed Login Attempts | High | A09:2025 – Security Logging Failures |
| VULN-19 | No Monitoring of Abnormal API Behavior | High | A09:2025 – Security Logging Failures |
| VULN-20 | Cross-Site Request Forgery (CSRF) | High | A01:2025 – Broken Access Control |
| VULN-21 | Verbose Error Messages Disclosure | Medium | A10:2025 – Mishandling of Exceptional Conditions |
| VULN-22 | Missing Security Headers | Medium | A05:2025 – Security Misconfiguration |
| VULN-23 | Improper Exception Handling | Medium | A10:2025 – Mishandling of Exceptional Conditions |
| VULN-24 | Information Leakage Through Error Responses | Medium | A10:2025 – Mishandling of Exceptional Conditions |

---

## Repository Structure
OWASP-Juice-Shop-VAPT/
│
├── README.md
├── LICENSE
│
├── VAPT_Report/
│ └── OWASP_Juice_Shop_VAPT_Report.pdf
│
├── Findings/
│ ├── Critical/
│ ├── High/
│ └── Medium/
│
├── Tools_Used/
│ └── README.md
│
└── Methodology/
└── README.md


Each vulnerability folder contains:

- `README.md` → Technical analysis  
- `screenshots/` → Evidence  
- `poc/` → Proof-of-concept (where applicable)  

---

## Final VAPT Report

The complete professional report is available here:

**Path:**  
`VAPT_Report/OWASP_Juice_Shop_VAPT_Report.pdf`

The report includes:

- Executive summary  
- Technical findings  
- Exploitation evidence  
- Risk ratings  
- Remediation guidance  

---

## Skills Demonstrated

- Web Application Penetration Testing  
- OWASP Top 10 vulnerability analysis  
- Manual security testing methodology  
- Burp Suite traffic interception and manipulation  
- Authentication and authorization testing  
- Proof-of-Concept (PoC) development  
- Secure coding recommendations  
- Professional VAPT report writing  

---

## Disclaimer

This project was conducted strictly for **educational and ethical security research purposes**.

- Testing was performed only on the intentionally vulnerable OWASP Juice Shop application  
- No production or unauthorized systems were targeted  
- All activities were performed in a controlled lab environment  

---

## Author

**Sumit Patil** 
`sumitpatil.140202@gmail.com`
Cybersecurity Student | CEH Certified  
Focus Areas: Web Security, VAPT, Network Security

---

If you found this project useful, consider starring the repository.
