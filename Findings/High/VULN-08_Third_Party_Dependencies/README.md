# VULN-08: Insecure Third-Party Dependencies

## Severity
High

## OWASP Category
A03:2025 – Software Supply Chain Failures

---

## Description

Insecure Third-Party Dependencies occur when an application uses external libraries or packages that contain known security vulnerabilities.

During assessment, the application dependencies were analyzed using `npm audit`. The scan revealed multiple vulnerable packages, including several rated as critical and high severity. These vulnerabilities are inherited by the application and may expose it to various attacks.

---

## Affected Component

`package.json` / `node_modules`

---

## Steps to Reproduce

1. Navigate to the Juice Shop project directory.
2. Run the following command: `npm audit`
3. Review the output showing vulnerable dependencies.
4. Observe multiple high and critical severity findings.

---

## Evidence

Refer to the screenshots showing:

- Execution of `npm audit`  
- List of vulnerable packages  
- Severity summary indicating multiple vulnerabilities  

---

## Impact

- Potential Remote Code Execution (RCE)  
- Increased attack surface via known CVEs  
- Risk of Denial of Service (DoS)  
- Supply chain compromise risk  

---

## Remediation

- Regularly run `npm audit fix`  
- Update vulnerable dependencies to secure versions  
- Integrate SCA tools (Dependabot/Snyk) into CI/CD  
- Remove unused or deprecated packages  

---

## OWASP Mapping

OWASP Top 10 2025 – A03: Software Supply Chain Failures
