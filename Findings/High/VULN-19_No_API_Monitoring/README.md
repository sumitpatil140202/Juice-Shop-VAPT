# VULN-19: No Monitoring of Abnormal API Behavior

## Severity
High

## OWASP Category
A09:2025 – Security Logging and Monitoring Failures

---

## Description

The application does not monitor or detect abnormal API usage patterns. During testing, automated fuzzing and high-volume requests were sent to various API endpoints using an interception proxy. The application processed all requests normally without triggering rate limits, alerts, or defensive controls.

This indicates the absence of behavioral monitoring and anomaly detection mechanisms. Attackers can exploit this weakness to perform automated attacks such as enumeration, brute force, and fuzzing without being detected.

---

## Affected Component

API endpoints and monitoring controls

---

## Steps to Reproduce

1. Intercept an API request using a proxy tool.
2. Send the request to an automated attack tool.
3. Launch a high-volume or fuzzing attack.
4. Observe that the application continues responding normally.
5. Confirm that no blocking, throttling, or alerting occurs.

---

## Evidence

Refer to the screenshots showing:

- Automated/fuzzed API requests  
- Large number of requests being processed  
- Consistent HTTP responses from the server  
- No rate limiting or blocking behavior  

---

## Impact

- Enables large-scale automated attacks  
- Facilitates endpoint enumeration  
- Increases risk of data extraction and abuse  
- Reduces the organization's ability to detect active attacks  

---

## Remediation

- Implement API rate limiting and throttling  
- Deploy anomaly detection for unusual traffic patterns  
- Monitor API usage with centralized logging  
- Integrate alerts into SIEM or monitoring platform  

---

## OWASP Mapping

OWASP Top 10 2025 – A09: Security Logging and Monitoring Failures
