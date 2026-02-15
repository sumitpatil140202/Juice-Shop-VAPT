Testing Methodology
Overview

The security assessment of the OWASP Juice Shop application was conducted using a structured and methodology-driven approach. The testing primarily followed the principles outlined in the OWASP Testing Guide, combining both manual penetration testing techniques and supporting security tools.

The objective was to simulate realistic attacker behavior and identify vulnerabilities that could impact the confidentiality, integrity, and availability of the application.

Testing Approach

I performed the assessment using a black-box testing approach, meaning no access to the application source code was assumed during the initial testing phase. The focus was on identifying vulnerabilities from an external attacker’s perspective.

The testing process included:

Reconnaissance and application mapping

Authentication and session analysis

Input validation testing

Access control testing

Business logic testing

Client-side security analysis

API security testing

Manual testing was prioritized to better understand the application behavior and uncover logic flaws that automated tools often miss.

Testing Phases
1. Reconnaissance & Application Mapping

Initially, I explored the application to understand its structure and functionality. This included:

Browsing all accessible pages

Identifying key endpoints and API routes

Mapping authentication and user flows

Reviewing client-side JavaScript

This phase helped in building a clear attack surface.

2. Authentication & Session Testing

In this phase, I focused on how the application handles login, session management, and JWT tokens.

Activities included:

Testing login functionality for injection flaws

Analyzing JWT structure and contents

Checking token validation behavior

Evaluating logout effectiveness

Performing brute-force attempts to test rate limiting

This phase revealed multiple authentication and token-related weaknesses.

3. Authorization & Access Control Testing

Access control was tested extensively to determine whether users could access unauthorized resources.

I performed:

IDOR testing by manipulating object identifiers

Horizontal privilege escalation checks

Vertical privilege escalation attempts

Forced browsing of hidden directories

API authorization validation

Most high-impact findings were identified during this phase.

4. Input Validation & Injection Testing

User input fields and parameters were tested for improper validation.

Testing included:

SQL Injection in authentication flows

Reflected XSS in search functionality

DOM-based XSS via URL manipulation

Parameter tampering in API requests

Both automated payloads and manual payload crafting were used.

5. Client-Side Security Review

Client-side code was reviewed to identify DOM-based vulnerabilities and insecure practices.

This involved:

Inspecting JavaScript sources and sinks

Monitoring DOM manipulation

Checking security headers

Reviewing browser storage usage

Testing for client-side trust issues

6. API Security & Business Logic Testing

The Juice Shop backend APIs were tested for logic flaws and abnormal behavior handling.

Key activities:

Intercepting and modifying API requests

Testing rate limiting controls

Fuzzing endpoints for abnormal responses

Evaluating error handling behavior

Checking monitoring and logging gaps

Tools and Techniques

The assessment combined manual techniques with supporting tools such as:

Burp Suite for interception and fuzzing

Chrome DevTools for client-side analysis

npm audit for dependency review

However, the majority of findings were discovered through manual exploratory testing, which provided deeper insight into application behavior.

Risk Rating Method

Vulnerabilities were classified into Critical, High, and Medium severity levels based on:

Ease of exploitation

Impact on the application

Potential business risk

OWASP Top 10 alignment

This helped prioritize remediation efforts effectively.

Ethical Considerations

All testing was performed in a controlled laboratory environment on the intentionally vulnerable OWASP Juice Shop application. No production systems or real user data were targeted during this assessment.
