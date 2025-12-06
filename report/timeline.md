📅 Project Timeline – CyberSentinel Web Security Assessment

This document outlines the complete timeline of activities performed during the CyberSentinel security assessment.
It reflects a structured, professional workflow aligned with real-world penetration testing methodology.

📆 Overall Assessment Duration
Start Date: 12 May 2024  
End Date:   20 May 2024


(Dates are derived from scan timestamps and aligned with project phases.)

🕒 Timeline Breakdown by Phase
1. Reconnaissance Phase

Date: 12 May 2024
Activities:

Nmap scanning and service enumeration

Identifying open ports and server fingerprints

Collecting headers and technology stack information

Tools: Nmap, Browser Developer Tools

2. Automated Vulnerability Scanning

Date: 12–13 May 2024
Activities:

Wapiti full scan on /TECH/

BurpSuite automated scanning

Identifying initial findings:

Reflected XSS

Internal server error

Security header weaknesses

Tools: BurpSuite, Wapiti

3. Manual Verification

Date: 14–15 May 2024
Activities:

Manual testing of suspicious parameters

Root-cause analysis of server errors

Payload crafting for validation

Eliminating false positives

Tools: Burp Repeater, Browser, Manual Payloads

4. Exploitation Phase

Date: 16–17 May 2024
Activities:

Successfully exploited Reflected XSS

Demonstrated alert execution:
Xss-By-Vitthal-Dhanve

Attempted safe server-side injection

Triggered 500 Internal Server Error for backend weakness confirmation

Captured screenshots & PoC steps

Tools: Browser, BurpSuite, Payload Injection

5. Mitigation Documentation

Date: 17–18 May 2024
Activities:

Prepared XSS mitigation

Created server-side injection mitigation

Added general secure coding best practices

References: OWASP Top 10, Web Security Guidelines

6. Reporting Phase

Date: 18–20 May 2024
Activities:

Wrote exploitation-report.md

Prepared executive-summary.md

Added methodology & scope-of-work

Generated final-security-report.pdf

Structured GitHub repository documentation

Outcome:
A complete professional-grade VAPT project with evidence, report, and mitigation.

🎯 Summary Timeline Table
Date	Phase	Activities
12 May 2024	Reconnaissance	Port scan, service enumeration
12–13 May	Scanning	Wapiti & BurpSuite automated scans
14–15 May	Manual Verification	Payload testing, false-positive removal
16–17 May	Exploitation	XSS PoC, server-side injection attempt
17–18 May	Mitigation	Fix recommendations documented
18–20 May	Reporting	Final report, summaries, documentation
👤 Prepared By

Vitthal Madhav Dhanve
Security Researcher & VAPT Analyst
CyberSentinel Web Security Project
