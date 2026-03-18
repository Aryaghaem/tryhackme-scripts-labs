# Log4j Attack Detection (HTTP Analysis)

## Lab
TryHackMe - Wireshark HTTP Analysis

## Objective
Detect and investigate a Log4j exploitation attempt within HTTP traffic and identify the attacker’s command-and-control (C2) connection.

## Tool
Wireshark

---

## Investigation Process

### 1. Identify suspicious HTTP POST request

Filter used:

http.request.method == "POST"

POST requests were inspected to locate abnormal payloads. A suspicious request containing "jndi" was identified, indicating a potential Log4j exploit attempt.

![Log4j POST request](screenshots/log4j-post-request.png)

---

### 2. Analyse exploit payload

The malicious request contained a Log4j payload using JNDI lookup:

${jndi:ldap://...}

This payload forces the server to contact an external system controlled by the attacker.

---

### 3. Decode attacker command

The payload included base64 encoded data. This data was decoded to reveal the destination IP address used by the attacker.

![Decoded IP](screenshots/base64-decoded-ip.png)

---

## Findings

The traffic confirms a Log4j exploitation attempt where a malicious JNDI payload was delivered via an HTTP POST request. The payload triggered outbound communication to an attacker-controlled IP address.

Key findings:

- Log4j exploit detected in HTTP POST request
- Presence of "jndi" payload indicating remote code execution attempt
- Base64 encoded command identified and decoded
- External IP address contacted by compromised system

---

## Skills Demonstrated

- HTTP traffic analysis
- Detection of Log4j exploitation patterns
- Payload inspection and decoding
- Identification of command-and-control (C2) communication
