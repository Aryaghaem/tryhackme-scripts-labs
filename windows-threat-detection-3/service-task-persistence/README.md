# Malicious Service and Scheduled Task Detection

## Lab
TryHackMe - Windows Threat Detection 3

## Objective
Investigate Security logs to detect malware persistence via a malicious Windows service and a malicious scheduled task.

## Tool
Windows Event Viewer (Security logs)

---

## Investigation Process

### 1. Detect malicious Windows service

Event ID: 4697

Filtered Security logs for service creation events. Found a new service created to run the Nessie malware automatically on every system boot.

![Malicious Service Created](./screenshots/malicious-service-created.png)

---

### 2. Detect malicious scheduled task

Event ID: 4698

Filtered Security logs for scheduled task creation events. Found a new task created to run the Troy malware automatically on system startup.

![Malicious Task Created](./screenshots/malicious-task-created.png)

---

## Findings
- Malicious Windows service created to run Nessie malware on boot
- Malicious scheduled task created to run Troy malware on startup
- Both persistence methods survive system reboots
- Detected via Security Event ID 4697 and 4698

---

## Skills Demonstrated
- Windows Security log analysis
- Malicious service detection via Event ID 4697
- Malicious scheduled task detection via Event ID 4698
- Persistence mechanism identification
