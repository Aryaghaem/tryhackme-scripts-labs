# 🛡️ Cybersecurity & IT Learning Portfolio

Hello! I'm an aspiring IT professional and SOC analyst based in Auckland, NZ,
working toward a career in cybersecurity and system administration.

This repository documents my hands-on learning through TryHackMe labs,
homelabs, and practical IT fundamentals.

---

## What I've Learned

**Security Tools & Concepts:**
- Network analysis (Wireshark, packet inspection, protocol analysis)
- Windows event log analysis and correlation
- Sysmon for process monitoring and threat detection
- PowerShell for system administration and forensics
- MITRE ATT&CK framework for threat classification
- Incident response workflows and log investigation
- SIEM fundamentals (log aggregation, alerting)
- DNS tunneling and ARP MITM attack detection
- Log4j vulnerability exploitation and detection

**IT Fundamentals:**
- Windows Server administration and configuration
- System monitoring and performance troubleshooting
- Command-line tools (PowerShell, Bash, Linux fundamentals)
- Network troubleshooting and enumeration (FTP, Nmap, Telnet, POP3)
- Security best practices and hardening

---

## SOC Analyst & Security Labs

### Windows Initial Access
- [Phishing Sysmon Analysis](./windows-initial-access/phishing-sysmon-analysis) - malware detection through process monitoring
- [USB Malware Analysis](./windows-initial-access/usb-malware-analysis) - USB propagation and execution detection

### Windows Security Monitoring
- [User Backdoor Detection](./windows-security-monitoring/user-backdoor-detection) - detecting unauthorized user creation and privilege escalation
- [Process Analysis with Sysmon](./windows-security-monitoring/process-analysis-sysmon) - analyzing browser processes, downloaded files, and network connections

### Windows Threat Detection
- [Detecting Discovery Commands](./windows-threat-detection/detecting-discovery) - identifying reconnaissance and defense evasion techniques
- [Detecting Data Stealer Collection](./windows-threat-detection/detecting-collection) - clipboard theft and data exfiltration detection

### Windows Threat Detection 3
- [Backdoor User Detection](./windows-threat-detection-3/backdoor-user-detection) - unauthorized account creation and access patterns
- [C2 Detection](./windows-threat-detection-3/c2-detection) - command and control communications identification
- [Service & Task Persistence](./windows-threat-detection-3/service-task-persistence) - malicious service and scheduled task detection
- [Startup Folder & Run Key Persistence](./windows-threat-detection-3/startup-runkey-persistence) - registry persistence mechanism detection

### Wireshark Network Analysis
- [Advanced Filters](./wireshark/advanced-filters) - TCP checksum validation, TTL analysis, version detection
- [ARP MITM Investigation](./wireshark/arp-mitm-investigation) - man-in-the-middle attack detection and credential theft analysis
- [DNS Tunneling Detection](./wireshark/dns-tunneling-detection) - identifying data exfiltration via DNS queries
- [Log4j Attack Detection](./wireshark/log4j-attack-detection) - detecting Log4j RCE exploitation attempts
- [Protocol Filters](./wireshark/protocol-filters) - DNS, HTTP, and TCP port analysis

### Email & PDF Analysis
- [Reconstructing PDF from Base64](./email-analysis/reconstructing-pdf-from-base64) - CyberChef recipe for decoding and analyzing encoded files

### File and Hash Intelligence
- [Threat Intelligence Challenge](./file-hash-intelligence/threat-intelligence-challenge) - independent file analysis and hash reputation lookup

### Linux & Bash
- [Linux and Bash Scripting](./linux-bash) - flag hunting, log searching, and system automation scripts

### Network Enumeration
- [FTP Enumeration](./networking/ftp-enumeration) - file transfer protocol reconnaissance and flag retrieval
- [Nmap Web Enumeration](./networking/nmap-web-enumeration) - service detection and web server identification
- [POP3 Enumeration](./networking/pop3-enumeration) - email protocol reconnaissance
- [Telnet HTTP](./networking/telnet-http) - legacy protocol analysis and HTTP communication

---

## Current Progress

- **TryHackMe SOC Level 1:** In progress (~25+ labs completed)
- **Certifications:** Google Cybersecurity Certificate (completed), Security+ (in progress), Level 4 IT
- **Homelabs:** Windows Server, PowerShell scripting, system administration practice
- **Real-world experience:** 2 weeks shadowing a senior systems administrator

---

## Goals

- Complete TryHackMe SOC Level 1 certification
- Pass CompTIA Security+ exam
- Transition into a Junior SOC Analyst or IT Support role
