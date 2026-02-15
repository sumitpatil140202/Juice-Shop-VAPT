# OWASP Juice Shop Vulnerability Assessment (VAPT) Project

![Security](https://img.shields.io/badge/Status-Completed-green)
![OWASP](https://img.shields.io/badge/OWASP-Top%2010-red)

---

##  Project Overview

This repository contains a full **Vulnerability Assessment and Penetration Testing (VAPT)** of the **OWASP Juice Shop** application, an intentionally vulnerable web app designed for learning and security testing.  

The main objective of this project was to:

- Identify security weaknesses in the application  
- Simulate real-world attack scenarios  
- Document vulnerabilities with evidence and proof-of-concept (PoC) files  
- Follow ethical testing practices in a controlled lab environment  

This project is part of my **cybersecurity portfolio** and demonstrates skills in **web application security testing, manual testing, and security tool usage**.

---

##  Tools Used

For a detailed list, see [Tools_Used/tools.md](Tools_Used/tools.md).  
Key tools included:

- **Burp Suite (Community Edition):** Intercept and manipulate HTTP requests, perform brute force, analyze cookies and JWT tokens.  
- **Chrome Developer Tools:** DOM inspection, JavaScript analysis, network monitoring, and client-side testing.  
- **npm audit:** Check for insecure third-party dependencies.  
- **Manual testing techniques:** Parameter tampering, forced browsing, CSRF testing, IDOR enumeration, business logic testing.  

---

##  Testing Methodology

For detailed methodology, see [Methodology/testing_methodology.md](Methodology/testing_methodology.md).  

Summary:

1. **Reconnaissance:** Explored endpoints, parameters, and potential attack surfaces.  
2. **Vulnerability Identification:** Used manual testing and automated tools to find vulnerabilities.  
3. **Exploitation:** Verified vulnerabilities with PoC and evidence (screenshots).  
4. **Documentation:** Categorized vulnerabilities by severity and mapped to OWASP Top 10.  
5. **Reporting:** Compiled final VAPT report in PDF format with detailed findings and recommendations.

---

##  Vulnerability Findings

All findings are organized **by severity**:

- **Critical:** SQL Injection, Weak Authentication, Sensitive Data Exposure, Insecure JWT Handling, Reflected XSS  
- **High:** IDOR, Vertical/Horizontal Privilege Escalation, CSRF, Insecure CORS, etc.  
- **Medium:** Missing Security Headers, Verbose Errors, Error Information Leakage  

Each vulnerability has:

- `README.md` → Description and impact  
- `screenshots/` → Evidence images  
- `poc/` → Proof-of-concept files (only for applicable vulnerabilities like CSRF)

Check the `Findings/` folder for full details.

---

##  Project Structure


```
OWASP-Juice-Shop-VAPT/
│
├── README.md
├── LICENSE
├── VAPT_Report/
│   └── OWASP_Juice_Shop_VAPT_Report.pdf
├── Findings/
│   ├── Critical/
│   ├── High/
│   └── Medium/
├── Tools_Used/
│   └── tools.md
└── Methodology/
    └── testing_methodology.md
```

---

##  Final VAPT Report

The full report with **detailed vulnerability descriptions, screenshots, PoCs, and recommendations** is available in:

VAPT_Report/OWASP_Juice_Shop_VAPT_Report.pdf


---

##  Disclaimer

All testing was performed **ethically and legally** on the intentionally vulnerable OWASP Juice Shop application in a controlled lab environment.  

This project is strictly for **educational and portfolio purposes only**. No live systems were tested or harmed.

---

##  Key Takeaways / Skills Demonstrated

- Web application security testing  
- Vulnerability discovery and analysis (OWASP Top 10)  
- Manual and automated testing using security tools  
- Writing professional penetration testing reports  
- Organizing evidence for a recruiter-friendly cybersecurity portfolio  

---
