# cybersecurity-portfolio
Hands-on cybersecurity projects focused on incident response, vulnerability management, IAM, and threat monitoring & analysis.

# Hi, I'm Marvelous Agunloye

Cybersecurity graduate specialising in incident response, digital forensics, and identity security — with hands-on experience across Windows, Linux, and hybrid cloud environments.

![GIAC](https://img.shields.io/badge/GIAC%20Certified%20(8×)-0078D4?style=flat&logoColor=white)
![Threat Detection](https://img.shields.io/badge/Threat%20Detection%20%26%20IR-1D9E75?style=flat&logoColor=white)
![IAM](https://img.shields.io/badge/IAM%20%26%20Entra%20ID-7F77DD?style=flat&logoColor=white)
![Platforms](https://img.shields.io/badge/Windows%20%26%20Linux-888780?style=flat&logoColor=white)
![Cloud](https://img.shields.io/badge/Azure%20%26%20AWS-BA7517?style=flat&logoColor=white)

---

## 📖 Portfolio Overview

This portfolio demonstrates a **balanced combination of hands-on labs, threat research, and technical write-ups**, providing real-world examples of:

- Threat detection & incident response  
- Vulnerability management and system hardening  
- Hybrid identity and access control implementation  
- Analytical and report-writing skills for security documentation  

---

## 🛠 Skills, Focus Areas & Toolset

- **Platforms:** Windows Server, Linux, Azure, AWS 
- **Incident Response & Digital Forensics**: Log analysis, packet capture, malware inspection  
- **Identity & Access Management (IAM)**: Active Directory and Entra ID configurations  
- **System Administration**: Windows Server, Linux, hybrid environments, hardening techniques  
- **Threat Monitoring & Analysis**: Honeypots, network monitoring
- **Tools:** Wazuh, Security Onion, Zeek, Wireshark, Metasploit, John the Ripper, Hashcat, tcpdump
- **Scripting & Automation**: Python, Bash, PowerShell

![Python](https://img.shields.io/badge/Python-3670A0?style=flat&logo=python&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat&logo=gnubash&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=flat&logo=powershell&logoColor=white)
![Wazuh](https://img.shields.io/badge/Wazuh-00A9E0?style=flat&logo=wazuh&logoColor=white)
![Security Onion](https://img.shields.io/badge/Security%20Onion-2E7D32?style=flat&logoColor=white)
![Zeek](https://img.shields.io/badge/Zeek-777BB4?style=flat&logoColor=white)
![Wireshark](https://img.shields.io/badge/Wireshark-017AFF?style=flat&logo=wireshark&logoColor=white)
![tcpdump](https://img.shields.io/badge/tcpdump-2C2D72?style=flat&logoColor=white)
![Metasploit](https://img.shields.io/badge/Metasploit-FF5C00?style=flat&logo=metasploit&logoColor=white)
![Burp Suite](https://img.shields.io/badge/Burp%20Suite-FF6633?style=flat&logo=burpsuite&logoColor=white)
![OWASP ZAP](https://img.shields.io/badge/OWASP%20ZAP-00549E?style=flat&logo=owasp&logoColor=white)
![Hashcat](https://img.shields.io/badge/Hashcat-A9225C?style=flat&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT%26CK-E31837?style=flat&logoColor=white)

![Active Directory](https://img.shields.io/badge/Active%20Directory-0078D4?style=flat&logo=microsoft&logoColor=white)
![Entra ID](https://img.shields.io/badge/Entra%20ID-0078D4?style=flat&logo=microsoft&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-0078D4?style=flat&logo=windows&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonwebservices&logoColor=white)

---

## 📁 Projects

### 1. 🖥️ Home Lab — Active Directory & Hybrid Domain
- Designed and deployed a hybrid **Windows + Linux domain environment**  
- Configured **Active Directory with DHCP & DNS, File Server, Certificate Authority, RDS**, with multi-platform domain joined devices
- Implemented host and network-based intrusion detection using Wazuh and Security Onion 
- Conducted vulnerability testing and exploitation using **Metasploit, John the Ripper, and Hashcat**

`Active Directory` `Wazuh` `Security Onion` `Metasploit`

[Read more →](./System-Hardening/README.md)

---

### 2. 🍯 Honeypot Threat Analysis — IoT Attack Surface
- Set up and deployed an internet-facing honeypot on **Raspberry Pi 4**  with SANS Cowrie server config and custom logs
- Monitored and captured attacks targeting IoT devices, performed traffic analysis, and extracted malware payloads  
- Mapped observations to MITRE ATT&CK techniques and documented prevention strategies
- Wrote a companion deep-dive on polyglot file abuse for stealth payload delivery.

`Cowrie` `MITRE ATT&CK` `Wireshark` `Malware Analysis`
  
- **Detailed observations & analyses**:  
  - [Attack Observations →](Honeypot-Threat-Analysis/Observations.md)  
  - [Blog Post on Polyglot File Research: When a GIF Isn't Just a GIF →](./BlogPosts/WhenAGIFIsntJustAGIF.md)
 
---

### 3. ☁️ Cloud IAM — Azure & AWS Security Configurations 
- Configured IAM policies, Conditional Access, and identity governance in Azure Entra ID and AWS environments.  
- Explored AD and Entra ID integrations, user lifecycle management, MFA enforcement and system hardening best practices

`Azure Entra ID` `AWS IAM` `Conditional Access`

---

### 4. 🌐 Web Application Security — Hometrumpeter Inc.
- Supported a real-world security assessment aligned with OWASP Top 10.  
- Identified and documented issues related to:
  - Authentication and authorization weaknesses  
  - Input validation and injection risks  
  - Insecure configurations via manual and automated testing  
- Delivered risk-rated findings with actionable remediation guidance for the development team

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Burp Suite](https://img.shields.io/badge/Burp%20Suite-FF5722?style=flat&logo=burpsuite&logoColor=white)
![OWASP ZAP](https://img.shields.io/badge/OWASP%20ZAP-0C4DA2?style=flat&logo=owasp&logoColor=white)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE%20ATT--CK-FF0000?style=flat)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)

[Read more →](./Web-App-Security/README.md)

---

## Blog: When a GIF Isn’t Just a GIF
- Analysis of polyglot files used for stealth malware delivery in IoT devices  
- Demonstrated RCE payload detection, file carving, and defensive measures  

[Read Blog →](BlogPosts/WhenAGIFIsntJustAGIF.md)

---

## 🔗 Certifications

| Certification | Issuer | Status |
|---|---|---|
| GCFE — Certified Forensic Examiner | GIAC | ✅ [Verify](https://www.credly.com/badges/6b27b413-e4eb-42ac-a6c9-5c755b8272ae/public_url) |
| GMON — Threat Detection & Monitoring | GIAC | ✅ [Verify](https://www.credly.com/badges/3ccdafed-be03-498b-a217-086d0bc8d194/public_url) |
| GCIA — Certified Intrusion Analyst | GIAC | ✅ [Verify](https://www.credly.com/badges/1140c87d-8fdb-40c1-bc76-5b5dba6124c3/public_url) |
| GCIH — Certified Incident Handler | GIAC | ✅ [Verify](https://www.credly.com/badges/87598346-8263-48e6-ae87-73a2a64d5765/public_url) |
| GSEC — Security Essentials | GIAC | ✅ [Verify](https://www.credly.com/badges/bdb5d38d-5a6f-4d2e-8ab4-7f8c2ea6b771/public_url) |
| GPYC — Python Coder | GIAC | ✅ [Verify](https://www.credly.com/badges/0e5a995e-3c7e-4ad5-b17d-c9cf4ed3f90d/public_url) |
| GFACT — Foundational Cybersecurity Technologies | GIAC | ✅ [Verify](https://www.credly.com/badges/aa8e5ff3-d268-40ec-8163-246c705b865c/public_url) |
| GISF — Information Security Fundamentals | GIAC | ✅ [Verify](https://www.credly.com/badges/bcaa2d68-6a6a-4860-b016-9e73f4cdeee0/public_url) |
| CompTIA Network+ | CompTIA | ✅ [Verify](https://www.credly.com/badges/236a9ccc-8e5a-48de-9efe-96fb3f195e9c/public_url) |
| CompTIA A+ | CompTIA | ✅ [Verify](https://www.credly.com/badges/9979cc3b-95b6-45da-9a14-55fc7b5f61c9/public_url) |
| SC-900 — Security, Compliance & Identity | Microsoft | ✅ Certified |
| AZ-900 — Azure Fundamentals | Microsoft | ✅ [Verify](https://www.credly.com/badges/4152e791-fdc2-4037-abaa-9af30ac0cdbb) |
| DP-900 — Azure Data Fundamentals | Microsoft | ✅ [Verify](https://www.credly.com/badges/00b9fc8b-7001-4369-ba17-4c87be11ed84) |
| SC-300 — Identity & Access Administrator | Microsoft | ⏳ In progress |
| GWAPT — Web App Penetration Testing and Ethical Hacking | GIAC | ⏳ In progress |

[Certificate Verification →](Certifications/README.md)

---

## Let's connect

I'm actively looking for roles in SOC analysis, incident response, and identity security. If you're hiring or just want to talk security, reach out.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0078D4?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/marv-wip)
[![GitHub](https://img.shields.io/badge/GitHub-24292e?style=flat&logo=github&logoColor=white)](https://github.com/magunloye1)
