# Reconnaissance Phase

This folder contains all **information-gathering and scanning activities** performed before exploitation.  
Reconnaissance is the first and most critical step in any VAPT engagement, helping identify:

- Open ports  
- Running services  
- Server technologies  
- Web vulnerabilities  
- Application behavior  
- Entry points for exploitation  

The reconnaissance phase here is divided into three tool-specific sections:

---

## 📁 1. Nmap Scan (`/nmap`)
Contains network-level scanning results, including:

- Open ports  
- Detected services  
- Server banners  
- SSL/TLS information  
- Potential attack surfaces  

**Files included:**  
- `nmap-scan.txt` — Raw Nmap output  
- Any additional screenshots or logs if required  

Purpose:  
To identify externally visible services and prepare for deeper web application testing.

---

## 📁 2. Wapiti Scan (`/wapiti`)
Contains results from the Wapiti web vulnerability scanner, which identifies:

- XSS  
- Internal server errors  
- Content Security Policy issues  
- Security misconfigurations  
- Input validation weaknesses  

**Files included:**  
- `wapiti-report.md` — Clean, written report  
- `wapiti-report.txt` — Raw scanner output  
- `/screenshots/` — Vulnerability screenshots (e.g., XSS, internal errors)

Purpose:  
To collect automated web-level vulnerabilities before manual exploitation.

---

## 📁 3. BurpSuite Scan (`/burpsuite`)
Contains results from BurpSuite’s automated scanning module, including:

- Reflected XSS  
- Password autocomplete warnings  
- Cross-domain script warnings  
- Clickjacking detection  
- Cacheable HTTPS responses  
- Security misconfigurations  

**Files included:**  
- `burpsuite-scan.txt` — Terminal-like raw findings  
- `burp-findings.md` (if created separately)  
- `/screenshots/` — Findings with visual evidence  

Purpose:  
To validate automated vulnerability presence through a professional-grade web scanner.

---

## 🎯 Objective of Reconnaissance

The reconnaissance phase helps establish:

- A **complete map of the application attack surface**  
- Verified vulnerabilities ready for exploitation  
- Understanding of backend/server behavior  
- Weaknesses in configuration, headers, and input validation  

Recon data directly supports the **exploitation phase**, making the engagement structured and professional.

---

## 📌 Folder Summary

| Folder | Purpose |
|--------|---------|
| `nmap/` | Network-level discovery and port scanning |
| `wapiti/` | Automated web vulnerability detection |
| `burpsuite/` | Advanced scanner results and findings |
| `.keep` | Maintains folder structure |

---

Prepared By:  
**Vitthal Dhanve**  
Security Researcher & VAPT Analyst  
CyberSentinel Web Security Project
