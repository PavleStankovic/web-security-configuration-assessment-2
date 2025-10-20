# 🔐 Web Security Configuration Assessment — Public Case Study

**Author:** Pavle Stankovic  
**Date:** October 18, 2025  
**Location:** Serbia  
**Age:** 17  
**Domain:** `svstudiodesign.com`  
**License:** CC BY-NC-ND 4.0  

---

## 🧭 Overview

This public case study examines the **SSL/TLS configuration** and **HTTP security headers** of a live production domain (`svstudiodesign.com`), conducted with **explicit permission from the owner**.  
The objective was to identify configuration gaps, evaluate security posture against **modern industry standards**, and document the remediation process for **learning and transparency**.

The assessment follows **OWASP**, **NIST**, and **PCI DSS v4.0** guidelines while maintaining a **non-intrusive, ethical approach**.

---

## ⚙️ Scope & Methodology

**Scope:**  
- SSL/TLS protocol configuration  
- Certificate validation & transparency (SCT, OCSP)  
- Supported cipher suites & forward secrecy  
- HTTP response security headers  

**Out of Scope:**  
- Internal infrastructure  
- Application logic  
- Authentication or intrusive exploitation  

**Tools Used:**  
- `sslyze` (TLS scanning)  
- `nmap` (port/service enumeration)  
- `curl`, `openssl` (header & handshake analysis)  
- `testssl.sh` (TLS simulation & vulnerability checks)  
- Browser DevTools  

**Methodology References:**  
- NIST SP 800-115  
- OWASP Testing Guide v5  

---

## 🔎 Key Findings

| Issue | Severity | Recommendation |
|-------|-----------|----------------|
| Missing HSTS header | Medium | Add Strict-Transport-Security |
| Missing CSP header | Medium | Implement a restrictive Content-Security-Policy |
| Missing X-Frame-Options | Low | Add DENY or SAMEORIGIN |
| Missing X-Content-Type-Options | Low | Set to nosniff |
| Missing Referrer-Policy | Low | Add strict-origin or no-referrer |
| OCSP Stapling disabled | Low | Enable stapling in server config |
| Low SCT count (2) | Low | Reissue certificate with ≥3 SCTs |
| 404 on common subpages | Low | Fix or remove broken endpoints |

✅ **TLS 1.2/1.3 supported**  
✅ **Forward Secrecy enabled**  
✅ **Modern cipher suites** (AES-GCM, ChaCha20-Poly1305)  
✅ **No critical vulnerabilities** (e.g., Heartbleed, POODLE, ROBOT)

---

## 🛠️ Recommended Fixes

Configuration examples for **Apache** and **Nginx** are included in the full report.  
Remediation focuses on achieving an **A+ SSL Labs rating** and aligning with **OWASP A05:2021 – Security Misconfiguration**.

---

## 📊 Compliance Mapping

| Standard | Requirement | Status |
|-----------|-------------|--------|
| OWASP Top 10:2021 | A05: Security Misconfiguration | Addressed |
| NIST SP 800-52 Rev. 2 | Strong TLS & cipher usage | Compliant |
| PCI DSS v4.0 | Req. 4: Secure transmission | Compliant |
| NIST SP 800-53 (SC-8) | Transmission integrity | Partially Met |
| GDPR/HIPAA | Encryption for data protection | Compliant |

---

## 🧠 About the Author

👋 I’m **Pavle Stankovic**, a **17-year-old cybersecurity enthusiast from Serbia** passionate about **web security, TLS, and ethical hacking**.  
I learn by performing **real-world assessments**, implementing secure configurations, and sharing knowledge through public case studies.

- 🌍 Location: Serbia  
- 🎓 Student | Cybersecurity Learner  
- 💡 Focus: TLS, HTTP security, OWASP practices, Linux hardening  
- ✔ Certified in Cybersecurity (CC) – (ISC)²  
- 📧 Email: [stankovic.pavle16@gmail.com](mailto:stankovic.pavle16@gmail.com)  
- 💼 LinkedIn: [linkedin.com/in/pavle-stanković-914694386](https://linkedin.com/in/pavle-stanković-914694386)

---

## 📘 License

This work is licensed under **[CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/)**  
You may **read and share for educational purposes**, but please **credit the author** and **do not modify or use commercially**.

---

## 🧩 Files

- [`Web Security Configuration Assessment.pdf`](./Web%20Security%20Configuration%20Assessment.pdf) — Full detailed report  
- `README.md` — Summary and key insights  

---

The **complete technical analysis**, including scans, configurations, and remediation steps, is available in the PDF.

---

### ⭐ If you found this useful  
Give the repo a **star ⭐**, share it, and feel free to **connect or collaborate!**
