# 🛡️ Penetration Test Case Study (Portfolio Version)

## Overview
In August 2025, I conducted an **internal penetration test** for a mid-sized financial services firm.  
The engagement simulated realistic internal threat scenarios to evaluate vulnerabilities, internal security posture, and response readiness.  

**Scope:** Internal network (~multiple hosts, representative sample)  
**Access:** Black-box (no credentials provided)  
**Methodology:** Host discovery, service enumeration, vulnerability identification, reporting, and remediation recommendations  

---

## Key Findings (High-Level)

### 🔴 Critical / High Risk
- Internal management interfaces exposed without segmentation
- Legacy services with missing patches

### 🟠 Medium Risk
- Misconfigured endpoints and redundant administrative services

### 🟢 Strengths
- Intrusion detection successfully logged test activity
- Firewalls effectively restricted most external traffic
- Core servers implemented baseline security controls

---

## Recommendations (Summary)

**Short-Term (30–60 days):**
- Limit administrative access to dedicated segments
- Apply missing patches and remove unnecessary services
- Standardize configuration settings across endpoints

**Long-Term (3–6 months):**
- Migrate from unsupported software and legacy services
- Implement continuous vulnerability scanning and patch management
- Harden internal security policies and enforcement

---

## Tools & Techniques
- **Network & Host Discovery:** Nmap / Zenmap  
- **Web Application & Service Testing:** Burp Suite Community, Manual Validation  
- **Scripting / Automation:** PowerShell, Python for automated checks  
- **Lab / Simulation:** Detection Lab VMs to simulate attack paths safely  

---

## Outcome
This engagement highlights hands-on experience in:
- Internal network threat modeling and attack simulation
- Host and service enumeration
- Communicating findings to both technical and executive audiences
- Delivering actionable remediation steps with clear risk prioritization

---

📌 **Note:** All sensitive details, including client names, IP addresses, hostnames, and specific internal configurations, have been removed or generalized for confidentiality.

