# Wireshark Advanced Filtering Analysis

## Lab Overview

This lab demonstrates advanced filtering techniques using Wireshark.

The objective was to analyze packet captures using operators such as:
- contains
- in
- mathematical filtering
- checksum analysis

Tool used:
- Wireshark

---

## Investigation 1: Microsoft IIS Servers

Filter used:

http.server contains "IIS"

Purpose:

Identify HTTP packets where the web server is Microsoft IIS.

Screenshot:

![IIS Servers](screenshots/iis-servers.png)

---

## Investigation 2: Microsoft IIS Version 7.5

Filter used:

http.server contains "IIS/7.5"

Purpose:

Identify packets from IIS servers running version 7.5.

Screenshot:

![IIS Version](screenshots/iis-version-75.png)

---

## Investigation 3: Suspicious Port Usage

Filter used:

tcp.port in {3333 4444 9999}

Purpose:

Detect packets using uncommon or potentially suspicious ports.

Screenshot:

![Suspicious Ports](screenshots/suspicious-ports.png)

---

## Investigation 4: Even TTL Packets

Filter used:

ip.ttl % 2 == 0

Purpose:

Analyze packets based on TTL values to demonstrate filtering using mathematical operators.

Screenshot:

![Even TTL](screenshots/even-ttl.png)

---

## Investigation 5: Bad TCP Checksums

Filter used:

tcp.checksum_bad == 1

Purpose:

Detect packets with incorrect TCP checksums which may indicate corruption or network anomalies.

Screenshot:

![Bad Checksum](screenshots/bad-tcp-checksum.png)

---

## Skills Demonstrated

- Packet analysis
- Network protocol investigation
- Advanced Wireshark filtering
- Network anomaly detection
