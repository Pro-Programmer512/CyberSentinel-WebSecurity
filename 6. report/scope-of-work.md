📄 Scope of Work (SoW) – CyberSentinel Web Security Assessment

This document defines the authorized scope, constraints, and boundaries of the CyberSentinel Web Security Assessment.
It ensures that all testing activities were performed within approved and ethical limits following VAPT standards.

🎯 1. Objective of the Assessment

The purpose of this engagement was to:

Identify vulnerabilities within the target web application

Validate findings through manual exploitation

Assess the real-world impact

Provide remediation recommendations

Produce a professional penetration testing report

🕸 2. In-Scope Targets
Primary Target (Web Application):
https://takshyantra.sypoly.org/TECH/

In-scope Modules / Functionalities:

Login form

Input parameters (email, password)

Client-side rendering

Server responses

Header configurations

Error handling behaviors

Application technologies and frameworks

Testing Allowed:

Reconnaissance

Vulnerability scanning

Manual verification

Exploitation of safe, non-destructive vulnerabilities

Evidence collection (screenshots, logs)

🚫 3. Out-of-Scope Targets

The following items were explicitly NOT included in the scope:

Any URLs outside /TECH/ directory

User account brute-force attempts

Credential stuffing

Destructive server-side attacks

Data alteration or deletion

Denial of Service (DoS) / stress testing

Third-party APIs, domains, or cloud services

Administrative panels not publicly accessible

Purpose:
To ensure safety of production systems and avoid unauthorized disruption.

⚠️ 4. Testing Limitations

Some activities were intentionally limited to avoid system impact:

Server-side injection was tested only to the point of observing the 500 Internal Server Error

No privilege escalation was attempted

No database scanning or enumeration was performed

No OS-level exploitation or port brute forcing

No modifications to server configuration

These constraints ensured safe exploitation without damaging live systems.

🧪 5. Testing Duration

The assessment was conducted over multiple phases:

Start Date: 12 May 2024  
End Date:   20 May 2024


(Timeframe approximate based on scan timestamps)

📘 6. Deliverables

This engagement produced the following documents:

Executive Summary

Detailed Vulnerability Findings

Exploitation Report

Mitigation Documentation

Final Security Report (PDF)

Complete GitHub Repository with Evidence & Scan Results

🔐 7. Rules of Engagement

Testing was limited to passive and safe exploitation

No destructive testing performed

Only vulnerabilities with proof-of-impact were included

All activities aligned with OWASP & PTES guidelines

Ethical testing boundaries were strictly followed

📝 Conclusion

This Scope of Work ensures that all assessment activities were properly authorized, controlled, and focused on the in-scope web application.
It also clarifies the boundaries and protects both the tester and the application owner by restricting unsafe or unintended actions.

👤 Prepared By

Vitthal Madhav Dhanve
Security Researcher & VAPT Analyst
CyberSentinel Web Security Project
