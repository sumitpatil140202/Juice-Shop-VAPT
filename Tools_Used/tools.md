# Tools Used

During the security assessment of the OWASP Juice Shop application, I used a combination of manual testing techniques and supporting security tools. The goal was to simulate real-world attack scenarios and identify practical security weaknesses.

---

##  Burp Suite (Community Edition)

Burp Suite was my primary tool for intercepting and analyzing HTTP/HTTPS traffic.

**How I used it:**

- Intercepted and modified requests/responses  
- Tested authentication and authorization flows  
- Performed brute force testing using Intruder  
- Manipulated parameters to identify IDOR and access control issues  
- Analyzed cookies, JWT tokens, and session behavior  

> This tool was heavily used throughout the engagement.

---

##  Google Chrome Developer Tools

Chrome DevTools was used mainly for client-side analysis.

**Activities performed:**

- Inspected DOM to identify DOM-based XSS  
- Reviewed JavaScript sources and sinks  
- Monitored network traffic  
- Checked security headers and cookies  
- Observed application behavior during testing  

> Helped in identifying several client-side weaknesses.

---

##  npm audit

To evaluate third-party dependency risks, I ran **npm audit**.

**Purpose:**

- Detect vulnerable packages  
- Identify known CVEs in dependencies  
- Assess supply chain security risks  

> Findings from this tool contributed to the insecure dependency vulnerability.

---

##  Manual Testing Techniques

Most vulnerabilities were identified through manual testing rather than only automated tools.

**Techniques performed:**

- Parameter tampering  
- Forced browsing  
- IDOR enumeration  
- JWT decoding and analysis  
- CSRF proof-of-concept testing  
- Input validation testing  
- Business logic manipulation  

> Manual testing was critical in uncovering access control and logic flaws.

---

##  Testing Environment

- **Target Application:** OWASP Juice Shop  
- **Testing Approach:** Black-box web application testing  
- **Proxy Setup:** Browser traffic routed through Burp Suite  
- **Encoding/Decoding:** Base64 decoding used for JWT inspection  

---

##  Disclaimer

All testing was performed in a **controlled lab environment** on the intentionally vulnerable OWASP Juice Shop application for **educational and security assessment purposes only**.
