# Linux and Bash Scripting

Bash scripting practice from TryHackMe Linux fundamentals labs, covering log searching, file permissions, and reading user input.

## Labs

### Flag hunt
Modified and debugged a script to search through system logs in `/var/log` using `grep`. This lab required managing file permissions and running the script with sudo (root) privileges.

Script: [`flag_hunt.sh`](./flag_hunt.sh)

### Locker script
Created a Bash script that takes user input (name, company, PIN) and stores it. Used to practice variables and reading input in the Linux terminal.

Script: [`locker_script.sh`](./locker_script.sh)

## Skills practiced
- Searching and filtering log files with `grep`
- Managing file permissions and executing scripts with elevated privileges
- Declaring and using variables in Bash
- Reading interactive user input with `read`

## Why this matters for SOC
Log searching from the command line is a core triage skill: being able to grep through `/var/log` quickly narrows down when and how something happened before reaching for heavier tooling.
