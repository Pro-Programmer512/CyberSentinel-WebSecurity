Wapiti Vulnerability Assessment Report

Target: https://takshyantra.sypoly.org/TECH/
Scan Date: 12 May 2024
Tool Used: Wapiti 3.x
Scan Scope: Full directory recursive scan

## 1. Vulnerability Summary
Category	Vulnerabilities Found
Backup file	0
Blind SQL Injection	0
Weak credentials	0
CRLF Injection	0
Content Security Policy Configuration	4
Cross Site Request Forgery	0
Potentially dangerous file	0
Command execution	0
Path Traversal	0
Htaccess Bypass	0
Cross Site Scripting (XSS)	1
XML External Entity	0
Internal Server Error	1
Resource Consumption	0
Fingerprint Web Technology	0

## 2. Cross-Site Scripting (XSS)
Severity: High
Location: /TECH/login.php

📎 Screenshot: screenshots/xss.png

Description

Cross-site scripting (XSS) occurs when an attacker injects malicious scripts into web pages viewed by other users.
This allows attackers to execute arbitrary JavaScript in the victim’s browser, steal cookies, modify DOM elements, or perform actions as the victim.

Details Extracted from Wapiti
XSS vulnerability found via injection in the parameter email


Injection Parameter: email

Impact

Account takeover via stolen session cookies

Phishing inside the trusted application

Unauthorized actions executed on behalf of logged-in users

Complete compromise of user data integrity

Solutions / Recommendations

Implement strict server-side and client-side validation for all parameters.
Recommended protections:

✔ Encode user input before rendering
✔ Escape dangerous characters: < > & ' ( ) ; # % + -
✔ Implement Content Security Policy (CSP) headers
✔ Use security frameworks that auto-sanitize HTML

References

OWASP: Cross Site Scripting (XSS)

Wikipedia: Cross-site scripting

CWE-79: Improper Neutralization of Input During Web Page Generation

## 3. Internal Server Error (500 Error Injection)
Severity: Medium
Location: /TECH/login.php

📎 Screenshot: screenshots/internal-error.png

Description

A server-side error occurred when Wapiti attempted to inject a payload, causing an HTTP 500 Internal Server Error.
This indicates that the backend is not sanitizing user input and may expose sensitive debugging information.

Details Extracted from Wapiti
The server responded with a 500 HTTP error code while attempting to inject a payload in the parameter password


Injection Parameter: password

Impact

Server crash or denial of service under repeated malicious requests

Information leakage through backend error traces

Exposure of internal server logic

Potential stepping stone to full exploitation (SQLi / RCE)

Solutions / Recommendations

✔ Backend must implement robust exception handling
✔ Validate & sanitize all incoming user inputs
✔ Disable verbose error pages in production
✔ Log internal errors securely without exposing them to users

References

Wikipedia: List of 5xx HTTP status codes

OWASP: Improper Error Handling

## 4. Conclusion

The Wapiti scan identified two actionable security issues:

1️⃣ Reflected XSS in email parameter
2️⃣ Backend crash vulnerability (HTTP 500) in password parameter

These vulnerabilities directly impact application security, user safety, and backend stability, and should be remediated on priority.

## 5. Screenshot Index
/reconnaissance/wapiti/screenshots/
    ├── xss.png
    ├── internal-error.png
