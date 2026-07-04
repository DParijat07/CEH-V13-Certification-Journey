# Covering Tracks

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Understand how attackers attempt to hide their activities and how defenders can detect such behavior.

---

# What is Covering Tracks?

Covering Tracks refers to techniques used by attackers to hide evidence of their activities after compromising a system.

The goal is to delay detection and forensic investigation.

---

# Objectives of Covering Tracks

- Hide attacker activities
- Remove evidence
- Avoid detection
- Maintain persistence
- Delay incident response

---

# Common Techniques

- Clearing Event Logs
- Deleting Command History
- Removing Temporary Files
- Hiding Files
- Timestamp Manipulation
- Log Modification
- Rootkits
- Anti-Forensics

---

# Windows Techniques

## Event Logs

Common Windows logs

- Security
- System
- Application

View logs

```cmd
eventvwr.msc
```

PowerShell

```powershell
Get-EventLog -LogName Security
```

---

## Command History

Command Prompt

```cmd
doskey /history
```

PowerShell History

```powershell
Get-History
```

---

## Temporary Files

Common locations

```
C:\Windows\Temp

%TEMP%
```

---

# Linux Techniques

## Bash History

View history

```bash
history
```

History file

```bash
cat ~/.bash_history
```

---

## Log Files

Common logs

```
/var/log/auth.log

/var/log/syslog

/var/log/messages
```

---

## Temporary Files

```
/tmp/

/var/tmp/
```

---

# Timestamp Manipulation

Attackers may modify file timestamps to hide malicious activity.

Useful command

```bash
stat filename
```

---

# Rootkits

A Rootkit is malicious software designed to hide files, processes, users, or network activity from the operating system.

Examples

- Kernel Rootkits
- User-mode Rootkits
- Bootkits

---

# Anti-Forensics

Examples

- Secure file deletion
- Log tampering
- Data wiping
- Encryption
- Metadata removal

---

# Detection

Indicators of compromise include:

- Missing log entries
- Deleted history files
- Suspicious timestamps
- Unexpected services
- Hidden files
- Rootkit indicators

---

# Defensive Measures

- Enable centralized logging
- Monitor log integrity
- Restrict administrative access
- Enable file integrity monitoring
- Use EDR/XDR solutions
- Regularly review audit logs

---

# MITRE ATT&CK Mapping

| Technique | ATT&CK ID |
|-----------|-----------|
| Clear Windows Event Logs | T1070.001 |
| Clear Linux Logs | T1070 |
| Delete Command History | T1070.003 |
| File Deletion | T1070.004 |
| Rootkits | T1014 |
| Timestomping | T1070.006 |

---

# Real Lab Examples

## Windows

```cmd
eventvwr.msc

Get-EventLog -LogName Security
```

---

## Linux

```bash
history

cat ~/.bash_history

ls -la /var/log
```

---

# Best Practices

✔ Enable centralized log collection.

✔ Monitor unusual log deletions.

✔ Protect audit logs from modification.

✔ Use Endpoint Detection and Response (EDR).

✔ Perform regular forensic reviews.

---

# Interview Questions

## What is Covering Tracks?

The process of hiding evidence after compromising a system to avoid detection.

---

## Which Windows utility displays event logs?

```cmd
eventvwr.msc
```

---

## Which file stores Bash command history?

```bash
~/.bash_history
```

---

## What is a Rootkit?

A type of malware designed to hide malicious activity from the operating system.

---

## Name two anti-forensic techniques.

- Log deletion
- Timestamp manipulation

---

# CEH Exam Tips

✔ Understand common anti-forensic techniques.

✔ Know the locations of Windows and Linux log files.

✔ Learn the purpose of timestomping and rootkits.

✔ Focus on both attacker techniques and defensive detection methods.

---

# Key Takeaways

- Covering tracks helps attackers evade detection and forensic analysis.
- Common methods include log deletion, history removal, timestamp manipulation, and rootkits.
- Security teams should monitor logs, file integrity, and endpoint behavior to detect anti-forensic activity.
- Understanding these techniques helps improve incident response and threat hunting.

---

## Related Notes

- `12-Persistence-Techniques.md`
- `14-Post-Exploitation-Checklist.md`
- `17-System-Hacking-Tools.md`
- `18-MITRE-Mapping.md`
- `20-Cheat-Sheet.md`
