# Startup Folder and Run Key Persistence Detection

## Lab
TryHackMe - Windows Threat Detection 3

## Objective
Investigate Sysmon logs to detect malware persistence via the Windows startup folder and registry Run keys.

## Tool
Windows Event Viewer (Sysmon logs)

---

## Investigation Process

### 1. Detect startup folder persistence

Event ID: 11

Filtered Sysmon for file creation events in the Startup folder path. Found the Odin malware being dropped there — meaning it would run automatically every time the user logged in.

![Startup Folder Persistence](./screenshots/startup-folder-persistence.png)

---

### 2. Detect Run key persistence

Event ID: 13

Filtered Sysmon for registry value change events. Found a new entry being added to the Windows Run key pointing to the Kitten malware file path — meaning it would run automatically on every user login.

![Run Key Persistence](./screenshots/run-key-persistence.png)

---

## Findings
- Odin malware dropped into startup folder for automatic execution on login
- Kitten malware added to registry Run key for automatic execution on login
- Both methods only require normal user permissions — no admin needed
- Detected via Sysmon Event ID 11 and Event ID 13

---

## Skills Demonstrated
- Sysmon log analysis
- Startup folder persistence detection via Event ID 11
- Registry Run key persistence detection via Event ID 13
- Low privilege persistence technique identification
