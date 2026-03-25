# RDP Brute Force Detection

## Lab
TryHackMe - Windows Initial Access

## Objective
Investigate Windows Security logs to detect an RDP brute force attack and identify the attacker.

## Tool
Windows Event Viewer

---

## Investigation Process

### 1. Detect the brute force
Event ID: 4625
Filtered Security logs for failed login attempts. Found a flood of 4625 events from a single external IP targeting common usernames — consistent with automated brute force.
![RDP Brute Force](./screenshots/rdp-bruteforce.png)

### 2. Confirm the breach
Event ID: 4624 — Logon Type 10
Switched filter to successful logins and filtered for Logon Type 10 (interactive RDP). Found a successful login from the same attacking IP shortly after the brute force.
![RDP Breach Confirmed](./screenshots/rdp-breach.png)

### 3. Identify attacker hostname
Located the Logon Type 3 event preceding the Logon Type 10 event. The Workstation Name field revealed the real hostname of the attacker's machine.
![Attacker Hostname](./screenshots/attacker-hostname.png)

---

## Findings
- Attacker IP launched automated brute force via RDP
- Brute force succeeded — confirmed by 4624 Logon Type 10
- Attacker's real machine hostname identified
- Logon ID saved for tracking post-access activity

---

## Skills Demonstrated
- Windows Security log analysis
- RDP brute force detection
- Logon Type filtering
- Attacker identification via event correlation

## Screenshots Needed
- rdp-bruteforce.png — flood of 4625 events from same IP
- rdp-breach.png — 4624 Logon Type 10 showing attacker IP
- attacker-hostname.png — Workstation Name in Logon Type 3 event
