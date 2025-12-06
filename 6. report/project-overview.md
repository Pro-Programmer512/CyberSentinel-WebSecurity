📄 Project Overview – CyberSentinel Web Security Assessment

The CyberSentinel Web Security Project is a complete end-to-end penetration testing and vulnerability assessment performed on the target web application.
The objective of this project was to identify critical security weaknesses, validate them through controlled exploitation, and provide actionable recommendations following industry standards such as OWASP Top 10 and PTES.

🎯 Project Goals

Identify potential vulnerabilities through automated and manual testing

Validate high-impact vulnerabilities such as XSS and injection flaws

Assess the security posture of the application

Provide mitigations and hardening recommendations

Build a professional VAPT case study for real-world cybersecurity evaluation

🛠 Tools & Technologies Used
Category	Tools
Reconnaissance	Nmap
Automated Scanning	Wapiti, BurpSuite
Manual Testing	BurpSuite Repeater, Browser PoC
Reporting	Markdown, PDF (ReportLab)
Standards Followed	OWASP Top 10, Pen-Testing Execution Standard (PTES)
📌 Scope of Testing

In-scope target:
https://takshyantra.sypoly.org/TECH/

Focused areas:

Login functionality

Input fields

Parameter behavior

Server response patterns

Application security headers

Client-side and server-side validation

Out-of-scope:

Third-party domains

DoS attacks (only simulated through controlled tests)

🔍 Assessment Methodology

The testing was conducted in 5 phases:

1️⃣ Reconnaissance

Identified open ports, services, and technologies

Collected server and application metadata

2️⃣ Vulnerability Scanning

Wapiti scan revealed XSS and internal server errors

BurpSuite identified reflected XSS and weak configuration issues

Nmap identified open services and server banners

3️⃣ Manual Verification

Verified scanner findings

Removed false positives

Identified real exploitable vectors

4️⃣ Exploitation

Successfully exploited Reflected XSS

Triggered backend failure via Server-side Injection Attempt

Captured impact evidence and PoC screenshots

5️⃣ Reporting

Created exploitation report

Added mitigation strategies

Generated final PDF report

Documented project in a structured GitHub repository

🚨 Key Findings
1. Reflected XSS (High Severity)

Exploitable via email parameter

Allowed arbitrary JavaScript execution

Could lead to session hijacking or phishing attacks

2. Server-Side Injection (Critical Severity)

Payload caused 500 Internal Server Error

Indicates backend instability and injection surface

Potential for DoS or server compromise

🛡 Mitigation Summary

Strict input validation & sanitization

Output encoding

Use of parameterized queries

Improved server error handling

Enable Content Security Policy (CSP)

Disable autocomplete on sensitive fields

Regular security audits & patching

Secure coding practices (OWASP Top 10)

🧩 Project Structure (Folders)
reconnaissance/
vulnerability-scans/
mitigation/
exploitation/
report/


Each folder represents a professional step in the VAPT lifecycle.

📘 Conclusion

The CyberSentinel project successfully demonstrated the process of:

Discovering vulnerabilities

Verifying scanner findings

Executing real-world exploits

Documenting business impact

Recommending strong security mitigations

This project showcases practical VAPT skills and real-world cybersecurity workflow, making it suitable for professional portfolios and job applications.

👤 Prepared By

Vitthal Madhav Dhanve
Security Researcher & VAPT Analyst
CyberSentinel Web Security Project
