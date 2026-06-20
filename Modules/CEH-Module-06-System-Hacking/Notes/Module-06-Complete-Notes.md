# CEH v13 Module 06 – System Hacking Complete Notes

# Module Overview

System Hacking is the phase where an attacker attempts to gain unauthorized access to a target system, escalate privileges, maintain access, and potentially cover tracks. In ethical hacking, these techniques are studied to identify weaknesses and improve security.

---

# What is System Hacking?

System Hacking is the process of:

1. Gaining access to a target system.
2. Escalating privileges.
3. Executing applications.
4. Hiding files.
5. Maintaining access.
6. Covering tracks.

## Real-World Example

Imagine a burglar:

* Finds an unlocked window (vulnerability).
* Enters the house (gains access).
* Finds the master bedroom key (privilege escalation).
* Makes duplicate keys (maintains access).
* Cleans fingerprints (covers tracks).

The same concept applies to system hacking.

---

# System Hacking Methodology

The typical phases are:

```text
Gain Access
    ↓
Escalate Privileges
    ↓
Maintain Access
    ↓
Cover Tracks
```

---

# Phase 1: Gaining Access

## What?

Obtaining unauthorized access to a system.

## How?

Attackers may exploit:

* Weak passwords
* Vulnerabilities
* Misconfigurations
* Social engineering
* Malware

## Common Techniques

### Password Attacks

* Brute Force
* Dictionary Attack
* Hybrid Attack
* Password Spraying

### Exploiting Vulnerabilities

Examples:

* EternalBlue
* SMB Vulnerabilities
* RDP Vulnerabilities

---

# Password Attacks

## Brute Force Attack

Attempts every possible password combination.

Example:

```text
admin
admin123
password
password123
```

### Advantages

* Can eventually crack weak passwords.

### Disadvantages

* Time consuming
* Easily detected

---

## Dictionary Attack

Uses a predefined wordlist.

Example:

```text
rockyou.txt
```

Tools:

* Hydra
* Medusa
* Ncrack

---

## Password Spraying

Uses a few common passwords against many accounts.

Example:

```text
Summer2025!
Welcome123
Password@123
```

Purpose:

Avoid account lockout policies.

---

# Privilege Escalation

## What?

Obtaining higher-level permissions after initial access.

## Why?

A normal user has limited access.

Attackers want:

* Administrator privileges
* SYSTEM privileges
* Root privileges

---

# Types of Privilege Escalation

## Vertical Privilege Escalation

User → Administrator

Example:

```text
User
↓
Administrator
```

---

## Horizontal Privilege Escalation

User A → User B

Example:

```text
Employee
↓
Manager Account
```

---

# Windows Privilege Escalation

Common Misconfigurations:

### Weak Service Permissions

```text
Service Executable Writable
```

### Unquoted Service Paths

Example:

```text
C:\Program Files\My App\Service.exe
```

Windows may execute the wrong file.

---

### Weak Registry Permissions

Misconfigured registry entries may allow privilege escalation.

---

### Scheduled Tasks

Poorly configured tasks may execute attacker-controlled code.

---

# Linux Privilege Escalation

## SUID Binaries

Example:

```bash
find / -perm -4000 2>/dev/null
```

SUID programs run with elevated privileges.

---

## Weak Sudo Permissions

Example:

```bash
sudo -l
```

Misconfigured sudo permissions can lead to root access.

---

## Cron Jobs

Scheduled jobs running as root.

Misconfigured jobs can be abused.

---

## PATH Hijacking

Manipulating environment paths to execute malicious binaries.

---

# Maintaining Access

## What?

Creating a method to re-enter the system later.

## Examples

* Backdoors
* Reverse Shells
* Web Shells
* Persistent Accounts

## Ethical Hacking Perspective

Understand the concept only.

Do not deploy persistence mechanisms on systems without authorization.

---

# Covering Tracks

## What?

Removing evidence of activities.

Examples:

* Deleting logs
* Clearing command history
* Removing malware traces

## Ethical Hacking Perspective

Security professionals study these techniques to understand attacker behavior and improve detection capabilities.

---

# Steganography

## What?

Hiding information inside another file.

Examples:

* Images
* Audio Files
* Video Files

---

## Real-World Example

A secret message hidden inside an image file.

Normal users see:

```text
holiday.jpg
```

Hidden inside:

```text
Confidential Data
```

---

# Steganography Tools

Examples:

* OpenStego
* Steghide

---

# Steganalysis

## What?

Detecting hidden information inside files.

Purpose:

* Malware Analysis
* Digital Forensics
* Threat Hunting

---

# Key Terms

| Term                 | Meaning                             |
| -------------------- | ----------------------------------- |
| Privilege Escalation | Obtaining higher permissions        |
| SUID                 | Special Linux permission bit        |
| Password Spraying    | Few passwords against many users    |
| Backdoor             | Hidden method of access             |
| Steganography        | Hiding data inside files            |
| Steganalysis         | Detecting hidden data               |
| Persistence          | Maintaining access                  |
| Exploitation         | Taking advantage of vulnerabilities |

---

# CEH Exam Tips

Remember:

### System Hacking Lifecycle

```text
Gain Access
↓
Escalate Privileges
↓
Maintain Access
↓
Cover Tracks
```

### Privilege Escalation Types

* Vertical
* Horizontal

### Linux Focus

* SUID
* sudo
* Cron Jobs
* PATH Hijacking

### Windows Focus

* Services
* Registry
* Scheduled Tasks
* Unquoted Service Paths

### Common Password Attacks

* Brute Force
* Dictionary
* Hybrid
* Password Spraying

---

# Practical Labs for Module 06

## TryHackMe

* Blue
* Ice
* Linux Privilege Escalation
* Windows Privilege Escalation

## Homelab

* Windows 7
* Metasploitable 2

## Skills Developed

* Enumeration
* Exploitation
* Privilege Escalation
* Post Exploitation Understanding
* VAPT Reporting
* Security Assessment Methodology

---

# Module Summary

System Hacking focuses on understanding how attackers gain access, escalate privileges, maintain persistence, and hide their activities. For ethical hackers, learning these techniques helps identify weaknesses, assess security controls, and recommend effective mitigations. This module bridges vulnerability assessment and real-world exploitation, making it one of the most practical and important sections of the CEH syllabus.
