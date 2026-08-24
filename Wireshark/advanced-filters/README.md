# Wireshark Advanced Filtering Analysis

## Lab Overview

This lab demonstrates advanced filtering techniques using Wireshark.

The objective was to analyse a packet capture (`Exercise.pcapng`) using operators such as:
- `contains` and `matches`
- set membership with `in`
- mathematical and string filtering
- checksum analysis

Tool used:
- Wireshark

---

## Investigation 1: Microsoft IIS Servers

Filter used:

```
http.server contains "IIS" && !(tcp.srcport==80)
```

Purpose:

Identify HTTP responses where the server header advertises Microsoft IIS, excluding traffic sourced from port 80 so the results focus on the non-standard listeners.

Screenshot:

![IIS servers matched by the http.server filter](screenshots/iis-servers.png)

---

## Investigation 2: Microsoft IIS Version 7.5

Filter used:

```
http.server contains "IIS" && http.server matches "7.5"
```

Purpose:

Narrow the previous result set to IIS servers running version 7.5, combining `contains` for the product name with `matches` for the version string.

Screenshot:

![IIS 7.5 responses isolated by the combined filter](screenshots/iis-version-75.png)

---

## Investigation 3: Suspicious Port Usage

Filter used:

```
tcp.port in {3333 4444 9999}
```

Purpose:

Detect traffic on uncommon ports frequently associated with backdoors and reverse shells, using the `in` operator to match a set of ports in a single expression.

Screenshot:

![TCP traffic on ports 3333, 4444 and 9999](screenshots/suspicious-ports.png)

---

## Investigation 4: Even TTL Packets

Filter used:

```
string(ip.ttl) matches "[02468]$"
```

Purpose:

Filter packets by TTL value, converting the numeric field to a string so a regular expression can match the trailing digit and isolate even TTLs.

Screenshot:

![Packets filtered to even TTL values](screenshots/even-ttl.png)

---

## Investigation 5: Bad TCP Checksums

Filter used:

```
tcp.checksum.status == 0
```

Purpose:

Detect packets with an invalid TCP checksum, which may indicate corruption, tampering, or checksum offloading on the capturing host.

Screenshot:

![TCP packets flagged with an incorrect checksum](screenshots/bad-tcp-checksum.png)

---

## Skills Demonstrated

- Packet analysis
- Network protocol investigation
- Advanced Wireshark filtering with `contains`, `matches` and `in`
- Network anomaly detection
