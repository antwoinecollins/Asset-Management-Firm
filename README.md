# 🛡️ Penetration Test Case Study (Portfolio Version)

## Overview
In August 2025, I conducted an **internal penetration test** for a mid-sized asset management company. The goal was to identify vulnerabilities, assess the internal security posture, and provide actionable remediation recommendations.  

**Scope:** Internal subnet (~44 active hosts)  
**Methodology:** Host discovery, service enumeration, vulnerability identification, and reporting  
**Access:** No credentials provided, black-box internal assessment  

---

## Key Findings

### 🔴 High Severity
- **Firewall Admin Interfaces**: Internal management ports (SSH + web) were open, increasing risk of unauthorized access.
- **PBX/VoIP Server**: Legacy software (Apache, PHP, MariaDB, OpenSSH) with multiple services exposed and expired SSL certificates. High-value system for attackers.

### 🟠 Medium Severity
- **Servers**: One Windows server had SMB signing disabled and legacy NFS services exposed.
- **Printers**: Multiple redundant admin interfaces (HTTP/HTTPS/9100) with expired SSL certificates.

### 🟢 Strengths
- **Intrusion Detection System (IDS)**: Successfully flagged initial scans.
- **Firewall Filtering**: Effectively blocked most external services.
- **Domain Controller**: Properly enforced SMB signing.

---

## Recommendations

**Short-Term (30–60 days):**
- Restrict firewall and PBX admin access to management VLANs.
- Disable unnecessary printer and server services.
- Replace expired certificates.

**Long-Term (3–6 months):**
- Migrate from end-of-life software (Apache, PHP, MariaDB).
- Standardize security hardening (SMB signing, RDP restrictions).
- Establish continuous vulnerability management and regular patch cycles.

---

## Tools & Techniques
- **Nmap / Zenmap** – Host discovery & service enumeration
- **Burp Suite Community** – Web application inspection
- **PowerShell** – URL and port testing
- **Manual Validation** – Browser-based checks of web interfaces

---

## Outcome
This engagement highlighted both **key risks and existing strengths**. The client’s quick detection of scanning activity demonstrated mature monitoring controls, while remediation steps were clearly defined to reduce exposure.  

For my portfolio, this case study reflects hands-on experience with:
- Host and service enumeration
- Internal threat modeling
- Communicating findings to both technical and executive audiences
- Delivering both a **full technical report** and an **executive-friendly slide deck**

---

📌 *Note: All sensitive details (company name, IP addresses) have been removed or generalized for confidentiality.*
