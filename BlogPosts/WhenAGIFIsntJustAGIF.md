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
| ZIP | Contained PHP/JSP web shells (`EeXi3.php`, `0MVzAe6pgwe5go1D.jsp`) | Gain persistence and remote write access to web directories, malware staging |

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

## Key Takeaways

- Payloads were embedded to bypass extension filters and content validation.
- Attacks leveraged RCE techniques and attempted to establish persistent access.
- Many payloads were designed to self-delete after execution, leaving minimal forensic traces.

---

## Lessons Learned

- File extensions alone are insufficient for security checks.  
- Deeper inspection(MIME type, magic bytes and file content) and strict validation, and behavioral analysis are necessary.
- Monitoring web server logs and network traffic (via Zeek, Wireshark) is critical to detect stealthy attacks.
- IoT devices and web services with upload functionality are particularly vulnerable and must enforce **secure file handling** and **segmented networks**.  
- Intrusion detection (Zeek, Suricata) and anti-malware scanning are essential defenses.  

---

## Conclusion

Polyglot files are a potent attack vector that can hide malware in plain sight. Monitoring, deep file inspection, and proactive controls are critical for IoT and web service security.

## References

1.  [MITRE ATT&CK - Defense Evansion](https://attack.mitre.org/tactics/TA0005/)
2.  [MITRE ATT&CK – Obfuscated Files or Information](https://attack.mitre.org/techniques/T1027/)
3.  [Polyglot Files – Security Threat Overview](https://wnesecurity.com/what-are-polyglot-files-and-how-do-hackers-use-them/)
4.  [Analyzing Embedded PHP in GIFs](https://thesecmaster.com/blog/what-are-polyglot-files-is-it-legit-or-security-threat)
5.  [Where the Polyglots Are: How Polyglot Files Enable Cyber Attack Chains and Methods for Detection & Disarmament - PDF file](https://arxiv.org/pdf/2407.01529)
6.  [Polyglot Files: a Hacker's best friend](https://medium.com/swlh/polyglot-files-a-hackers-best-friend-850bf812dd8a)

[Back to Attack Observations →](../Honeypot-Threat-Analysis/Observations.md)

