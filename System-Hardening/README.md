# Home Lab — Active Directory & Hybrid Domain Environment

A multi-VM home lab built on Oracle VirtualBox, simulating a real-world hybrid Windows/Linux enterprise network. The environment spans domain infrastructure, certificate services, remote access, file services, network monitoring, and offensive security tooling — all isolated on an internal network (`LocalNet`) with NAT for internet access.

---

## Lab Architecture

| VM | OS | Role |
|---|---|---|
| LAB-DC | Windows Server (upgraded → 2022) | Primary Domain Controller, AD DS, DHCP, DNS |
| LAB-DCII | Windows Server 2022 | Upgraded DC — in-place OS upgrade from Server 2019 |
| LAB-CA | Windows Server 2019 | Certificate Authority (AD CS) |
| LAB-FS | Windows Server 2019 | File Server, GPO management |
| LAB-RDS | Windows Server 2019 | Remote Desktop Services |
| WORKSTATION | Windows 11 | Domain-joined Windows 11 client |
| WORKSTATION-WIN10 | Windows 10 | Domain-joined Windows 10 client |
| WORKSTATION-LINUX | Linux | Domain-joined Linux endpoint |
| WORKSTATION-KALI | Kali Linux | Attack machine / penetration testing |
| WORKSTATION-KALI Clone | Kali Linux | Secondary attack instance |
| KALI-BHP | Kali Linux | Black Hat Python tooling & scripting |
| WORKSTATION-SIFT | SIFT Workstation | Digital forensics & incident response |
| Security Onion 2.4 | Security Onion | Network security monitoring & IDS |

**Hypervisor:** Oracle VirtualBox  
**Network:** NAT (internet access) + Internal Network (`LocalNet`) for isolated lab traffic  

---

## What Was Built

### Active Directory & Domain Controller

- Deployed Active Directory Domain Services (AD DS) on `LAB-DC`
- Configured DHCP and DNS for the internal domain
- Joined Windows 10, Windows 11, and Linux workstations to the domain
- Created Organisational Units (OUs), user accounts, and security groups reflecting a realistic enterprise structure
- Applied and tested Group Policy Objects (GPOs) for desktop lockdown, password policies, and software restriction

### Domain Controller In-Place Upgrade

- Performed an in-place upgrade of the primary DC from **Windows Server 2019 to Windows Server 2022** (`LAB-DCII`)
- Validated AD replication, FSMO role transfer, and domain health post-upgrade
- Tested client connectivity and policy application after the transition

### Certificate Authority (AD CS)

- Deployed an Enterprise CA on `LAB-CA` integrated with Active Directory
- Issued certificates for internal services and domain-joined machines
- Configured auto-enrollment via GPO for domain workstations

### File Server & GPO Management

- Configured shared folders and NTFS permissions on `LAB-FS` with role-based access control
- Applied and audited file access policies through Group Policy
- Tested access controls across domain users with varying privilege levels

### Remote Desktop Services

- Deployed RDS on `LAB-RDS` for centralised remote access to the domain environment
- Configured RDS licensing and session host settings

### Network Monitoring — Security Onion 2.4

- Deployed Security Onion 2.4 on the internal network to capture and analyse lab traffic
- Configured interface mirroring to monitor east-west traffic across VMs
- Used Zeek for protocol-level logging and Suricata for signature-based IDS alerting
- Reviewed alerts and logs via the Security Onion web console (SOC interface)

### Host-Based Detection — Wazuh

- Deployed Wazuh agents on domain-joined Windows and Linux endpoints
- Centralised log collection, file integrity monitoring, and security event correlation
- Configured active response rules and reviewed alert dashboards

### Offensive Tooling & Validation

- Used **WORKSTATION-KALI** and clones to simulate attacker activity within the `LocalNet`
- Ran Metasploit modules against lab targets to validate detection coverage in Security Onion and Wazuh
- Used **KALI-BHP** (Black Hat Python) for custom scripting and tool development against lab services
- Used **WORKSTATION-SIFT** for forensic analysis of artifacts generated during simulated attacks — including log review, memory analysis, and file carving

---

## Key Skills Demonstrated

![Active Directory](https://img.shields.io/badge/Active%20Directory-0078D4?style=flat&logo=microsoft&logoColor=white)
![Windows Server 2022](https://img.shields.io/badge/Windows%20Server%202022-0078D4?style=flat&logo=windows&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Security Onion](https://img.shields.io/badge/Security%20Onion-2E7D32?style=flat&logoColor=white)
![Wazuh](https://img.shields.io/badge/Wazuh-00A9E0?style=flat&logo=wazuh&logoColor=white)
![Zeek](https://img.shields.io/badge/Zeek-777BB4?style=flat&logoColor=white)
![Metasploit](https://img.shields.io/badge/Metasploit-FF5C00?style=flat&logo=metasploit&logoColor=white)
![Kali Linux](https://img.shields.io/badge/Kali%20Linux-557C94?style=flat&logo=kalilinux&logoColor=white)
![SIFT](https://img.shields.io/badge/SIFT%20Workstation-2C2D72?style=flat&logoColor=white)
![VirtualBox](https://img.shields.io/badge/VirtualBox-183A61?style=flat&logo=virtualbox&logoColor=white)
![Python](https://img.shields.io/badge/Python-3670A0?style=flat&logo=python&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=flat&logo=powershell&logoColor=white)
![GPO](https://img.shields.io/badge/Group%20Policy-0078D4?style=flat&logo=microsoft&logoColor=white)
![AD CS](https://img.shields.io/badge/AD%20CS-0078D4?style=flat&logo=microsoft&logoColor=white)

---

## Lessons & Takeaways

- **DC upgrade complexity** — an in-place domain controller upgrade requires careful FSMO role planning and post-upgrade health validation; replication issues will silently break things if not checked
- **Detection coverage gaps** — running attacker tools against the lab revealed that default Wazuh and Security Onion configurations miss many techniques; tuning alert thresholds and writing custom rules is essential
- **GPO as a hardening tool** — Group Policy is underutilised in many environments; applying CIS benchmark-aligned GPOs significantly reduces the attack surface on domain-joined workstations
- **Linux domain join quirks** — integrating Linux endpoints into Active Directory via SSSD/Kerberos surfaces edge cases around DNS resolution and Kerberos ticket caching that don't appear on Windows clients
- **Network segmentation matters** — even in a lab, separating attacker VMs from the production domain network via the internal `LocalNet` reinforced the value of network segmentation in real deployments

---

## Related Projects

- [Honeypot Threat Analysis](../Honeypot-Threat-Analysis/README.md)
- [Cloud & IAM — Azure & AWS](../Cloud-IAM/README.md)
- [Web Application Security](../Web-App-Security/README.md)
