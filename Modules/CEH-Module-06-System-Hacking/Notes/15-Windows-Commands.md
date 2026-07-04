# Windows Commands for System Hacking

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Learn essential Windows commands used during enumeration, privilege escalation, and post-exploitation.

---

# User Enumeration

Current User

```cmd
whoami
```

Current Privileges

```cmd
whoami /priv
```

Current Groups

```cmd
whoami /groups
```

List Users

```cmd
net user
```

User Information

```cmd
net user username
```

Local Administrators

```cmd
net localgroup administrators
```

---

# System Information

Hostname

```cmd
hostname
```

Operating System

```cmd
systeminfo
```

Environment Variables

```cmd
set
```

Current Directory

```cmd
cd
```

Current Date & Time

```cmd
date
time
```

---

# Network Enumeration

IP Configuration

```cmd
ipconfig /all
```

Routing Table

```cmd
route print
```

ARP Cache

```cmd
arp -a
```

DNS Cache

```cmd
ipconfig /displaydns
```

NetBIOS

```cmd
nbtstat -n
```

Network Connections

```cmd
netstat -ano
```

---

# File Enumeration

List Files

```cmd
dir
```

Recursive Search

```cmd
dir /s
```

Find Files

```cmd
where filename
```

Search Text

```cmd
findstr "password" *.txt
```

---

# Process Enumeration

Running Processes

```cmd
tasklist
```

Detailed Processes

```cmd
wmic process list brief
```

Kill Process

```cmd
taskkill /PID <PID> /F
```

---

# Service Enumeration

List Services

```cmd
sc query
```

Service Details

```cmd
sc qc ServiceName
```

Running Services

```cmd
net start
```

---

# Scheduled Tasks

View Tasks

```cmd
schtasks /query
```

Detailed View

```cmd
schtasks /query /fo LIST /v
```

---

# Shares

List Shares

```cmd
net share
```

View Network Resources

```cmd
net view
```

---

# Password & Credentials

Saved Credentials

```cmd
cmdkey /list
```

Credential Manager

```cmd
control keymgr.dll
```

---

# Firewall

Firewall Status

```cmd
netsh advfirewall show allprofiles
```

---

# PowerShell

PowerShell Version

```powershell
$PSVersionTable
```

Execution Policy

```powershell
Get-ExecutionPolicy
```

Running Services

```powershell
Get-Service
```

Running Processes

```powershell
Get-Process
```

---

# Useful CEH Commands

```cmd
whoami

systeminfo

hostname

ipconfig /all

tasklist

net user

net localgroup administrators

whoami /priv

cmdkey /list

netstat -ano
```

---

# Best Practices

✔ Enumerate before exploiting.

✔ Collect evidence.

✔ Document command output.

✔ Verify findings manually.

✔ Work only in authorized environments.

---

# Interview Questions

### Which command displays the current user?

```cmd
whoami
```

### Which command shows Windows privileges?

```cmd
whoami /priv
```

### Which command lists local users?

```cmd
net user
```

### Which command displays network connections?

```cmd
netstat -ano
```

### Which command displays system information?

```cmd
systeminfo
```

---

# CEH Exam Tips

- Memorize common Windows enumeration commands.
- Learn the difference between `whoami`, `net user`, and `systeminfo`.
- Practice these commands on Windows virtual machines.
- Record command outputs during penetration tests.

---

## Related Notes

- `02-Windows-Enumeration.md`
- `10-Privilege-Escalation-Windows.md`
- `17-System-Hacking-Tools.md`
- `20-Cheat-Sheet.md`
