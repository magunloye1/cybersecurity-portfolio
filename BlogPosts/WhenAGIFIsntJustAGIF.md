# When a GIF Isn’t Just a GIF – Polyglot Files and Hidden IoT Exploits

**Date:** September 2025  
**Author:** Marvelous Agunloye  

During honeypot monitoring, several seemingly harmless image files (GIFs and JPEGs) were discovered to contain **embedded malicious code**. These “polyglot files” blend two or more file types, allowing attackers to bypass standard upload filters and malware scanners.

---

## What Are Polyglot Files?

A polyglot file is valid in multiple formats simultaneously. While they have legitimate uses (cross-compatibility, testing), attackers leverage them for:

- Malware delivery  
- Remote code execution  
- File upload exploitation  
- Defense evasion and obfuscation  

**Examples of malicious polyglot formats:**

| Covert Format | Overt Format |
|---------------|-------------|
| PHP | GIF, JPEG, PNG, ZIP |
| PHAR | GIF, JPEG |
| JavaScript | GIF, BMP |
| PowerShell | JPEG, GIF |
| ZIP | JPEG, GIF, PDF |

---

## Observed Payloads

The honeypot captured several malicious uploads. Key payloads included:

| File Type | Payload Summary | Threat |
|-----------|----------------|--------|
| GIF | PHP script: `<?php echo md5("CVE-2020-28871"); unlink(__FILE__); ?>` | Self-deleting remote code execution |
| JPEG | Base64-encoded PHP decoded to: `<?php echo md5('uuyang');unlink(__FILE__);?>` | RCE, stealth persistence |
| ZIP | Contained PHP/JSP web shells (`EeXi3.php`, `.jsp`) | Remote write access, malware staging |

These payloads indicate attempts to **install trojans, achieve RCE, and bypass detection** using file obfuscation.

---

## Detection & Analysis Techniques

To identify polyglot threats:

- Network packet capture with **tcpdump**  
- Analysis with **Zeek** and **Wireshark**  
- File extraction/carving using `extract-all-files.zeek`  
- Base64 decoding with **CyberChef**  
- Malware scanning with **ClamAV** or YARA  

---

## Lessons Learned

- File extensions alone are insufficient for security checks.  
- Strict validation, MIME inspection, and behavioral analysis are necessary.  
- IoT devices and web services must enforce **secure file handling** and **segmented networks**.  
- Intrusion detection (Zeek, Suricata) and anti-malware scanning are essential defenses.  

---

## Conclusion

Polyglot files are a potent attack vector that can hide malware in plain sight. Monitoring, deep file inspection, and proactive controls are critical for IoT and web service security.

[Back to Attack Observations →](../Honeypot-Threat-Analysis/Observations.md)

