# FTP Enumeration and File Retrieval

Used the FTP protocol to enumerate files and retrieve data from a remote FTP server.

## What I did
- Connected to an FTP server using the ftp client
- Logged in using anonymous authentication
- Listed available files on the server
- Retrieved a file containing a flag

## Key observations
- FTP uses a control connection on TCP port 21
- File transfers occur over a separate data connection
- Commands sent by the client differ from those received by the server

## Why this matters for SOC
FTP traffic is unencrypted by default, making it easy to inspect credentials, commands, and file contents during network monitoring and investigations.
