# Hydra Cheat Sheet

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Tool:** Hydra
>
> **Objective:** Learn how to perform authorized online password auditing against network services using Hydra.

---

# What is Hydra?

Hydra is one of the most popular tools used for **online password auditing**. It supports dozens of authentication protocols and is commonly used during authorized penetration tests to evaluate the strength of authentication mechanisms.

Hydra can test:

- SSH
- FTP
- HTTP
- HTTPS
- SMB
- RDP
- Telnet
- SMTP
- POP3
- IMAP
- VNC
- MySQL
- PostgreSQL
- MSSQL
- Cisco Login
- SNMP
- WordPress
- Many more

---

# Basic Syntax

```bash
hydra [options] SERVICE://TARGET
```

or

```bash
hydra -l USERNAME -P WORDLIST TARGET SERVICE
```

---

# Basic Options

| Option | Description |
|---------|-------------|
| -l | Single username |
| -L | Username list |
| -p | Single password |
| -P | Password list |
| -C | username:password file |
| -t | Number of parallel tasks |
| -f | Stop after first valid credential |
| -V | Verbose output |
| -vV | Very verbose output |
| -o | Save output |
| -s | Custom port |
| -u | Loop users first |
| -e nsr | Try empty, username=password, reverse username |

---

# SSH

Single User

```bash
hydra -l root -P rockyou.txt ssh://192.168.1.100
```

---

Custom Port

```bash
hydra -l admin -P passwords.txt -s 2222 ssh://192.168.1.100
```

---

Username List

```bash
hydra -L users.txt -P passwords.txt ssh://TARGET
```

---

Stop After Success

```bash
hydra -l root -P rockyou.txt -f ssh://TARGET
```

---

Verbose

```bash
hydra -l root -P rockyou.txt -V ssh://TARGET
```

---

# FTP

```bash
hydra -l ftp -P rockyou.txt ftp://TARGET
```

---

Anonymous Test

```bash
hydra -l anonymous -P passwords.txt ftp://TARGET
```

---

# Telnet

```bash
hydra -l admin -P passwords.txt telnet://TARGET
```

---

# SMB

```bash
hydra -l administrator -P passwords.txt smb://TARGET
```

---

# RDP

```bash
hydra -l administrator -P passwords.txt rdp://TARGET
```

---

# VNC

```bash
hydra -P passwords.txt vnc://TARGET
```

---

# MySQL

```bash
hydra -l root -P passwords.txt mysql://TARGET
```

---

# PostgreSQL

```bash
hydra -l postgres -P passwords.txt postgres://TARGET
```

---

# HTTP Basic Authentication

```bash
hydra -l admin -P passwords.txt http-get://TARGET/protected
```

---

# HTTPS Basic Authentication

```bash
hydra -l admin -P passwords.txt https-get://TARGET/login
```

---

# HTTP POST Form

General Syntax

```bash
hydra -l USER -P WORDLIST TARGET http-post-form "PATH:PARAMETERS:FAILURE_MESSAGE"
```

Example

```bash
hydra -l admin -P rockyou.txt 192.168.1.100 http-post-form "/login.php:username=^USER^&password=^PASS^:Invalid Login"
```

---

# HTTPS POST Form

```bash
hydra -l admin -P passwords.txt TARGET https-post-form "/login.php:user=^USER^&pass=^PASS^:Invalid"
```

---

# WordPress Login

```bash
hydra -l elliot -P fsocity.dic TARGET http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log In:The password you entered"
```

---

# Using Username List

```bash
hydra -L users.txt -P rockyou.txt ssh://TARGET
```

---

# Username and Password Combo File

Format

```
admin:password123

john:qwerty

alice:welcome
```

Command

```bash
hydra -C credentials.txt ssh://TARGET
```

---

# Save Results

```bash
hydra -l admin -P passwords.txt ssh://TARGET -o results.txt
```

---

# Increase Speed

```bash
hydra -l admin -P passwords.txt -t 16 ssh://TARGET
```

---

# Resume Interrupted Scan

```bash
hydra -R
```

---

# Output Example

```
[22][ssh] host: TARGET

login: root

password: password123
```

---

# Common Wordlists

RockYou

```bash
/usr/share/wordlists/rockyou.txt
```

---

SecLists

```bash
/opt/SecLists/
```

---

Mr Robot

```text
fsocity.dic
```

---

# Useful Workflow

```text
Discover Login Service
        │
        ▼
Identify Username
        │
        ▼
Choose Password List
        │
        ▼
Run Hydra
        │
        ▼
Verify Credentials
        │
        ▼
Document Findings
```

---

# Common Errors

## Connection Refused

Target service is not running.

---

## Too Many Connections

Reduce threads.

```bash
-t 4
```

---

## Login Form Doesn't Work

Verify:

- POST URL
- Parameters
- Failure Message
- Cookies
- CSRF Token

---

# Hydra vs Medusa

| Hydra | Medusa |
|--------|---------|
| Most Popular | Faster in some cases |
| Easy Syntax | Modular |
| Excellent Documentation | Lightweight |
| Supports Many Protocols | Supports Many Protocols |

---

# Best Practices

✔ Verify the target service is reachable.

✔ Enumerate usernames before password testing when permitted.

✔ Start with small, relevant wordlists before larger dictionaries.

✔ Tune the number of threads to avoid overwhelming the target.

✔ Save results for reporting.

✔ Stop after the first valid credential if appropriate.

---

# Real Lab Examples

## Metasploitable 2

```bash
hydra -l msfadmin -P rockyou.txt ssh://TARGET
```

---

## Basic Pentesting 1

```bash
hydra -l jan -P rockyou.txt ssh://TARGET
```

---

## Mr. Robot

```bash
hydra -l elliot -P fsocity.dic TARGET http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log In:The password you entered:The password you entered"
```

---

# Interview Questions

## What is Hydra?

Hydra is an online password auditing tool used to test authentication services such as SSH, FTP, SMB, HTTP, and RDP during authorized security assessments.

---

## Difference between -l and -L?

```
-l  = Single username

-L  = Username list
```

---

## Difference between -p and -P?

```
-p = Single password

-P = Password list
```

---

## Which option stops after finding valid credentials?

```bash
-f
```

---

## Which option controls parallel tasks?

```bash
-t
```

---

## Which option saves output?

```bash
-o
```

---

## Which option enables verbose mode?

```bash
-V
```

---

# CEH Exam Tips

✔ Hydra performs **online** password testing.

✔ Always verify the login failure message when testing web forms.

✔ Use protocol-specific syntax (e.g., `ssh://`, `ftp://`, `smb://`).

✔ Document successful credentials and recommend stronger password policies or MFA where appropriate.

---

# Key Takeaways

- Hydra is one of the most widely used tools for authorized online password auditing.
- Understanding the correct module syntax is more important than memorizing commands.
- Proper username enumeration, appropriate wordlists, and careful tuning of options improve effectiveness while reducing unnecessary load on the target.
