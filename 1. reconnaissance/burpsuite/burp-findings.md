# BurpSuite Web Vulnerability Assessment Report  
**Target:** https://takshyantra.sypoly.org/TECH/login.php  
**Scanner:** BurpSuite Professional v1.7.34  
**Date of Scan:** 20 May 2024  
**Scope:** Application folder: /TECH/  
**Assessed By:** VDsWorld

---

## 📌 Summary of Findings

| Category                             | Vulnerabilities Found |
|-------------------------------------|------------------------|
| Reflected Cross-Site Scripting (XSS) | 1 |
| Password Autocomplete Enabled        | 1 |
| Strict Transport Security Missing    | 1 |

Total Confirmed Issues: **3**

---

# 1️⃣ Reflected Cross-Site Scripting (XSS)

### **Severity:** HIGH  
### **Confidence:** Certain  
### **Affected Path:** `/TECH/login.php`  
### **Parameter:** `email`  
### **Screenshot:** `screenshots/reflected-xss.png`

---

## 🔍 **Description**
A reflected XSS vulnerability occurs when user-controlled input is injected into the server response **without sanitization**.  
BurpSuite confirmed that the application **reflects raw HTML/JS** back to the browser.

This allows attackers to execute **arbitrary JavaScript** in the victim's browser.

---

## 🧪 **Evidence (Proof of Concept)**

Payload used:

```

zxcqw"><script>alert(1)</script>sv529

````

Application reflected the payload without encoding → JavaScript executed successfully.

---

## 🛠 **Technical Details**
- Email parameter input is copied directly into the HTML response.
- No HTML entity encoding ( `< > & " '` ) applied.
- No server-side sanitization or input validation.
- No Content Security Policy (CSP) implemented.

---

## 🎯 **Impact**
- Account/session takeover  
- Redirection to malicious sites  
- Keylogging  
- Theft of authentication cookies  
- Browser exploitation  

This can lead to **complete compromise of the victim’s account**.

---

## 🛡 **Recommendations**
✔ Implement strict server-side input validation  
✔ Encode output using security libraries (e.g., OWASP ESAPI)  
✔ Block unsafe tags & scripts  
✔ Add server-wide **Content Security Policy (CSP)**  
✔ Sanitize and filter user-supplied parameters  

---

---

# 2️⃣ Password Field Autocomplete Enabled

### **Severity:** LOW  
### **Confidence:** Certain  
### **Affected Path:** `/TECH/login.php`  
### **Screenshot:** `screenshots/autocomplete-password.png`

---

## 🔍 **Description**
The login form contains a password field that does **NOT** disable browser autocomplete:

```html
<input type="password" name="password">
````

Because of this, browsers may **store the user’s password locally**, which can be stolen if the system becomes compromised.

---

## 🧪 **Evidence**

BurpSuite identified the form action:

```
https://takshyantra.sypoly.org/TECH/login.php
```

with the password field containing:

```
autocomplete="on" (default)
```

---

## 🛠 **Technical Details**

Browser-stored credentials can be stolen via:

* Malware
* Local system compromise
* Credential-export tools
* Exploited XSS vulnerabilities

---

## 🎯 **Impact**

* User’s credentials may be exposed
* PCI non-compliance risk
* Attackers can log into user accounts without interacting with the application

---

## 🛡 **Recommendations**

✔ Disable autocomplete using:

```
<input type="password" autocomplete="off">
```

OR:

```
<form autocomplete="off">
```

✔ Enforce secure session handling
✔ Educate users regarding password hygiene

---

---

# 3️⃣ HTTP Strict Transport Security (HSTS) Not Enforced

### **Severity:** LOW

### **Confidence:** Certain

### **Affected Path:** `/`

### **Screenshot:** `screenshots/strict-transport.png`

---

## 🔍 **Description**

The web server does not implement **HTTP Strict Transport Security (HSTS)**.
This allows attackers to downgrade secure HTTPS connections to HTTP, enabling **MITM attacks**.

---

## 🧪 **Evidence**

Missing header:

```
Strict-Transport-Security
```

---

## 🎯 **Impact**

* SSL stripping attacks possible
* Sessions can be hijacked
* Sensitive data may be exposed
* User authentication can be intercepted

---

## 🛡 **Recommendations**

Add the following header globally:

```
Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
```

---

---

# 📌 Final Summary

| Vulnerability                 | Severity | Status    |
| ----------------------------- | -------- | --------- |
| Reflected XSS                 | High     | Confirmed |
| Password autocomplete enabled | Low      | Confirmed |
| HSTS missing                  | Low      | Confirmed |

---

# 📁 Files Included

* **burp-report.md**
* **screenshots/reflected-xss.png**
* **screenshots/autocomplete-password.png**
* **screenshots/strict-transport.png**

---

# ✔️ End of Report
