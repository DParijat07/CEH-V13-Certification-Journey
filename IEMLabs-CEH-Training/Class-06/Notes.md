# Class6-IEMLabs-Notes.md

**Date:** 15/06/2026
**Class:** 06
**Training:** IEMLabs CEH Training

---

# Topics Covered

## 1. Revision: Metasploitable 2 Enumeration and Exploitation

The class began with a practical review of previously covered concepts using the Metasploitable 2 vulnerable machine. The objective was to reinforce the methodology of identifying exposed services and understanding how different attack vectors can lead to system compromise.

---

# Service Enumeration Review

## FTP (File Transfer Protocol)

### Enumeration

```bash
nmap -sV <target-ip>
ftp <target-ip>
```

### Key Points

* Check for anonymous login.
* Identify FTP version.
* Look for known vulnerabilities.
* Explore accessible files and directories.

---

## SSH (Secure Shell)

### Enumeration

```bash
nmap -sV -p 22 <target-ip>
```

### Key Points

* Identify OpenSSH version.
* Look for weak credentials.
* SSH generally requires valid credentials.
* Misconfigurations may lead to unauthorized access.

---

## HTTP (Web Service)

### Enumeration

```bash
nmap -sV -p 80 <target-ip>

nikto -h http://<target-ip>

gobuster dir -u http://<target-ip> \
-w /usr/share/wordlists/dirb/common.txt
```

### Key Points

* Investigate website source code.
* Check robots.txt.
* Discover hidden directories.
* Identify technologies and versions.
* Search for credentials or sensitive information.

---

## SMB (Server Message Block)

### Enumeration

```bash
nmap --script smb-enum-shares.nse -p 139,445 <target-ip>

smbclient -L //<target-ip> -N
```

### Key Points

* Enumerate available shares.
* Check anonymous access.
* Search for sensitive files.
* Identify SMB version.

---

# Enumeration Methodology

The importance of following a structured process was emphasized:

```text
Reconnaissance
↓
Service Enumeration
↓
Version Identification
↓
Vulnerability Assessment
↓
Exploitation
↓
Post-Exploitation
↓
Documentation
```

---

# 2. TryHackMe – Mr. Robot CTF

## Introduction

A new practical exercise was introduced through the Mr. Robot CTF room on TryHackMe.

### Objectives

* Apply enumeration techniques independently.
* Investigate web services.
* Discover hidden clues.
* Capture all available flags.

---

# Initial Enumeration

## Connectivity Check

```bash
ping <target-ip>
```

### Observation

Example:

```text
ttl=62
```

### Learning Point

* Linux systems commonly use a default TTL of 64.
* TTL values help form an initial hypothesis about the target operating system.
* TTL should be treated as a clue rather than definitive proof.

---

## Nmap Scan

Example:

```bash
nmap -A <target-ip>
```

### Purpose

* Service detection
* Version detection
* OS detection
* Script scanning
* Traceroute

---

# Mr. Robot Enumeration Approach

## Manual Inspection

Check:

* Website content
* Page source
* Comments
* Forms
* Hidden clues

---

## robots.txt

```bash
curl http://<target-ip>/robots.txt
```

### Purpose

Discover directories or files intentionally exposed by developers.

---

## Directory Enumeration

```bash
gobuster dir \
-u http://<target-ip> \
-w /usr/share/wordlists/dirb/common.txt
```

### Purpose

Identify hidden directories and resources.

---

## Status

* Successfully captured Flag 1.
* Flag 2 and Flag 3 assigned as homework.

---

# Key Learning Outcomes

* Enumeration is the most critical phase of penetration testing.
* Never assume; validate findings through evidence.
* Small clues can lead to major breakthroughs.
* Follow a consistent methodology.
* Document every step for reporting and future revision.
* Persistence and attention to detail are essential during CTF challenges.

---

# Important Commands Practiced

```bash
ping <target-ip>

nmap -A <target-ip>

nikto -h http://<target-ip>

gobuster dir \
-u http://<target-ip> \
-w /usr/share/wordlists/dirb/common.txt

curl http://<target-ip>/robots.txt

ftp <target-ip>

smbclient -L //<target-ip> -N
```

---

# Homework

* Continue solving the Mr. Robot CTF.
* Obtain Flag 2 and Flag 3.
* Document the complete attack path.
* Prepare screenshots of important findings.
* Review today's enumeration techniques.

---

# Summary

Class 6 focused on strengthening core enumeration skills through revision of Metasploitable 2 services and applying those concepts in the Mr. Robot CTF challenge. The session reinforced the importance of systematic reconnaissance, careful observation, and thorough documentation in ethical hacking engagements.
