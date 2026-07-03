# Windows Enumeration

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Learn how to enumerate a Windows system after obtaining initial access.

---

# What is Windows Enumeration?

Windows Enumeration is the process of collecting detailed information from a Windows machine after gaining an initial foothold.

The objective is to identify:

- Current user
- System information
- Hostname
- Running services
- Installed software
- Network configuration
- User accounts
- Groups
- Shares
- Scheduled tasks
- Password policies
- Privilege escalation opportunities

Enumeration is one of the most important phases because **the more information you gather, the easier it becomes to identify misconfigurations and potential attack paths.**

---

# Windows Enumeration Workflow

```text
Gain Initial Shell
        │
        ▼
Identify Current User
        │
        ▼
Collect System Information
        │
        ▼
Enumerate Users & Groups
        │
        ▼
Enumerate Network
        │
        ▼
Enumerate Running Processes
        │
        ▼
Enumerate Services
        │
        ▼
Enumerate Installed Applications
        │
        ▼
Check Scheduled Tasks
        │
        ▼
Search for Credentials
        │
        ▼
Identify Privilege Escalation Opportunities
```

---

# 1. Identify Current User

## whoami

Shows the logged-in user.

```cmd
whoami
```

Example

```
desktop\john
```

---

## whoami /all

Displays:

- SID
- Privileges
- Integrity Level
- Groups

```cmd
whoami /all
```

Useful for privilege escalation.

---

## whoami /priv

Lists available privileges.

```cmd
whoami /priv
```

Example

```
SeShutdownPrivilege

SeChangeNotifyPrivilege

SeImpersonatePrivilege
```

---

# 2. Host Information

## hostname

```cmd
hostname
```

Example

```
WIN10-PC
```

---

## systeminfo

Very important command.

```cmd
systeminfo
```

Shows:

- OS Version
- Build Number
- Hotfixes
- RAM
- CPU
- Domain
- Architecture

Useful for:

- Kernel exploits
- Missing patches

---

## ver

Displays Windows version.

```cmd
ver
```

---

# 3. Current Working Directory

```cmd
cd

dir
```

List files

```
dir
```

Hidden files

```
dir /a
```

---

# 4. Enumerating Users

## net user

```cmd
net user
```

Example

```
Administrator

Guest

John

Support
```

---

## User Details

```cmd
net user Administrator
```

Shows

- Last login
- Password age
- Local groups

---

# 5. Enumerating Groups

```cmd
net localgroup
```

Example

```
Administrators

Users

Backup Operators

Remote Desktop Users
```

---

View Administrators

```cmd
net localgroup administrators
```

---

# 6. Network Enumeration

## ipconfig

```cmd
ipconfig
```

---

Detailed Information

```cmd
ipconfig /all
```

Shows

- DNS
- Gateway
- MAC Address
- DHCP
- IPv4

---

## arp

```cmd
arp -a
```

Shows nearby hosts.

---

## Route Table

```cmd
route print
```

---

## Active Connections

```cmd
netstat -ano
```

Shows

- Listening Ports
- Established Connections
- PID

---

# 7. Running Processes

```cmd
tasklist
```

Lists processes.

---

Verbose

```cmd
tasklist /v
```

---

Filter

```cmd
tasklist | findstr explorer
```

---

# 8. Services

```cmd
sc query
```

Shows running services.

---

Specific Service

```cmd
sc qc Spooler
```

Useful for

- Unquoted Service Path
- Weak Permissions

---

# 9. Installed Applications

Using WMIC

```cmd
wmic product get name,version
```

PowerShell

```powershell
Get-WmiObject Win32_Product
```

Useful to identify

- Outdated Software
- Vulnerable Applications

---

# 10. Scheduled Tasks

```cmd
schtasks
```

Detailed

```cmd
schtasks /query /fo LIST /v
```

Look for

- Writable Tasks
- High Privilege Tasks

---

# 11. Shared Resources

```cmd
net share
```

Example

```
C$

ADMIN$

Users

Public
```

---

# 12. Password Policy

```cmd
net accounts
```

Shows

- Minimum Password Length
- Lockout Policy
- Password Age

---

# 13. Environment Variables

```cmd
set
```

PowerShell

```powershell
Get-ChildItem Env:
```

Useful for

- Credentials
- Paths
- Tokens

---

# 14. Searching for Interesting Files

Search for passwords

```cmd
dir C:\password* /s
```

Search config files

```cmd
dir *.config /s
```

Search text files

```cmd
dir *.txt /s
```

---

# 15. Registry Enumeration

AutoRun

```cmd
reg query HKLM\Software\Microsoft\Windows\CurrentVersion\Run
```

AutoRun (User)

```cmd
reg query HKCU\Software\Microsoft\Windows\CurrentVersion\Run
```

Installed Software

```cmd
reg query HKLM\Software
```

---

# 16. PowerShell Enumeration

Current User

```powershell
whoami
```

Processes

```powershell
Get-Process
```

Services

```powershell
Get-Service
```

Users

```powershell
Get-LocalUser
```

Groups

```powershell
Get-LocalGroup
```

Network

```powershell
Get-NetIPAddress
```

---

# 17. Security Software

Check Defender

```powershell
Get-MpComputerStatus
```

Firewall

```cmd
netsh advfirewall show allprofiles
```

---

# 18. Windows Event Logs

Security

```cmd
wevtutil qe Security
```

System

```cmd
wevtutil qe System
```

Application

```cmd
wevtutil qe Application
```

---

# 19. Useful Enumeration Tools

| Tool | Purpose |
|-------|----------|
| WinPEAS | Privilege Escalation Enumeration |
| Seatbelt | Windows Enumeration |
| PowerUp | Privilege Escalation |
| PowerView | Active Directory Enumeration |
| SharpUp | Privilege Escalation |
| Sysinternals Suite | System Analysis |

---

# Common Information to Collect

- Username
- Hostname
- Windows Version
- Architecture
- Domain
- Local Users
- Administrator Group
- Network Configuration
- Running Processes
- Installed Software
- Scheduled Tasks
- Password Policy
- Firewall Status
- Antivirus
- Shares

---

# Typical Enumeration Checklist

```text
✓ Current User

✓ Hostname

✓ Windows Version

✓ IP Address

✓ Running Services

✓ Installed Software

✓ Administrator Users

✓ Scheduled Tasks

✓ Shares

✓ Firewall

✓ Antivirus

✓ Environment Variables

✓ Password Policy

✓ Registry

✓ Interesting Files
```

---

# Interview Questions

## What is Windows Enumeration?

The process of collecting detailed information from a Windows system after obtaining initial access.

---

## Why is systeminfo important?

It reveals:

- Windows version
- Build number
- Installed hotfixes
- System architecture

This information helps identify vulnerable versions and potential privilege escalation paths.

---

## Why check net localgroup administrators?

To identify users with administrative privileges.

---

## Which command lists running processes?

```cmd
tasklist
```

---

## Which command displays detailed network configuration?

```cmd
ipconfig /all
```

---

## Which command displays password policy?

```cmd
net accounts
```

---

## Which command lists scheduled tasks?

```cmd
schtasks
```

---

# CEH Exam Tips

✔ Always start with `whoami`.

✔ Collect system information before attempting exploitation.

✔ Enumerate users and groups.

✔ Check installed software.

✔ Look for scheduled tasks and services.

✔ Document every finding.

✔ Never assume you have administrator privileges.

---

# Key Takeaways

- Enumeration is the foundation of successful post-exploitation.
- Small pieces of information often lead to privilege escalation.
- Commands like `systeminfo`, `whoami /priv`, and `net user` are among the most valuable during Windows assessments.
- Use both built-in Windows commands and specialized enumeration tools where appropriate.
