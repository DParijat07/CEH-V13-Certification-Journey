# Persistence Techniques

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Understand common persistence mechanisms attackers use to maintain access after compromising a system.

---

# What is Persistence?

Persistence is the process of maintaining access to a compromised system even after reboot, logout, or password changes.

Example

```
Gain Access

↓

Privilege Escalation

↓

Install Persistence

↓

Maintain Access
```

---

# Persistence Workflow

```text
Initial Access
      │
      ▼
Privilege Escalation
      │
      ▼
Create Persistence
      │
      ▼
Maintain Access
      │
      ▼
Post Exploitation
```

---

# Common Persistence Techniques

- Startup Programs
- Scheduled Tasks
- Windows Services
- Registry Run Keys
- SSH Authorized Keys
- Cron Jobs
- Backdoor Accounts
- Web Shells
- Reverse Shell Listeners

---

# Windows Persistence

## Startup Folder

Programs placed in the Startup folder execute automatically when a user logs in.

Location

```
C:\Users\<User>\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup
```

---

## Registry Run Keys

Automatically execute programs during user login.

Common Locations

```
HKCU\Software\Microsoft\Windows\CurrentVersion\Run

HKLM\Software\Microsoft\Windows\CurrentVersion\Run
```

---

## Scheduled Tasks

View scheduled tasks

```cmd
schtasks /query
```

---

## Windows Services

List services

```cmd
sc query
```

---

# Linux Persistence

## Cron Jobs

View cron jobs

```bash
crontab -l
```

System cron

```bash
cat /etc/crontab
```

---

## SSH Authorized Keys

Common location

```
~/.ssh/authorized_keys
```

---

## Startup Scripts

System startup directory

```
/etc/init.d/

systemd services
```

---

## Bash Profile

Executed during login

```
~/.bashrc

~/.profile
```

---

# Web Shell Persistence

Example web shells

- PHP
- ASPX
- JSP

Common locations

```
/var/www/html/

htdocs/

wwwroot/
```

---

# Persistence Detection

Indicators include:

- Unknown scheduled tasks
- Unknown services
- New startup entries
- Modified registry keys
- Unexpected cron jobs
- Unauthorized SSH keys
- Suspicious web files

---

# Defensive Measures

- Enable Endpoint Detection and Response (EDR)
- Monitor startup items
- Audit scheduled tasks
- Restrict administrative privileges
- Enable logging and alerting
- Regularly review user accounts
- Patch operating systems and applications

---

# MITRE ATT&CK Mapping

| Technique | ATT&CK ID |
|-----------|-----------|
| Registry Run Keys | T1547 |
| Scheduled Task | T1053 |
| Services | T1543 |
| SSH Authorized Keys | T1098 |
| Cron Jobs | T1053.003 |
| Web Shell | T1505 |

---

# Real Lab Examples

## Windows

```cmd
schtasks /query

sc query
```

---

## Linux

```bash
crontab -l

cat /etc/crontab

ls ~/.ssh
```

---

# Best Practices

✔ Monitor startup locations.

✔ Review scheduled tasks regularly.

✔ Audit user accounts.

✔ Monitor service creation.

✔ Enable centralized logging.

---

# Interview Questions

## What is Persistence?

Persistence is a technique used to maintain access to a compromised system after the initial compromise.

---

## Which Windows feature can automatically execute programs at logon?

Startup Folder and Registry Run Keys.

---

## Which Linux file stores user cron jobs?

```bash
crontab -l
```

---

## Which file stores SSH public keys?

```
~/.ssh/authorized_keys
```

---

## Name two persistence techniques.

- Scheduled Tasks
- Registry Run Keys

---

# CEH Exam Tips

✔ Understand the purpose of persistence after successful exploitation.

✔ Learn common Windows and Linux persistence mechanisms.

✔ Know where to investigate for persistence during incident response.

✔ Focus on detection and remediation as well as attacker techniques.

---

# Key Takeaways

- Persistence enables attackers to regain access after reboot or logout.
- Windows commonly uses services, scheduled tasks, startup folders, and registry run keys.
- Linux commonly uses cron jobs, SSH authorized keys, and startup scripts.
- Regular monitoring and auditing help detect unauthorized persistence mechanisms.

---

## Related Notes

- `10-Privilege-Escalation-Windows.md`
- `11-Privilege-Escalation-Linux.md`
- `13-Covering-Tracks.md`
- `14-Post-Exploitation-Checklist.md`
- `18-MITRE-Mapping.md`
