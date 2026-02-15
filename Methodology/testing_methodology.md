# Testing Methodology

This document outlines the methodology followed during the security assessment of the OWASP Juice Shop application. The goal was to simulate real-world attack scenarios and identify vulnerabilities in a structured and professional manner.

---

##  Testing Approach

- **Scope:** Black-box web application testing  
- **Objective:** Identify security weaknesses, including authentication, authorization, input validation, session management, and business logic flaws  
- **Environment:** All testing performed in a controlled lab environment on the intentionally vulnerable OWASP Juice Shop application  
- **Proxy Setup:** All browser traffic routed through Burp Suite for analysis and manipulation  

---

##  Phases of Assessment

### 1. Reconnaissance
- Performed initial discovery of application functionality  
- Enumerated endpoints, parameters, and potential attack surfaces  
- Reviewed publicly available information and documentation  

### 2. Vulnerability Identification
- Conducted both **manual testing** and **automated scanning**  
- Tools used included Burp Suite, npm audit, and browser developer tools  
- Manual techniques included:
  - Parameter tampering  
  - Forced browsing  
  - JWT decoding and analysis  
  - DOM inspection  
  - CSRF testing  

### 3. Exploitation
- Validated identified vulnerabilities by safely exploiting them in a controlled environment  
- Created proof-of-concept (PoC) files for vulnerabilities such as CSRF and XSS  
- Ensured no real harm to systems (educational environment only)  

### 4. Documentation
- Captured screenshots and evidence for all vulnerabilities  
- Prepared detailed writeups per vulnerability  
- Categorized vulnerabilities by severity (Critical, High, Medium)  
- Mapped findings to OWASP Top 10 web application risks  

### 5. Reporting
- Compiled all findings into a professional VAPT report (PDF)  
- Included detailed technical descriptions, screenshots, PoC, and risk recommendations  

---

##  Notes on Methodology

- Emphasis on **manual testing**: Most vulnerabilities were discovered through thoughtful testing rather than automated tools alone  
- All testing followed **ethical and controlled procedures**  
- Risk ratings were assigned based on likelihood and impact  

---

##  Disclaimer

All testing was conducted **legally** on the OWASP Juice Shop lab environment for **educational and portfolio purposes only**. No production systems were tested or harmed.
