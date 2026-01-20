# Nmap Web Server Enumeration

## Overview
In this lab, I used Nmap to enumerate open TCP ports and identify services running on a target host.

## Tools Used
- Nmap
- Web browser

## Steps Performed
- Ran a TCP SYN scan to identify open ports
- Used service/version detection to identify running services
- Discovered a web server running on the target
- Accessed the web server and retrieved a flag from the main page

## Key Findings
- 6 TCP ports were open on the target system
- A web server was identified along with its version
- The web service was accessible via a browser

## SOC Relevance
- Port scanning is used to identify exposed services
- Service enumeration helps assess attack surface
- Open web services are common initial access points
