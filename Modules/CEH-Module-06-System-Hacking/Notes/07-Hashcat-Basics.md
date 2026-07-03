# 07-Hashcat-Basics.md

# Hashcat Basics

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Tool:** Hashcat
>
> **Objective:** Learn how to perform high-speed offline password auditing using Hashcat.

---

# What is Hashcat?

Hashcat is one of the world's fastest password recovery tools. It performs **offline password cracking** using CPUs and GPUs.

Hashcat supports thousands of hash algorithms and is widely used during:

- Penetration Testing
- Password Auditing
- Incident Response
- Digital Forensics
- Red Team Operations

Unlike Hydra, Hashcat never communicates with the target system. It only attacks password hashes.

---

# Hydra vs John vs Hashcat

| Tool | Purpose |
|-------|----------|
| Hydra | Online password attacks |
| John the Ripper | Offline password cracking |
| Hashcat | High-speed offline password cracking (GPU optimized) |

---

# Password Cracking Workflow

```text
Obtain Password Hash
        │
        ▼
Identify Hash Type
        │
        ▼
Select Attack Mode
        │
        ▼
Choose Wordlist or Mask
        │
        ▼
Run Hashcat
        │
        ▼
Recover Password
        │
        ▼
Document Finding
```

---

# Installation

Kali Linux

```bash
sudo apt install hashcat
```

Verify Installation

```bash
hashcat --version
```

---

# Basic Syntax

```bash
hashcat -m HASHMODE -a ATTACKMODE hash.txt wordlist.txt
```

---

# Important Options

| Option | Description |
|---------|-------------|
| -m | Hash Mode |
| -a | Attack Mode |
| -o | Save Output |
| --show | Display Cracked Passwords |
| --force | Ignore Warnings |
| -O | Optimized Kernel |
| --username | Username:Hash Format |

---

# Common Attack Modes

| Mode | Description |
|------|-------------|
| 0 | Dictionary Attack |
| 1 | Combination Attack |
| 3 | Mask (Brute Force) |
| 6 | Hybrid (Wordlist + Mask) |
| 7 | Hybrid (Mask + Wordlist) |

---

# Common Hash Modes

| Hash Type | Mode |
|------------|------|
| MD5 | 0 |
| SHA1 | 100 |
| SHA256 | 1400 |
| SHA512 | 1700 |
| NTLM | 1000 |
| bcrypt | 3200 |

Complete list:

```bash
hashcat --help
```

---

# Dictionary Attack

```bash
hashcat -m 0 -a 0 hash.txt rockyou.txt
```

Meaning

```
-m 0

↓

MD5

-a 0

↓

Dictionary Attack
```

---

# NTLM Example

```bash
hashcat -m 1000 -a 0 hashes.txt rockyou.txt
```

---

# SHA256 Example

```bash
hashcat -m 1400 -a 0 hashes.txt rockyou.txt
```

---

# Brute Force Attack

```bash
hashcat -m 0 -a 3 hash.txt ?a?a?a?a?a?a
```

Characters

| Mask | Meaning |
|------|----------|
| ?l | Lowercase |
| ?u | Uppercase |
| ?d | Digit |
| ?s | Special Character |
| ?a | All Characters |

Example

```bash
?a?a?a?a?a?a
```

Attempts

```
aaaaaa

↓

AAAAAA

↓

123456

↓

abc123

↓

etc.
```

---

# Numeric PIN Attack

```bash
hashcat -m 0 -a 3 hash.txt ?d?d?d?d
```

Attempts

```
0000

↓

9999
```

---

# Hybrid Attack

Dictionary + Numbers

```bash
hashcat -m 0 -a 6 hash.txt rockyou.txt ?d?d
```

Example

```
password01

admin55

welcome99
```

---

# Combination Attack

```bash
hashcat -m 0 -a 1 hash.txt words1.txt words2.txt
```

Example

```
summer

+

2025

↓

summer2025
```

---

# Show Cracked Passwords

```bash
hashcat --show hash.txt
```

---

# Save Output

```bash
hashcat -m 0 -a 0 hash.txt rockyou.txt -o results.txt
```

---

# Benchmark GPU

```bash
hashcat -b
```

Shows cracking performance.

---

# Restore Session

```bash
hashcat --restore
```

---

# Pause Session

Press

```
p
```

Resume

```
r
```

Quit

```
q
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

Custom

```text
passwords.txt
```

---

# Identify Hash

Example

```text
5f4dcc3b5aa765d61d8327deb882cf99
```

Hash Mode

```
MD5

Mode 0
```

---

# Real Lab Example

## Mr. Robot

Hash

```text
c3fcd3d76192e4007dfb496cca67e13b
```

Command

```bash
hashcat -m 0 -a 0 hash.txt fsocity.dic
```

Recovered Password

```text
abcdefghijklmnopqrstuvwxyz
```

---

# Linux Password Audit

Obtain

```
/etc/shadow
```

Extract hashes

Run

```bash
hashcat -m 1800 hashes.txt rockyou.txt
```

---

# Windows Password Audit

Extract NTLM Hash

Run

```bash
hashcat -m 1000 hashes.txt rockyou.txt
```

---

# Performance Tips

Use GPU whenever available.

Enable optimized kernels.

```bash
-O
```

Example

```bash
hashcat -m 0 -a 0 hash.txt rockyou.txt -O
```

---

# Common Errors

## Token Length Exception

Wrong hash mode selected.

---

## No Devices Found

GPU drivers not installed.

---

## Exhausted

Wordlist completed.

Password not found.

---

# John vs Hashcat

| John | Hashcat |
|-------|----------|
| CPU Based | GPU Optimized |
| Easier for Beginners | Much Faster |
| Excellent Utilities | Excellent Performance |
| Better Linux Integration | Better Large-scale Cracking |

---

# Best Practices

✔ Identify the correct hash type.

✔ Use targeted wordlists before brute force.

✔ Prefer dictionary attacks over mask attacks.

✔ Save recovered credentials securely.

✔ Document findings and recommend stronger passwords and MFA.

---

# Interview Questions

## What is Hashcat?

Hashcat is a GPU-accelerated offline password auditing tool used to recover passwords from hashes.

---

## Difference between John and Hashcat?

John is CPU-focused and beginner-friendly.

Hashcat is GPU-optimized and significantly faster.

---

## Which option specifies hash mode?

```bash
-m
```

---

## Which option specifies attack mode?

```bash
-a
```

---

## Which attack mode performs dictionary attacks?

```
0
```

---

## Which attack mode performs brute force?

```
3
```

---

## Which option displays recovered passwords?

```bash
--show
```

---

## Which option benchmarks hardware performance?

```bash
hashcat -b
```

---

# CEH Exam Tips

✔ Hashcat is an **offline** password auditing tool.

✔ Always identify the correct hash mode before starting.

✔ Learn common hash mode IDs (MD5, NTLM, SHA1, SHA256).

✔ Start with dictionary attacks before brute-force attacks.

✔ GPU acceleration is Hashcat's biggest advantage.

---

# Key Takeaways

- Hashcat is the industry-standard GPU-accelerated password recovery tool.
- It supports thousands of hash algorithms and multiple attack modes.
- Selecting the correct hash mode and attack strategy is more important than memorizing commands.
- Hashcat is an essential tool for CEH, eJPT, PNPT, CRTO, and OSCP preparation.

---

## Related Notes

- `04-Password-Attacks.md`
- `05-Hydra-Cheat-Sheet.md`
- `06-John-the-Ripper.md`
- `20-Cheat-Sheet.md`
