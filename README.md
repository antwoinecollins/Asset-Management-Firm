# 🛡️ Penetration Test Case Study (Portfolio Version)

## Overview
In August 2025 I performed an **internal penetration test** for a mid-sized asset-management firm. The engagement simulated realistic internal threat scenarios to evaluate vulnerabilities, internal security posture, and response readiness.

**Scope:** Internal network (representative sample of hosts and services)  
**Access:** Black-box (no credentials provided)  
**Methodology:** Reconnaissance, host/service enumeration, safe validation of vulnerabilities, and remediation recommendations.

---

## Key High-Level Findings
**Critical / High Risk**
- Internal management interfaces exposed without segmentation (high-risk admin panels on telephony and firewall devices).
- End-of-life / unpatched software on certain appliances (e.g., PBX web interfaces, embedded devices).

**Medium Risk**
- Redundant administrative services running on printers and IoT/VoIP endpoints.
- Unrestricted internal access to certain backup/replication services.

**Strengths**
- IDS detected test activity and logging was functioning.
- Core domain controller had SMB signing enforced and other baseline hardening.

---

## Executive Recommendations (summary)
**Short-Term (30–60 days)**
- Restrict management interfaces to management VLANs only and enforce MFA for admin access.
- Patch or replace EOL systems and rotate default/weak credentials.
- Forward device logs (syslog/SNMP) into a SIEM for baseline monitoring.

**Long-Term (3–6 months)**
- Establish continuous vulnerability scanning and a formal patch cadence.
- Harden VoIP/PBX infrastructure and apply vendor firmware updates.
- Implement least-privilege network segmentation and device inventory.

---

## Tools & Techniques
- **Network/Host Discovery:** Nmap, Advanced IP Scanner  
- **Web & App Testing:** Burp Suite Enterprise, manual inspection  
- **Scripting & Automation:** PowerShell, small Python tooling for enumeration  
- **Reporting:** Sanitized PDF report + technical appendix

---

## Example (Sanitized) Technical Finding — PBX Server
**Summary:** PBX system exposed multiple admin panels, running end-of-life components. Expired TLS observed on management ports.

**Risk:** Critical — potential for remote code execution or credential compromise.

**Evidence (sanitized):**
- Nmap fingerprinting showed multiple HTTPS ports responding with the same domain CN (redacted).
- SIP/Asterisk interfaces reachable internally; multiple web admin endpoints accessible.

**Recommendation:**
1. Immediately restrict web admin ports to management VLAN/VPN only.  
2. Update PBX software/firmware to vendor-supported release.  
3. Replace expired TLS certs; enforce modern cipher suites.  
4. Rotate all admin credentials and enable 2FA where supported.  
5. Forward PBX logs to SIEM and monitor for suspicious activity.

**Screenshot:** `Onsite with my laptop and notepad, plugged into network` (Sanitized Ports & IPs).

![Laptop & Notepad](https://github.com/antwoinecollins/Asset-Management-Firm/blob/main/Onsite_Pentest_InAction_Sanitized.png)

## Deliverables & Repo Contents
- `report/unnamedcompany-fullreport-sanitized.pdf` — executive + sanitized technical appendix  
- `technical_findings/` — one-page sanitized findings (CSV/MD)  
- `screenshots/` — sanitized images (see naming below)  
- `README.md` (this file)  
- `scripts/` — non-sensitive helper scripts (generic scanners, no hardcoded IPs)

### 📄 Sanitized Report Example  
_A sample of the professional deliverable created for this engagement (all sensitive details removed)._  

![Report Screenshot](https://github.com/antwoinecollins/Asset-Management-Firm/blob/main/ReportSample_Screenshot_Sanitized.png)


---

## Notes on Confidentiality
All client-identifying details, IP addresses, hostnames, and raw screenshots have been redacted or replaced with placeholders. This repo is a portfolio artifact meant to illustrate methodology, thought process, and remediation guidance — not to publish live client data.

