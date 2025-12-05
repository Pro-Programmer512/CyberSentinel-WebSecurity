# Wapiti Vulnerability Assessment Report  
**Target:** https://takshyantra.sypoly.org/TECH/  
**Scan Date:** Sun, 12 May 2024  
**Tool:** Wapiti (Automated Web Vulnerability Scanner)

---

## 📌 1. Executive Summary
Wapiti web vulnerability scan was performed on the `/TECH/` section of the target application.  
The tool identified multiple findings, including:

- **4 Content Security Policy (CSP) configuration issues**
- **1 Cross-Site Scripting (XSS) vulnerability**
- **1 Internal Server Error (Potential backend misconfiguration)**

These findings indicate insufficient input validation, weak output encoding, and missing security headers.

---

## 📌 2. Scan Summary Table

| Category                          | Vulnerabilities Found |
|----------------------------------|------------------------|
| Backup File                      | 0 |
| Blind SQL Injection              | 0 |
| Weak Credentials                 | 0 |
| CRLF Injection                   | 0 |
| Content Security Policy Issues   | **4** |
| Cross-Site Request Forgery       | 0 |
| Potentially Dangerous File       | 0 |
| Command Execution                | 0 |
| Path Traversal                   | 0 |
| Htaccess Bypass                  | 0 |
| **Cross-Site Scripting (XSS)**   | **1** |
| XML External Entity (XXE)        | 0 |
| **Internal Server Error**        | **1** |
| Resource Consumption             | 0 |
| Fingerprint Web Technology       | 0 |

---

# ✅ 3. Detailed Findings

---

## 🔥 **3.1 Cross-Site Scripting (XSS)**  
**File:** `/TECH/login.php`  
**Severity:** High  
**Type:** Reflected XSS  
**Location:** `email` parameter

### ✔ Description  
Wapiti detected a reflected XSS vulnerability in the login page.  
The application fails to sanitize user input, allowing execution of injected payloads.

### ✔ Proof of Injection  


XSS vulnerability found via injection in the parameter email


### ✔ Impact  
- Attackers may steal session cookies  
- Redirect users to malicious pages  
- Deface UI or perform phishing attacks  
- Execute arbitrary JavaScript in victim's browser

### ✔ Screenshot  
`/reconnaissance/wapiti/screenshots/xss.png`

### ✔ Recommendations  
- Validate all headers, cookies, query strings, and form inputs  
- Apply strict output encoding (`<`, `>`, `"`, `'`, `&`, etc.)  
- Implement **Content Security Policy (CSP)**  
- Prefer server-side sanitization (NOT client-side only)

### ✔ References  
- OWASP: https://owasp.org/www-community/attacks/xss/  
- CWE-79: Improper Neutralization of Input During Web Page Generation  

---

## 🛡 **3.2 Content Security Policy Misconfiguration (CSP)**  
**Severity:** Medium  
**Findings Count:** 4  

### ✔ Description  
The site lacks a strong CSP header, which allows:  
- Browser to load untrusted scripts  
- High risk of XSS exploitation  
- Unsafe inline JavaScript execution

### ✔ Impact  
- Increased exposure to cross-site scripting  
- Browser may load malicious third-party scripts  
- No restriction on framing, media, or script sources

### ✔ Recommendations  
Implement a secure CSP header like:

```http
Content-Security-Policy: 
 default-src 'self'; 
 script-src 'self'; 
 object-src 'none';
 frame-ancestors 'none';
 base-uri 'self';


Screenshot (optional):
/reconnaissance/wapiti/screenshots/csp-issues.png

❗ 3.3 Internal Server Error (500 Error)

File: /TECH/login.php
Parameter: password
Severity: Medium
Category: Error Handling / Input Validation Issue

✔ Description

Wapiti detected an internal server error when injecting payloads into the password field.
The backend server fails to handle unexpected or malicious inputs.

✔ Proof (Wapiti Output)
The server responded with a 500 HTTP error code while attempting to inject a payload in the parameter password

✔ Impact

Reveals unstable backend logic

Possible input validation bypass

May expose the server to DoS or logic exploitation

Indicates potential SQL or backend exception leakage

✔ Screenshot

/reconnaissance/wapiti/screenshots/internal-error.png

✔ Recommendations

Implement complete backend error handling

Do not reflect raw exceptions to users

Add server-level input validation filters

Review application logs for root cause

✔ References

OWASP: Improper Error Handling

HTTP 500 Status: Internal Server Error Guide

📌 4. Overall Risk Evaluation
Vulnerability Type	Severity	Risk
XSS (Reflected)	High	🚨 High
CSP Issues	Medium	⚠️ Medium
500 Internal Error	Medium	⚠️ Medium

Overall, the application is at high risk due to the presence of XSS combined with weak CSP.

📌 5. Conclusion

The Wapiti scan highlights input validation issues, insufficient security headers, and backend instability.
To secure the application, immediate remediation of XSS and server error handling is required.

📎 6. Files & Evidence

/reconnaissance/wapiti/wapiti-report.md (This file)

/reconnaissance/wapiti/screenshots/xss.png

/reconnaissance/wapiti/screenshots/internal-error.png

(Optional) CSP screenshot
