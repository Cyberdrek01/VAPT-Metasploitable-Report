# 🔐 Vulnerability Assessment & Penetration Testing (VAPT) Report

**Date:** January 2, 2026  
**Target System:** 192.168.1.4 (Metasploitable)  
**Assessment Type:** Internal Penetration Test  
**Assessor:** Manas Jyoti Boro  
**Tools Used:** Nmap, Metasploit Framework, Netcat  

---

## 1. Executive Summary

An internal Vulnerability Assessment and Penetration Test (VAPT) was conducted against the target host **192.168.1.4**, a deliberately vulnerable system (Metasploitable), to evaluate its security posture.

The assessment identified multiple **Critical severity vulnerabilities** that enabled **unauthorized remote code execution and full system compromise**. The assessment successfully bypassed authentication controls and obtained **root (administrative) access** using **two independent attack vectors**.

These findings highlight severe misconfigurations and outdated services. Immediate remediation is required to prevent exploitation in real-world environments.

---

## 2. Scope & Methodology

### Scope
- Single internal host: `192.168.1.4`
- Controlled lab environment
- No denial-of-service attacks performed

### Methodology
1. Reconnaissance & Port Scanning
2. Service Enumeration
3. Vulnerability Identification
4. Exploitation
5. Privilege Escalation Verification
6. Reporting & Remediation

---

## 3. Summary of Findings

| ID | Vulnerability Name | Severity | Status |
|----|------------------|----------|--------|
| FIND-01 | vsftpd v2.3.4 Backdoor Command Execution | Critical | Exploited |
| FIND-02 | Samba “Usermap Script” Remote Code Execution | Critical | Exploited |
| FIND-03 | Unprotected Bind Shell (Port 1524) | Critical | Verified |

---

## 4. Technical Findings

---

### 🔴 FIND-01: vsftpd v2.3.4 Backdoor Command Execution

- **Service:** FTP  
- **Port:** 21/TCP  
- **CVSS Score:** 10.0 (Critical)

#### Description
The target system was running **vsftpd version 2.3.4**, which contains a malicious backdoor introduced through a historical supply-chain compromise. A specially crafted username triggers a shell listener on **port 6200**.

#### Impact
Successful exploitation provides **root-level access**, leading to complete system compromise.

#### Proof of Concept
Metasploit module used: exploit/unix/ftp/vsftpd_234_backdoor

Observed output: 
[*] Command shell session opened
uid=0(root) gid=0(root)



---

### 🔴 FIND-02: Samba “Usermap Script” Remote Code Execution

- **Service:** SMB  
- **Ports:** 139, 445/TCP  
- **CVSS Score:** 9.0 (Critical)

#### Description
The Samba service was misconfigured with the `username map script` option enabled. This allows command injection via the username field during authentication, resulting in **arbitrary command execution as root**.

#### Impact
Unauthenticated attackers can execute system commands and establish reverse shells.

#### Proof of Concept
Metasploit module used: exploit/multi/samba/usermap_script


Observed output: 
[] Started reverse TCP handler
[] Command shell session opened

---

### 🔴 FIND-03: Unprotected Bind Shell

- **Port:** 1524/TCP  
- **Severity:** Critical

#### Description
An unsecured bind shell was discovered listening on port **1524**, allowing direct shell access without authentication.

#### Impact
This backdoor provides immediate unauthorized system access.
This service is commonly left behind as a debugging or backdoor mechanism and represents a severe security misconfiguration.

---

## 5. Risk Assessment

The vulnerabilities identified pose an **extreme risk** to confidentiality, integrity, and availability. Exploitation requires minimal technical effort and can be performed remotely, making the system highly vulnerable.

---

## 6. Recommendations & Remediation

### Immediate Actions

#### Patch Management
- Upgrade **vsftpd** to version 3.0.3 or later.
- Update **Samba** to a supported and patched release.

#### Configuration Hardening
- Remove `username map script` from `smb.conf`.
- Disable anonymous FTP access.
- Remove unauthorized bind shells.

#### Network Security
- Restrict access to ports **21, 139, 445, and 1524** using firewall rules.
- Apply network segmentation to limit lateral movement.
---
## 7. Skills Demonstrated

- Network and service enumeration using Nmap
- Vulnerability identification and analysis
- Exploitation using Metasploit Framework
- Understanding of CVSS severity ratings
- Post-exploitation privilege verification
- Professional penetration testing reporting

---

## 8. Conclusion

The penetration test demonstrated that the target system is **critically insecure** and vulnerable to complete compromise via multiple attack paths. Implementing the recommended remediation steps will significantly enhance the system’s security posture.

---

## 9. Legal Disclaimer

This assessment was conducted **strictly for educational purposes** in a controlled lab environment on an intentionally vulnerable system.  
Unauthorized testing of systems without permission is illegal. The author assumes no responsibility for misuse of this information.

---

**Author:**  
**Manas Jyoti Boro**  
Aspiring Cybersecurity Professional


