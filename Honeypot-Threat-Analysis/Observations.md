# Honeypot Attack Observations

This document summarizes attacks observed and analyzed during honeypot deployment on a Raspberry Pi 4 and other lab environments.  
The goal is to demonstrate practical skills in **incident response, network monitoring, file carving and IoT/Windows exploitation analysis**.

---

## Honeypot Deployment & Initial Configuration

**Date:** N/A  
**Environment:** Raspberry Pi 4, Raspberry Pi OS 64-bit

**Summary:**  
- Configured an internet-facing honeypot using SANS Cowrie for SSH/Telnet and a web server.  
- Integrated logging with the SANS Internet Storm Center (ISC).  
- Challenges included initial network connectivity issues with the 32-bit OS and occasional device restarts.  

**Skills Demonstrated:**  
- Linux configuration & hardening  
- Firewall & router configuration for controlled exposure  
- Host-based and network-based logging setup  

---

## Observation 1: IoT Brute Force & Exploit Attempts

**Date:** June 18–19, 2025  
**Target:** Legacy IoT devices (ZTE, Huawei, D-Link, GPON modems)  
**Payload Type:** Brute force login, command injection  

**Summary:**  
- Detected multiple IPs attempting access to `/boaform/admin/formLogin` and `/cgi-bin/luci/;stok=/locale`.  
- Payloads aimed to gain administrative access and execute system commands remotely.  
- Correlated with firewall logs and ISC reports to identify attacker patterns.  

**MITRE ATT&CK Techniques:**  
- T1078 — Valid Accounts (brute force)  
- T1190 — Exploit Public-Facing Application  
- T1059.004 — Command and Scripting Interpreter: Unix Shell  
- T1105 — Ingress Tool Transfer  

**Prevention Measures:**  
- Retire or replace vulnerable IoT devices  
- Restrict management interfaces to LAN only  
- Apply firewall/ACL restrictions and continuous monitoring  

---

## Observation 2: Remote Command Execution via Web Forms

**Date:** August 23, 2025  
**Target:** IoT devices with exposed `/goform/mp` interface  
**Payload Type:** Remote code execution (wget shell script download)  

**Summary:**  
- Captured network traffic using tcpdump, analyzed with Zeek & Wireshark.  
- Identified HTTP POST requests attempting to download and execute malicious scripts.  
- Indicators included suspicious user agents and known malicious IPs.  

**MITRE ATT&CK Techniques:**  
- T1190 — Exploit Public-Facing Application  
- T1059 — Command and Scripting Interpreter  
- T1105 — Ingress Tool Transfer  

**Preventive Actions:**  
- Regular firmware updates  
- IoT network segmentation  
- Block connections to known malicious domains/IPs  

---

## Observation 3: Polyglot File Exploitation & Malware Delivery

**Date:** September 01, 2025  
**Target:** Web services accepting file uploads  
**Payload Type:** Polyglot files, embedded PHP/JSP scripts, trojans  

**Summary:**  
- Analyzed pcap files to extract unusual MIME types (GIF, JPEG, ZIP, PHP, JSP).  
- Found embedded payloads for remote code execution and stealth malware installation.  
- Demonstrated techniques like file carving, base64 decoding, and behavioral analysis.  

**Key Findings:**  
| File Type | Payload Summary | Risk |
|-----------|----------------|------|
| GIF | PHP script executing MD5 & self-delete | RCE |
| JPEG | Base64-encoded PHP script | RCE |
| ZIP | PHP/JSP web shells | Remote write access & persistence |

**MITRE ATT&CK Techniques:**  
- T1190 — Exploit Public-Facing Application  
- T1059 — Command and Scripting Interpreter  
- T1105 — Ingress Tool Transfer  
- T1071.001 — Application Layer Protocol: Web

**Defensive Measures:**  
- Enforce file validation, MIME type checks  
- Disable execution in upload directories  
- Use intrusion detection (Zeek, Suricata) and anti-malware/YARA scans  

---

## Summary

These observations showcase a mix of **hands-on lab setup, attack detection, and threat analysis skills**, highlighting:

- IoT and web application exploitation detection  
- Network traffic and log analysis  
- Malware extraction and forensic review  
- Use of MITRE ATT&CK framework to classify threats  

[Back to Portfolio →](../README.md)
