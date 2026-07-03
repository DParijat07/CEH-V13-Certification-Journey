

# Linux Enumeration

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Learn how to systematically enumerate Linux systems after obtaining initial access.

---

# What is Linux Enumeration?

Linux Enumeration is the process of collecting information from a Linux machine after gaining an initial foothold.

The purpose is to discover:

- Current user
- Operating system information
- Running services
- Network configuration
- Users and groups
- Scheduled tasks
- Sensitive files
- Credentials
- Misconfigurations
- Privilege Escalation vectors

Enumeration is the **most important phase after obtaining a shell** because almost every privilege escalation starts with gathering information.

---

# Linux Enumeration Workflow

```text
Initial Shell
      │
      ▼
Current User
      │
      ▼
Operating System
      │
      ▼
Hostname
      │
      ▼
Users & Groups
      │
      ▼
Network Enumeration
      │
      ▼
Processes & Services
      │
      ▼
Interesting Files
      │
      ▼
Permissions
      │
      ▼
SUID / Capabilities
      │
      ▼
Cron Jobs
      │
      ▼
Privilege Escalation
```

---

# 1. Current User

## whoami

```bash
whoami
```

Example

```
www-data
```

---

## id

```bash
id
```

Example

```
uid=33(www-data)
gid=33(www-data)
groups=33(www-data)
```

Very useful because it shows:

- UID
- GID
- Groups

---

## groups

```bash
groups
```

Shows group memberships.

---

# 2. Host Information

Hostname

```bash
hostname
```

Kernel Version

```bash
uname -a
```

Distribution

```bash
cat /etc/os-release
```

Architecture

```bash
arch
```

---

# 3. Current Directory

```bash
pwd
```

List files

```bash
ls
```

Detailed listing

```bash
ls -la
```

Hidden files

```bash
ls -la
```

---

# 4. System Information

Kernel

```bash
uname -r
```

Mounted Filesystems

```bash
mount
```

Disk Usage

```bash
df -h
```

Memory

```bash
free -h
```

CPU

```bash
lscpu
```

---

# 5. User Enumeration

Current User

```bash
whoami
```

Logged-in Users

```bash
who
```

All Users

```bash
cat /etc/passwd
```

Groups

```bash
cat /etc/group
```

Current User Information

```bash
id
```

---

# 6. Home Directories

```bash
ls /home
```

Detailed

```bash
ls -la /home
```

Look for

- SSH Keys
- Notes
- Password Files
- Scripts

---

# 7. Network Enumeration

IP Address

```bash
ip addr
```

Old Command

```bash
ifconfig
```

Routing Table

```bash
ip route
```

ARP Cache

```bash
arp -a
```

Listening Ports

```bash
ss -tulpn
```

Alternative

```bash
netstat -tulpn
```

---

# 8. Running Processes

```bash
ps aux
```

Tree View

```bash
ps -ef
```

Look for

- Root Processes
- Interesting Services
- Password Managers
- Databases

---

# 9. Services

Systemd

```bash
systemctl list-units
```

Service Status

```bash
systemctl status apache2
```

---

# 10. Environment Variables

```bash
env
```

Useful for

- Credentials
- Tokens
- API Keys

---

# 11. Scheduled Tasks

Cron Jobs

```bash
crontab -l
```

System Cron

```bash
cat /etc/crontab
```

Cron Directories

```bash
ls -la /etc/cron*
```

Look for

- Writable Scripts
- Root Cron Jobs

---

# 12. SUID Binaries

One of the most important privilege escalation checks.

```bash
find / -perm -4000 -type f 2>/dev/null
```

Example

```
/usr/bin/passwd

/usr/bin/sudo

/usr/local/bin/nmap
```

Always verify binaries on GTFOBins.

---

# 13. SGID Binaries

```bash
find / -perm -2000 -type f 2>/dev/null
```

---

# 14. Writable Files

World Writable

```bash
find / -writable 2>/dev/null
```

World Writable Directories

```bash
find / -type d -writable 2>/dev/null
```

---

# 15. File Capabilities

Linux Capabilities may allow privilege escalation.

```bash
getcap -r / 2>/dev/null
```

Example

```
python3 cap_setuid
```

---

# 16. SSH Enumeration

SSH Keys

```bash
ls -la ~/.ssh
```

Authorized Keys

```bash
cat ~/.ssh/authorized_keys
```

Private Keys

```bash
find / -name id_rsa 2>/dev/null
```

---

# 17. Password Files

Users

```bash
cat /etc/passwd
```

Shadow File

```bash
cat /etc/shadow
```

Usually requires root.

---

# 18. Searching for Interesting Files

Configuration Files

```bash
find / -name "*.conf" 2>/dev/null
```

Passwords

```bash
find / -iname "*password*" 2>/dev/null
```

Backup Files

```bash
find / -name "*.bak" 2>/dev/null
```

History Files

```bash
find / -name ".bash_history" 2>/dev/null
```

---

# 19. Sudo Permissions

One of the first commands to execute.

```bash
sudo -l
```

Shows

- Allowed Commands
- NOPASSWD Entries
- Misconfigurations

---

# 20. Installed Software

Ubuntu

```bash
dpkg -l
```

CentOS

```bash
rpm -qa
```

---

# 21. Useful Enumeration Tools

## LinPEAS

Automatically checks hundreds of privilege escalation vectors.

## LinEnum

General Linux enumeration.

## Linux Exploit Suggester

Suggests kernel exploits.

## pspy

Monitors processes without root privileges.

## GTFOBins

Search for privilege escalation methods for common Linux binaries.

---

# Linux Enumeration Checklist

```text
✓ whoami

✓ id

✓ hostname

✓ uname -a

✓ /etc/os-release

✓ /etc/passwd

✓ /etc/group

✓ ip addr

✓ ip route

✓ ps aux

✓ ss -tulpn

✓ sudo -l

✓ find SUID

✓ find SGID

✓ getcap

✓ cron jobs

✓ writable files

✓ SSH keys

✓ configuration files

✓ history files
```

---

# Common Privilege Escalation Opportunities

- SUID binaries
- Weak sudo permissions
- Writable cron jobs
- Misconfigured services
- Weak file permissions
- Sensitive files
- SSH private keys
- Writable PATH
- Linux capabilities
- Vulnerable kernel
- Password reuse

---

# Recommended Tools

| Tool | Purpose |
|------|----------|
| LinPEAS | Privilege Escalation Enumeration |
| LinEnum | Enumeration |
| Linux Exploit Suggester | Kernel Exploits |
| pspy | Process Monitoring |
| GTFOBins | Binary Abuse |
| Nmap | Service Enumeration |
| Netcat | Reverse Shell |
| Python | Shell Upgrade |

---

# Real Lab Examples

You have already encountered Linux enumeration in:

- Metasploitable 2
- Basic Pentesting 1
- Mr. Robot
- TryHackMe Linux Rooms
- VulnHub Machines

Common commands used:

```bash
whoami

id

uname -a

sudo -l

find / -perm -4000 -type f 2>/dev/null

cat /etc/passwd

ls -la /home

ps aux

ip addr

ss -tulpn
```

---

# Interview Questions

## What is Linux Enumeration?

The process of gathering detailed information about a Linux system after obtaining initial access to identify security weaknesses and privilege escalation opportunities.

---

## Which command displays the current user?

```bash
whoami
```

---

## Which command displays user ID and group memberships?

```bash
id
```

---

## Which command lists SUID binaries?

```bash
find / -perm -4000 -type f 2>/dev/null
```

---

## Which command checks sudo privileges?

```bash
sudo -l
```

---

## Why are SUID binaries important?

SUID binaries execute with the permissions of their owner (often root). Misconfigured or vulnerable SUID programs can sometimes be abused for privilege escalation.

---

## Which tool is commonly used for Linux privilege escalation enumeration?

- LinPEAS

---

# CEH Exam Tips

✔ Start with `whoami` and `id`.

✔ Check `sudo -l` immediately.

✔ Enumerate SUID binaries.

✔ Look for cron jobs.

✔ Search for SSH keys.

✔ Inspect `/etc/passwd`.

✔ Check Linux capabilities.

✔ Document all findings.

---

# Key Takeaways

- Thorough enumeration is the foundation of successful Linux privilege escalation.
- Built-in Linux commands often provide enough information to identify attack paths.
- Combine manual enumeration with trusted tools such as LinPEAS for comprehensive assessments.
- Always validate privilege escalation techniques in an authorized lab or assessment scope before reporting.
