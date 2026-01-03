# 🔐 VAPT – Metasploitable Penetration Testing Report

> Ethical Hacking & Vulnerability Assessment Report on a Metasploitable System

---

## 📌 Project Overview

This repository contains a **Vulnerability Assessment & Penetration Testing (VAPT)** report conducted on **Metasploitable**, an intentionally vulnerable Linux system, in a **controlled lab environment**.

The project demonstrates practical penetration testing skills including **reconnaissance, exploitation, privilege escalation, and professional reporting**, aligned with real-world security assessment workflows.

---

## 🎯 Target Details

- **Target System:** Metasploitable  
- **Target IP:** `192.168.1.4`  
- **Assessment Type:** Internal Penetration Test  
- **Testing Environment:** Kali Linux (Attacker) & Metasploitable (Target)  
- **Authorization:** Educational / Lab-based testing only  

---

## 🛠 Tools & Technologies Used

- **Nmap**
  - Network discovery
  - Port scanning
  - Service and version enumeration

- **Metasploit Framework**
  - Exploitation of known vulnerabilities
  - Payload delivery
  - Session handling

- **Netcat**
  - Manual shell interaction
  - Bind and reverse shell verification

---

## 🚨 Vulnerability Summary

The assessment identified multiple **Critical severity vulnerabilities** leading to **complete system compromise (root access)**.

| ID | Vulnerability | Service | Severity |
|----|---------------|---------|----------|
| FIND-01 | vsftpd v2.3.4 Backdoor RCE | FTP (21) | Critical |
| FIND-02 | Samba Usermap Script RCE | SMB (139/445) | Critical |
| FIND-03 | Unprotected Bind Shell | TCP (1524) | Critical |

---

## 🧨 Exploitation Results

- Successfully gained **root shell access** via vsftpd backdoor  
- Executed **remote code execution as root** using Samba misconfiguration  
- Verified **unauthenticated bind shell** allowing direct system access  

These findings confirm that the target system is **critically insecure** and vulnerable to immediate compromise.

---

## 📄 Project Files

- 📘 **[VAPT_Report_Metasploitable.md](./report/VAPT_Report_Metasploitable.md)** – Detailed technical report  
- 📷 **[Screenshots](./screenshots)** - Contains the images of the testing
- 🛠️ **[Tools Used](./tools-used)** - Contains all the tools used in the testing
- ⚠ **[disclaimer.md](./disclaimer.md)** – Legal & ethical usage disclaimer  

---

## 🛡 Recommendations (High-Level)

- Upgrade outdated and vulnerable services  
- Remove insecure configurations (e.g., Samba usermap scripts)  
- Disable unnecessary services and backdoors  
- Restrict access using firewall rules and network segmentation  

> Detailed remediation steps are provided in the full report.

---

## ⚠ Legal Disclaimer

This project was conducted **strictly for educational purposes** in a controlled lab environment on an intentionally vulnerable system.

⚠ **Unauthorized penetration testing is illegal.**  
The author is not responsible for misuse of this information.

---

## 👤 Author

**Manas Jyoti Boro**  
Aspiring Cybersecurity Professional  
GitHub: `Cyberdrek01`
