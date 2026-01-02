# 🔐 Vulnerability Assessment & Penetration Testing (VAPT) Report

## 📌 Project Overview
This repository contains a Vulnerability Assessment and Penetration Testing (VAPT) report conducted on a deliberately vulnerable system (Metasploitable) in a controlled lab environment.

The objective of this project is to identify security weaknesses, exploit them ethically, and provide remediation recommendations following industry best practices.

---

## 🎯 Target Details
- **Target IP:** 192.168.1.4
- **Environment:** Local lab (Metasploitable)
- **Assessment Type:** Internal Penetration Test

---

## 🛠 Tools Used
- Nmap
- Metasploit Framework
- Netcat

---

## 🚨 Key Findings
| ID | Vulnerability | Severity | Status |
|----|--------------|----------|--------|
| FIND-01 | vsftpd v2.3.4 Backdoor RCE | Critical | Exploited |
| FIND-02 | Samba Usermap Script RCE | Critical | Exploited |
| FIND-03 | Unprotected Bind Shell (1524) | Critical | Verified |

---

## 📄 Report
- [PDF Report](report/VAPT_Report_Metasploitable.pdf)
- [Markdown Report](report/VAPT_Report_Metasploitable.md)

---

## ⚠ Disclaimer
This project was performed strictly for **educational purposes** in a **legal lab environment**.  
No real-world systems were harmed or tested without authorization.

---

## 👤 Author
**Manas Jyoti Boro**  
Aspiring Cybersecurity Professional
