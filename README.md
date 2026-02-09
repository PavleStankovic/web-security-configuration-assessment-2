# Web Security Configuration Assessment

**Target:** svstudiodesign.com  
**Assessment Date:** February 6, 2026  
**Tester:** Pavle Stankovic  
**Authorization:** Explicit written permission from domain owner  

---

## Executive Summary

Black-box security assessment of SSL/TLS configuration and HTTP security headers for a production web application. Testing identified several configuration weaknesses (missing security headers, low Certificate Transparency coverage) alongside strong cryptographic implementation (TLS 1.2/1.3, modern cipher suites, forward secrecy).

**Key Outcomes:**
- Identified 8 configuration issues (2 Medium, 6 Low severity)
- Provided actionable remediation with server config examples
- Collaborated with site owner to fix HTTP-to-HTTPS redirect
- Achieved SSL Labs A+ rating baseline with improvement roadmap

---

## Technical Approach

**Tools:**
- sslyze (certificate validation, protocol enumeration)
- testssl.sh (vulnerability scanning, client simulation)
- nmap (port/service discovery)
- curl + openssl (header analysis, handshake verification)
- Qualys SSL Labs (configuration benchmarking)

**Standards Referenced:**
- OWASP Top 10:2021 (A05 - Security Misconfiguration)
- NIST SP 800-52 Rev. 2 (TLS Guidelines)
- PCI DSS v4.0 (Requirement 4)

---

## Findings Summary

| Finding | CVSS 4.0 | Priority | Status |
|---------|----------|----------|--------|
| Missing HSTS | 4.8 | High | Open |
| Missing CSP | 5.3 | High | Open |
| Missing X-Frame-Options | 4.3 | Medium | Open |
| Low SCT count (2 vs. 3+) | 3.1 | Medium | Open |
| No OCSP Stapling | 2.4 | Low | Open |

**Positive Findings:**
- TLS 1.2/1.3 only (no deprecated protocols)
- Strong AEAD cipher suites (AES-GCM, ChaCha20-Poly1305)
- Forward secrecy enabled
- Not vulnerable to Heartbleed, POODLE, FREAK, DROWN

---

## Deliverables

**[📄 Full Technical Report (PDF)](./Web%20Security%20Configuration%20Assessment2.pdf)**

Includes:
- Detailed methodology and tool selection rationale
- Complete scan outputs and analysis
- CVSS v4.0 scoring methodology with examples
- Server configuration remediation (Apache/Nginx)
- Compliance mapping (OWASP, NIST, PCI DSS)

---

## About

**Pavle Stankovic**  
18-year-old cybersecurity enthusiast | (ISC)² Certified in Cybersecurity (CC)  
📍 Serbia  
📧 stankovic.pavle16@gmail.com  
💼 [LinkedIn](https://linkedin.com/in/pavle-stanković-914694386)

*This assessment is part of my public learning portfolio demonstrating hands-on security analysis and professional reporting skills.*

---

**Ethical Note:** All testing was authorized. Sensitive infrastructure details (IP addresses) are redacted. This report is shared for educational purposes under responsible disclosure principles.
