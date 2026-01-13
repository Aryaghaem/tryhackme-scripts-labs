# POP3 Enumeration and Email Retrieval

Used the POP3 protocol to authenticate to a mail server and retrieve email messages.

## What I did
- Connected to a POP3 server using telnet on TCP port 110
- Authenticated using valid credentials
- Listed available email messages
- Retrieved a specific email containing a flag

## Key observations
- POP3 requires authentication before access
- Credentials and email contents are transmitted in plaintext
- Messages can be retrieved individually by number

## Why this matters for SOC
POP3 traffic can expose usernames, passwords, and email contents to anyone monitoring the network, making it important to detect plaintext authentication and data access.

