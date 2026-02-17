# VULN-18: No Logging of Failed Login Attempts

## Severity
High

## OWASP Category
A09:2025 – Security Logging and Monitoring Failures

---

## Description

The application does not properly log or monitor failed authentication attempts. During testing, multiple invalid login requests were sent to the login endpoint, but no visible logging, alerting, or defensive response was observed.

The server consistently returned HTTP 401 responses without triggering any security controls such as account lockout, alert generation, or monitoring indicators.

This lack of visibility allows attackers to perform password guessing and brute force attacks without detection.

---

## Affected Component

User authentication and logging mechanism

---

## Steps to Reproduce

1. Navigate to the login functionality.
2. Send multiple invalid login attempts using different passwords.
3. Observe repeated HTTP 401 Unauthorized responses.
4. Verify that no account lockout, CAPTCHA, or alert is triggered.

---

## Evidence

Refer to the screenshots showing:

- Multiple failed login attempts  
- Repeated HTTP 401 responses  
- No lockout or blocking behavior  
- Continuous acceptance of login requests  

---

## Impact

- Enables undetected brute force attacks  
- Reduces incident detection capability  
- Increases risk of account compromise  
- Weakens overall security monitoring posture  

---

## Remediation

- Implement centralized authentication logging  
- Generate alerts for repeated failed logins  
- Configure account lockout or progressive delays  
- Integrate logs with SIEM for real-time monitoring  

---

## OWASP Mapping

OWASP Top 10 2025 – A09: Security Logging and Monitoring Failures
