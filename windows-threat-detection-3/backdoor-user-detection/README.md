# Backdoor User Account Detection

## Lab
TryHackMe - Windows Threat Detection 3

## Objective
Investigate Windows Security logs to detect a backdoor user account created by an attacker after RDP brute force, and identify privilege escalation activity.

## Tool
Windows Event Viewer (Security logs)

---

## Investigation Process

### 1. Detect the backdoor user created

Event ID: 4720

Filtered Security logs for user creation events. Found a new account created shortly after the attacker's successful RDP login — this was the backdoor account created for persistent access.

![Backdoor User Created](./screenshots/backdoor-user-created.png)

---

### 2. Detect privilege escalation

Event ID: 4732

Filtered for group membership events. Found the backdoor account being added to a privileged group, giving the attacker administrative access to the machine.

![Backdoor Group Added](./screenshots/backdoor-group-added.png)

---

## Findings
- Attacker brute forced RDP before gaining access
- Backdoor user account created shortly after successful login
- Backdoor account added to privileged group for full admin access
- Attack chain confirmed using Security event log correlation

---

## Skills Demonstrated
- Windows Security log analysis
- Backdoor account detection via Event ID 4720
- Privilege escalation detection via Event ID 4732
- Brute force detection via Event ID 4625
