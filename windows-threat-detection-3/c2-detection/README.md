# Command and Control (C2) Detection

## Lab
TryHackMe - Windows Threat Detection 3

## Objective
Investigate Sysmon logs to detect a C2 setup - finding the suspicious archive downloaded, the hidden malware file, and the C2 server domain.

## Tool
Windows Event Viewer (Sysmon logs)

---

## Investigation Process

### 1. Identify the suspicious archive downloaded

Event ID: 11

Filtered Sysmon for file creation events. Found `URGENT!.zip` written into the Downloads folder by `chrome.exe` - the initial phishing attachment that triggered the C2 setup. The urgency in the filename is itself a social engineering tell.

![Event ID 11 showing URGENT!.zip created in Downloads by Chrome](./screenshots/c2-archive-downloaded.png)

---

### 2. Find where the C2 malware was hidden

Event ID: 11

Continued reviewing file creation events. Found `powershell.exe` dropping `update.exe` into `C:\Users\Administrator\AppData\Roaming\` - a staging directory chosen because it is user writable and rarely inspected. Attackers do this so the C2 connection survives even if the original attachment is deleted, and the innocuous name helps it blend in.

![Event ID 11 showing update.exe dropped into AppData Roaming by PowerShell](./screenshots/c2-malware-hidden.png)

---

### 3. Identify the C2 server domain

Event ID: 22

Filtered Sysmon for DNS query events from the malware process. Found `update.exe` resolving `route.m365officesync.workers.dev` - the attacker's Command and Control server. The domain is built to impersonate Microsoft 365 infrastructure while actually sitting on a public developer platform.

![Event ID 22 showing update.exe resolving the C2 domain](./screenshots/c2-domain.png)

---

## Findings
- Suspicious archive `URGENT!.zip` downloaded via phishing
- C2 malware `update.exe` hidden in `AppData\Roaming` to survive deletion of the original file
- Malware resolved the external C2 domain `route.m365officesync.workers.dev`
- Full C2 setup traced using Event ID 11 and Event ID 22

---

## Skills Demonstrated
- Sysmon log analysis
- C2 detection via DNS query events
- Hidden malware file identification
- Event ID 11 and Event ID 22 correlation
