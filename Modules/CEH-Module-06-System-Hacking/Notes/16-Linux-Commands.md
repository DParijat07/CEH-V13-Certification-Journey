# Linux Commands for System Hacking

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Learn essential Linux commands used for enumeration, privilege escalation, and post-exploitation.

---

# User Enumeration

Current User

```bash
whoami
```

User Information

```bash
id
```

Current Groups

```bash
groups
```

Logged-in Users

```bash
who

w
```

All Users

```bash
cat /etc/passwd
```

---

# System Information

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

Architecture

```bash
arch
```

Current Directory

```bash
pwd
```

---

# File Enumeration

List Files

```bash
ls -la
```

Find Files

```bash
find / -name filename 2>/dev/null
```

Search for Passwords

```bash
grep -Ri "password" /etc 2>/dev/null
```

Locate File

```bash
locate filename
```

---

# Network Enumeration

IP Address

```bash
ip a
```

Routing Table

```bash
ip route
```

ARP Table

```bash
arp -a
```

Listening Ports

```bash
ss -tuln
```

Network Connections

```bash
netstat -tulnp
```

---

# Process Enumeration

Running Processes

```bash
ps aux
```

Interactive Process Viewer

```bash
top
```

Kill Process

```bash
kill -9 PID
```

---

# Privilege Escalation

Sudo Privileges

```bash
sudo -l
```

Find SUID Binaries

```bash
find / -perm -4000 -type f 2>/dev/null
```

Find Writable Files

```bash
find / -writable 2>/dev/null
```

Linux Capabilities

```bash
getcap -r / 2>/dev/null
```

---

# Scheduled Tasks

Current User Cron

```bash
crontab -l
```

System Cron

```bash
cat /etc/crontab
```

---

# SSH Enumeration

SSH Directory

```bash
ls -la ~/.ssh
```

Authorized Keys

```bash
cat ~/.ssh/authorized_keys
```

---

# Log Files

Authentication Logs

```bash
cat /var/log/auth.log
```

System Logs

```bash
cat /var/log/syslog
```

Kernel Logs

```bash
dmesg
```

---

# Disk Information

Disk Usage

```bash
df -h
```

Directory Size

```bash
du -sh *
```

Mounted Drives

```bash
mount
```

---

# Useful CEH Commands

```bash
whoami

id

hostname

uname -a

ip a

ss -tuln

sudo -l

find / -perm -4000 -type f 2>/dev/null

ps aux

crontab -l
```

---

# Best Practices

✔ Enumerate before exploiting.

✔ Check sudo permissions first.

✔ Inspect SUID binaries.

✔ Review cron jobs.

✔ Document command outputs.

---

# Interview Questions

### Which command shows the current user?

```bash
whoami
```

### Which command displays user privileges?

```bash
id
```

### Which command checks sudo permissions?

```bash
sudo -l
```

### Which command finds SUID binaries?

```bash
find / -perm -4000 -type f 2>/dev/null
```

### Which command displays running processes?

```bash
ps aux
```

---

# CEH Exam Tips

- Memorize common Linux enumeration commands.
- Practice using `find`, `grep`, `sudo -l`, and `ss`.
- Learn to identify privilege escalation opportunities.
- Record all findings during assessments.

---

## Related Notes

- `03-Linux-Enumeration.md`
- `11-Privilege-Escalation-Linux.md`
- `17-System-Hacking-Tools.md`
- `20-Cheat-Sheet.md`
