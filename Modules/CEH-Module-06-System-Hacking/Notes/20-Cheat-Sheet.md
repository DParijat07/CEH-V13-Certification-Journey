# 20-Cheat-Sheet.md

# System Hacking Cheat Sheet

> **Module:** CEH v13 – Module 06 (System Hacking)

---

# System Hacking Workflow

```text
Reconnaissance
      ↓
Scanning
      ↓
Enumeration
      ↓
Password Attacks
      ↓
Exploitation
      ↓
Privilege Escalation
      ↓
Persistence
      ↓
Post Exploitation
      ↓
Covering Tracks
```

---

# Windows Enumeration

```cmd
whoami
whoami /priv
whoami /groups
hostname
systeminfo
net user
net localgroup administrators
tasklist
ipconfig /all
netstat -ano
schtasks /query
sc query
cmdkey /list
```

---

# Linux Enumeration

```bash
whoami
id
hostname
uname -a
cat /etc/os-release
sudo -l
ip a
ss -tuln
ps aux
crontab -l
find / -perm -4000 -type f 2>/dev/null
find / -writable 2>/dev/null
getcap -r / 2>/dev/null
```

---

# Hydra

SSH

```bash
hydra -l user -P rockyou.txt ssh://TARGET
```

FTP

```bash
hydra -l admin -P rockyou.txt ftp://TARGET
```

HTTP POST

```bash
hydra -l admin -P rockyou.txt TARGET http-post-form "/login:user=^USER^&pass=^PASS^:F=Invalid"
```

---

# John the Ripper

```bash
john hashes.txt

john --wordlist=rockyou.txt hashes.txt

john --show hashes.txt
```

---

# Hashcat

MD5

```bash
hashcat -m 0 hash.txt rockyou.txt
```

NTLM

```bash
hashcat -m 1000 hash.txt rockyou.txt
```

---

# Nmap

Basic Scan

```bash
nmap TARGET
```

Service Detection

```bash
nmap -sV TARGET
```

Default Scripts

```bash
nmap -sC TARGET
```

Aggressive Scan

```bash
nmap -A TARGET
```

All Ports

```bash
nmap -p- TARGET
```

---

# Gobuster

Directories

```bash
gobuster dir -u http://TARGET -w wordlist.txt
```

Extensions

```bash
gobuster dir -u http://TARGET -w wordlist.txt -x php,txt,html
```

Virtual Hosts

```bash
gobuster vhost -u http://TARGET -w wordlist.txt
```

---

# Nikto

```bash
nikto -h http://TARGET

nikto -h https://TARGET
```

---

# Metasploit

```bash
msfconsole

search exploit

use exploit/module

show options

set RHOSTS TARGET

run
```

---

# Meterpreter

```text
sysinfo

getuid

pwd

ls

cd

download

upload

shell

hashdump

ps

migrate

screenshot
```

---

# Windows Privilege Escalation Checklist

- Weak Service Permissions
- Unquoted Service Paths
- AlwaysInstallElevated
- Stored Credentials
- Scheduled Tasks
- DLL Hijacking
- Token Privileges
- WinPEAS
- Seatbelt
- PowerUp

---

# Linux Privilege Escalation Checklist

- sudo -l
- SUID Binaries
- GTFOBins
- Cron Jobs
- Writable Files
- Linux Capabilities
- Kernel Version
- SSH Keys
- LinPEAS
- LinEnum

---

# Common Tools

| Purpose | Tool |
|---------|------|
| Port Scanning | Nmap |
| Directory Enumeration | Gobuster |
| Web Scanner | Nikto |
| Online Password Attack | Hydra |
| Offline Password Cracking | John |
| GPU Password Cracking | Hashcat |
| Exploitation | Metasploit |
| Post Exploitation | Meterpreter |
| Windows Enumeration | WinPEAS |
| Linux Enumeration | LinPEAS |
| Windows Credentials | Mimikatz |
| Linux PrivEsc Reference | GTFOBins |

---

# MITRE ATT&CK

| Technique | ATT&CK ID |
|------------|-----------|
| Brute Force | T1110 |
| Credential Dumping | T1003 |
| Account Discovery | T1087 |
| System Discovery | T1082 |
| Process Discovery | T1057 |
| File Discovery | T1083 |
| Network Service Scanning | T1046 |
| Scheduled Task | T1053 |
| Registry Run Keys | T1547 |
| Services | T1543 |
| Clear Event Logs | T1070.001 |

---

# Important File Locations

## Windows

```
C:\Windows\Temp

C:\Users\

Startup Folder

Registry Run Keys
```

## Linux

```
/etc/passwd

/etc/shadow

/etc/crontab

~/.ssh/

/var/log/

/tmp/
```

---

# CEH Exam Quick Tips

✔ Enumerate before exploiting.

✔ Verify findings manually.

✔ Document every command and output.

✔ Practice Windows and Linux privilege escalation.

✔ Understand MITRE ATT&CK mappings.

✔ Know the purpose of common tools.

✔ Focus on methodology rather than memorizing commands.

---

# Quick Revision

| Topic | Remember |
|--------|----------|
| Enumeration | Gather information first |
| Password Attacks | Hydra, John, Hashcat |
| Exploitation | Metasploit |
| Post Exploitation | Meterpreter |
| Windows PrivEsc | WinPEAS, PowerUp |
| Linux PrivEsc | LinPEAS, GTFOBins |
| Persistence | Scheduled Tasks, Cron Jobs |
| Covering Tracks | Logs, History, Timestomping |
| Documentation | Screenshots + Evidence + Remediation |

---

# One-Line Summary

> **Enumerate → Exploit → Escalate → Maintain Access → Document → Recommend Mitigation.**
