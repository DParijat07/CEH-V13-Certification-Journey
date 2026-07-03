# 04-Password-Attacks.md

# Password Attacks

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Learn the different password attack techniques, their methodologies, common tools, and defensive measures.

---

# What is a Password Attack?

A password attack is the process of attempting to obtain valid credentials to gain authorized or unauthorized access to systems, applications, or network services.

In an **authorized penetration test**, password attacks are performed to evaluate the strength of authentication mechanisms and identify weak password practices.

---

# Password Attack Workflow

```text
Identify Authentication Service
            │
            ▼
Gather Usernames
            │
            ▼
Choose Attack Method
            │
            ▼
Select Tool
            │
            ▼
Execute Attack
            │
            ▼
Analyze Results
            │
            ▼
Report Weak Credentials
```

---

# Common Authentication Services

- SSH
- FTP
- SMB
- RDP
- Telnet
- HTTP Login
- HTTPS Login
- WordPress
- Database Login
- VPN
- Email Services

---

# Types of Password Attacks

## 1. Brute Force Attack

Attempts every possible password combination until the correct password is found.

Example

```
admin

admin1

admin12

admin123

admin1234

...
```

### Advantages

- Guaranteed success eventually

### Disadvantages

- Extremely slow
- Easily detected
- May trigger account lockout

---

## 2. Dictionary Attack

Uses a predefined list of common passwords.

Example

```
password

welcome

letmein

qwerty

admin123

summer2025
```

### Advantages

- Fast
- Efficient
- Most commonly used

### Common Wordlists

- rockyou.txt
- SecLists
- fsocity.dic
- Custom Wordlists

---

## 3. Hybrid Attack

Combines dictionary words with mutations.

Examples

```
password1

Password@

admin2025

Winter123

Company@123
```

---

## 4. Mask Attack

Uses a known password pattern.

Example

Suppose password format is:

```
Company####

```

Hashcat mask

```
Company?d?d?d?d
```

Very effective when password policies are known.

---

## 5. Rule-Based Attack

Applies transformation rules.

Example

```
password

↓

Password

↓

Password1

↓

Password123!

```

Hashcat rules

```
best64.rule

rockyou-30000.rule
```

---

## 6. Credential Stuffing

Uses previously leaked username/password combinations.

Example

```
alice@gmail.com : Password123

↓

Try on VPN

↓

Try on Office365

↓

Try on GitHub
```

Works because users often reuse passwords.

---

## 7. Password Spraying

Attempts one common password against many users.

Example

```
Password123

↓

admin

↓

john

↓

alice

↓

mike
```

Advantages

- Avoids lockout
- Harder to detect

---

## 8. Rainbow Table Attack

Uses precomputed password hashes.

Only effective when:

- Unsalted hashes
- Weak algorithms

Examples

```
LM

NTLM

MD5

SHA1
```

---

## 9. Offline Hash Cracking

Hashes are stolen first.

Then cracked locally.

Examples

```
NTLM

SHA256

MD5

bcrypt

```

Common Tools

- Hashcat
- John the Ripper

---

## 10. Online Password Attack

Attack performed directly against a live service.

Examples

- SSH
- FTP
- SMB
- WordPress
- HTTP Login

Common Tools

- Hydra
- Medusa
- Burp Suite Intruder

---

# Password Attack Comparison

| Attack | Online | Offline | Speed |
|---------|---------|----------|--------|
| Brute Force | Yes | Yes | Slow |
| Dictionary | Yes | Yes | Fast |
| Hybrid | Yes | Yes | Medium |
| Mask | Mostly Offline | Yes | Fast |
| Rule-Based | Mostly Offline | Yes | Fast |
| Password Spraying | Yes | No | Fast |
| Credential Stuffing | Yes | No | Very Fast |
| Rainbow Table | No | Yes | Very Fast |

---

# Password Cracking Workflow

```text
Collect Username
        │
        ▼
Collect Password Hash
        │
        ▼
Identify Hash Type
        │
        ▼
Choose Wordlist
        │
        ▼
Choose Tool
        │
        ▼
Crack Password
        │
        ▼
Validate Credentials
```

---

# Common Password Attack Tools

| Tool | Purpose |
|-------|----------|
| Hydra | Online Password Attacks |
| Medusa | Online Authentication Testing |
| John the Ripper | Offline Hash Cracking |
| Hashcat | GPU Password Cracking |
| Burp Suite | Web Login Testing |
| CeWL | Custom Wordlist Generation |
| Crunch | Wordlist Generation |
| CUPP | Password Profiling |

---

# Common Wordlists

## rockyou.txt

Most famous password dictionary.

Location

```bash
/usr/share/wordlists/rockyou.txt
```

---

## SecLists

Contains

- Usernames
- Passwords
- Directories
- DNS
- API

Location

```bash
/opt/SecLists/
```

---

## fsocity.dic

Used in

- TryHackMe Mr Robot

Contains

- Usernames
- Passwords

---

# Password Policies

A strong password should include

- Uppercase
- Lowercase
- Numbers
- Special Characters
- 12–16+ Characters
- No dictionary words
- Unique per account

---

# Common Weak Passwords

```
password

admin

welcome

123456

password123

qwerty

abc123

letmein

root

administrator
```

---

# Common Hash Types

| Hash | Example Length |
|------|----------------|
| MD5 | 32 |
| SHA1 | 40 |
| SHA256 | 64 |
| NTLM | 32 |
| bcrypt | 60 |

---

# Defensive Measures

- Strong Password Policy
- Account Lockout
- Multi-Factor Authentication (MFA)
- Password Manager
- Unique Passwords
- Password Expiration (where appropriate)
- Monitor Failed Logins
- CAPTCHA
- Disable Default Accounts

---

# MITRE ATT&CK Mapping

| Technique | ATT&CK ID |
|-----------|-----------|
| Brute Force | T1110 |
| Password Guessing | T1110.001 |
| Password Spraying | T1110.003 |
| Credential Stuffing | T1110.004 |
| Valid Accounts | T1078 |

---

# CEH Practical Examples

Examples you have already performed

- Hydra SSH Brute Force
- Hydra WordPress Login
- John the Ripper Hash Cracking
- Mr. Robot WordPress Enumeration
- Password Hash Discovery
- Basic Penetration 1 Login Attack

---

# Interview Questions

## What is a password attack?

A password attack is the process of testing authentication mechanisms by attempting to discover valid credentials through approved techniques such as dictionary attacks, brute force, or password spraying.

---

## Difference between Brute Force and Dictionary Attack?

Brute Force tries every possible combination.

Dictionary Attack only tries passwords from a predefined wordlist.

---

## Difference between Online and Offline Password Attack?

Online attacks interact with the target service directly.

Offline attacks crack password hashes locally without communicating with the target.

---

## What is Password Spraying?

Trying one common password against many user accounts to reduce the chance of account lockout.

---

## What is Credential Stuffing?

Using leaked username/password combinations on other services because users often reuse passwords.

---

## Which tool is commonly used for SSH password testing?

Hydra

---

## Which tools crack password hashes?

- John the Ripper
- Hashcat

---

# CEH Exam Tips

✔ Always identify the authentication service first.

✔ Prefer dictionary attacks before brute force.

✔ Understand the distinction between online authentication testing and offline hash cracking.

✔ Recognize common hash types by their length and format.

✔ Recommend mitigations such as MFA, strong password policies, and monitoring for repeated failed login attempts.

---

# Key Takeaways

- Password attacks remain one of the most common ways attackers gain initial access.
- Different attack techniques are suited to different scenarios.
- Offline attacks are generally faster because they are not limited by network speed or account lockout.
- Strong authentication, unique passwords, MFA, and monitoring significantly reduce the effectiveness of password attacks.

---

**Related Notes**

- `05-Hydra-Cheat-Sheet.md`
- `06-John-the-Ripper.md`
- `07-Hashcat-Basics.md`
- `20-Cheat-Sheet.md`
