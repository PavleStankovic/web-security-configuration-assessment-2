🔐 Web Security Configuration Assessment — Public Case Study

Author: Pavle Stankovic
Date: October 18, 2025
Domain: svstudiodesign.com
Location: Serbia
Age: 17
License: CC BY-NC-ND 4.0

🧭 Overview

This public case study presents a real-world assessment of the SSL/TLS configuration and HTTP security headers of a production website (svstudiodesign.com), performed with explicit permission from the owner.

The objective was to:

Evaluate alignment with modern web security standards

Detect configuration weaknesses

Provide clear, actionable remediation steps

Document the process for educational and professional growth

This assessment follows ethical, non-intrusive methods and references OWASP, NIST, and PCI DSS v4.0 standards—demonstrating a professional-level security approach.

⚙️ Scope & Methodology
✅ In Scope

SSL/TLS protocol analysis

Certificate validation & transparency (SCTs, OCSP Stapling)

Supported cipher suites & forward secrecy

HTTP response security headers

❌ Out of Scope

Internal infrastructure

Authentication/session testing

Application logic or intrusive exploitation

Social engineering

🛠 Tools Utilized
Tool	Purpose
sslyze	TLS protocol & certificate analysis
nmap	Port & service discovery
curl / openssl	Header inspection & handshake testing
testssl.sh	Full TLS vulnerability scanning
Qualys SSL Labs	External grading & validation
Browser DevTools	Real-world header behavior
📚 Methodology References

NIST SP 800-115 – Technical test framework

OWASP Testing Guide v5 – Web configuration best practices

PCI DSS v4.0 – Secure transmission requirements

🔎 Key Findings
Issue	Severity	Recommendation
Missing HSTS header	Medium	Enforce Strict-Transport-Security
Missing CSP policy	Medium	Implement restrictive Content-Security-Policy
Missing X-Frame-Options	Low	Add DENY or SAMEORIGIN
Missing X-Content-Type-Options	Low	Set nosniff
Missing Referrer-Policy	Low	Add strict-origin or no-referrer
OCSP Stapling disabled	Low	Enable on server
Low SCTs (2)	Low	Reissue certificate with ≥3 SCTs
404 on common subpages	Low	Fix or remove broken endpoints

✅ Positive Security Controls

TLS 1.2 / 1.3 only (no deprecated protocols)

Strong modern cipher suites (AES-GCM, ChaCha20-Poly1305)

Forward Secrecy supported

No major vulnerabilities (Heartbleed, POODLE, ROBOT, etc.)

HTTPS enforced (HTTP redirect implemented)

🛠 Remediation Highlights

(Full configuration examples included in the PDF report)

Add security headers via .htaccess / server config

Enable OCSP Stapling

Improve Certificate Transparency (CT)

Fix missing pages (404s)

Aim for A+ SSL Labs rating

Align with OWASP A05: Security Misconfiguration

📊 Compliance Alignment
Standard	Requirement	Status
OWASP Top 10 (2021)	A05: Security Misconfiguration	Partially Met
NIST SP 800-52	Strong TLS, cipher order	Compliant
PCI DSS v4.0	Encrypted transmission	Compliant
NIST SP 800-53 (SC-8)	Network protection	Partially Met
GDPR / HIPAA	Data in transit protection	Compliant
🧠 About the Author

Hi! I’m Pavle Stanković, a 17-year-old cybersecurity enthusiast from Serbia.
I’m passionate about TLS, HTTP security, Linux hardening, and real-world penetration testing.

🎓 Certified in Cybersecurity (CC) – (ISC)²
🛠 I learn by doing: hands-on testing, case studies, and reporting
🌍 My goal: become a professional ethical hacker and inspire others

Contact & Profiles:
📧 Email: stankovic.pavle16@gmail.com

💼 LinkedIn: linkedin.com/in/pavle-stanković-914694386

📘 License

This project is licensed under CC BY-NC-ND 4.0.
You may share this work for educational purposes with attribution.
You may not modify or use commercially without permission.

📁 Repository Contents
├── Web Security Configuration Assessment.pdf   # Full detailed report
└── README.md                                   # Summary & highlights


The full technical details, scans, and configuration examples are available in the PDF report.

⭐ Support & Collaboration

If you found this case study valuable:
✅ Star the repository ⭐
✅ Connect with me on LinkedIn
✅ Let’s collaborate on security projects!
