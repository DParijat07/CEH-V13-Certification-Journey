# John the Ripper (Jumbo Edition)

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Tool:** John the Ripper (JtR)
>
> **Objective:** Learn how to identify, crack, and audit password hashes using John the Ripper.

---

# What is John the Ripper?

John the Ripper (JtR) is one of the world's most popular **offline password cracking tools**.

Unlike Hydra, which attacks **live login services**, John works on **password hashes** that have already been obtained from a system.

John supports hundreds of hash formats and is widely used during:

- Penetration Testing
- Digital Forensics
- Incident Response
- Password Auditing
- Red Team Operations

---

# Online vs Offline Password Cracking

| Online | Offline |
|----------|-----------|
| Hydra | John the Ripper |
| Medusa | Hashcat |
| Burp Suite | Cain & Abel |

Online attacks communicate with the target.

Offline attacks work on password hashes locally.

---

# Password Cracking Workflow

```text
Obtain Password Hash
        │
        ▼
Identify Hash Type
        │
        ▼
Select Wordlist
        │
        ▼
Choose Attack Mode
        │
        ▼
Run John
        │
        ▼
Recover Password
        │
        ▼
Document Finding
```

---

# Installation

Ubuntu/Kali

```bash
sudo apt install john
```

Verify

```bash
john --version
```

---

# Supported Hash Types

John supports hundreds of formats.

Examples

- MD5
- SHA1
- SHA256
- SHA512
- NTLM
- LM
- bcrypt
- DES
- Unix Crypt
- ZIP
- RAR
- PDF
- Office Documents
- SSH Keys

---

# Basic Syntax

```bash
john HASHFILE
```

---

Using a Wordlist

```bash
john --wordlist=rockyou.txt HASHFILE
```

---

Show Cracked Passwords

```bash
john --show HASHFILE
```

---

# Identifying Hash Format

Before cracking, determine the hash type.

Example

```
5f4dcc3b5aa765d61d8327deb882cf99
```

Could be:

- MD5

Another example

```
c3fcd3d76192e4007dfb496cca67e13b
```

MD5 hash used in TryHackMe Mr. Robot.

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

Custom Wordlist

```bash
passwords.txt
```

---

# Cracking Linux Password Hashes

Suppose

```
hash.txt
```

contains

```
root:$6$....
```

Command

```bash
john hash.txt
```

---

Using RockYou

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt hash.txt
```

---

# Cracking MD5

Example

```
5f4dcc3b5aa765d61d8327deb882cf99
```

Command

```bash
john --format=raw-md5 hash.txt
```

---

# Cracking NTLM

```bash
john --format=NT hash.txt
```

---

# Cracking SHA256

```bash
john --format=raw-sha256 hash.txt
```

---

# Cracking SHA512

```bash
john --format=raw-sha512 hash.txt
```

---

# List Supported Formats

```bash
john --list=formats
```

---

# Incremental Mode

Attempts every possible combination.

```bash
john --incremental hash.txt
```

Very slow.

---

# Single Crack Mode

Uses username and metadata.

```bash
john --single hash.txt
```

Useful for Linux password files.

---

# Wordlist Mode

Most commonly used.

```bash
john --wordlist=rockyou.txt hash.txt
```

---

# Rules Mode

Applies mutations.

```bash
john --wordlist=rockyou.txt --rules hash.txt
```

Example

```
password

↓

Password

↓

Password123

↓

Password!
```

---

# Session Management

Save Session

```bash
john --session=lab hash.txt
```

Resume Session

```bash
john --restore=lab
```

---

# Show Cracked Passwords

```bash
john --show hash.txt
```

Output

```
robot:abcdefghijklmnopqrstuvwxyz
```

---

# Cracking ZIP Files

Generate hash

```bash
zip2john secret.zip > hash.txt
```

Crack

```bash
john hash.txt
```

---

# Cracking RAR Files

Generate

```bash
rar2john secret.rar > hash.txt
```

Crack

```bash
john hash.txt
```

---

# Cracking PDF Files

Generate

```bash
pdf2john secret.pdf > hash.txt
```

Crack

```bash
john hash.txt
```

---

# Cracking Office Documents

```bash
office2john report.docx > hash.txt
```

Then

```bash
john hash.txt
```

---

# Cracking SSH Private Keys

Generate

```bash
ssh2john id_rsa > hash.txt
```

Crack

```bash
john hash.txt
```

---

# Cracking /etc/shadow

Combine passwd and shadow

```bash
unshadow passwd shadow > hashes.txt
```

Crack

```bash
john hashes.txt
```

---

# Useful Commands

List Formats

```bash
john --list=formats
```

Show Results

```bash
john --show hashes.txt
```

Wordlist

```bash
john --wordlist=rockyou.txt hashes.txt
```

Incremental

```bash
john --incremental hashes.txt
```

Rules

```bash
john --rules hashes.txt
```

---

# Common John Utilities

| Utility | Purpose |
|----------|----------|
| zip2john | ZIP Password |
| rar2john | RAR Password |
| pdf2john | PDF Password |
| office2john | Office Documents |
| ssh2john | SSH Keys |
| unshadow | Merge passwd & shadow |

---

# Common Hash Lengths

| Hash | Length |
|------|---------|
| MD5 | 32 |
| SHA1 | 40 |
| SHA256 | 64 |
| SHA512 | 128 |
| NTLM | 32 |
| bcrypt | 60 |

---

# Real Lab Example

## TryHackMe – Mr. Robot

Discovered

```
robot:c3fcd3d76192e4007dfb496cca67e13b
```

Saved as

```
hash.txt
```

Cracked

```bash
john --format=raw-md5 --wordlist=fsocity.dic hash.txt
```

Recovered Password

```
abcdefghijklmnopqrstuvwxyz
```

---

## Linux Password Audit

Obtain

```
/etc/passwd

/etc/shadow
```

Merge

```bash
unshadow passwd shadow > hashes.txt
```

Crack

```bash
john --wordlist=rockyou.txt hashes.txt
```

---

# John vs Hashcat

| John | Hashcat |
|-------|----------|
| CPU Based | GPU Optimized |
| Beginner Friendly | Faster on Supported Hardware |
| Many Built-in Utilities | Highly Customizable |
| Excellent for Linux Password Files | Excellent for Large-scale Cracking |

---

# Best Practices

✔ Identify the correct hash type before cracking.

✔ Start with a targeted wordlist before trying brute force.

✔ Use rules to mutate common passwords.

✔ Save and restore long-running sessions.

✔ Record recovered credentials securely and report them as findings in authorized assessments.

---

# Interview Questions

## What is John the Ripper?

John the Ripper is an offline password auditing and hash cracking tool used to recover passwords from password hashes.

---

## Difference between Hydra and John?

Hydra attacks live authentication services.

John attacks password hashes locally.

---

## Which command displays cracked passwords?

```bash
john --show hash.txt
```

---

## Which mode is most commonly used?

Wordlist Mode

```bash
john --wordlist=rockyou.txt hash.txt
```

---

## Which utility extracts ZIP password hashes?

```bash
zip2john
```

---

## Which utility combines passwd and shadow?

```bash
unshadow
```

---

## Which hash from Mr. Robot did we crack?

```
c3fcd3d76192e4007dfb496cca67e13b
```

Recovered password:

```
abcdefghijklmnopqrstuvwxyz
```

---

# CEH Exam Tips

✔ John is an **offline** password auditing tool.

✔ Always identify the hash format before cracking.

✔ Learn the helper utilities (`zip2john`, `pdf2john`, `ssh2john`, `unshadow`).

✔ Prefer wordlist attacks before incremental (brute-force) mode.

✔ Document recovered credentials and recommend remediation such as stronger password policies and MFA.

---

# Key Takeaways

- John the Ripper is one of the most versatile offline password auditing tools.
- It supports hundreds of hash formats and multiple attack modes.
- Understanding the workflow—from identifying the hash type to selecting the right attack mode—is more valuable than memorizing commands.
- It is an essential tool for CEH, eJPT, PNPT, and OSCP preparation.

---

## Related Notes

- `04-Password-Attacks.md`
- `05-Hydra-Cheat-Sheet.md`
- `07-Hashcat-Basics.md`
- `20-Cheat-Sheet.md`
```
