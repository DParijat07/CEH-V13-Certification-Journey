# CEHv13 - IEMLabs Class 09 Notes

**Date:** 29/06/2026

**Module:** Practical Penetration Testing & Exploitation

**Lab Environment**

* VMware Workstation
* Kali Linux (Attacker)
* Basic Penetration Testing 1 (VulnHub)
* Network Mode: NAT

---

# Objective

The objective of this lab was to understand the complete penetration testing methodology by performing:

* Lab setup
* Host discovery
* Network reconnaissance
* Service enumeration
* Vulnerability analysis
* Exploitation
* Post-exploitation
* Password auditing concepts

---

# Lab Setup

## Environment

Attacker Machine:

* Kali Linux

Target Machine:

* Basic Penetration Testing 1 (VulnHub)

Network Configuration:

* NAT

Reason for using NAT:

* Both attacker and victim remain inside the same isolated virtual network.
* Safe environment for offensive security practice.
* Easy communication between virtual machines.

---

# Phase 1 – Host Discovery

## Objective

Identify active hosts present inside the network.

### Tool Used

* Netdiscover

### Learning

Host discovery is the first stage of penetration testing. Before scanning ports or identifying vulnerabilities, the attacker must determine which systems are alive on the network.

Information obtained:

* Target IP Address
* MAC Address
* Vendor Information

---

# Phase 2 – Connectivity Verification

## Objective

Verify that the discovered host is reachable.

### Tool

Ping (ICMP)

### Purpose

* Confirm network communication
* Measure latency
* Ensure target is alive

Successful replies indicate that further enumeration can begin.

---

# Phase 3 – Service Enumeration

## Tool

Nmap

Aggressive Scan

Purpose:

* Port Discovery
* Service Detection
* Version Detection
* Operating System Detection
* Script Scanning
* Traceroute

---

## Open Services Discovered

### FTP

* Service: FTP
* Software: ProFTPD

Learning:

FTP is commonly used for file transfer.

During penetration testing always check:

* Anonymous login
* Version information
* Misconfigurations
* Public vulnerabilities

---

### SSH

Purpose:

Secure remote administration.

Learning:

SSH is generally not exploited directly.

It becomes valuable after obtaining:

* Valid credentials
* SSH private keys
* Password hashes
* Credential reuse

---

### HTTP

Purpose:

Web application hosting.

Learning:

Whenever HTTP is discovered:

Always enumerate:

* Source code
* Hidden directories
* Login pages
* Robots.txt
* Configuration files
* Web technologies

---

# Enumeration Methodology

Never exploit immediately after scanning.

Always perform:

* Banner analysis
* Version verification
* Technology identification
* Vulnerability research
* Service-specific enumeration

Enumeration generally consumes most of the penetration testing lifecycle.

---

# Vulnerability Analysis

After identifying software versions:

Research should include:

* CVEs
* Public exploits
* Vendor advisories
* Exploit reliability
* Environmental requirements

Important Learning:

Matching a version number alone does not confirm that a system is vulnerable. Verification is essential before attempting exploitation.

---

# Metasploit Framework

Learning Objectives

* Searching modules
* Reading module information
* Understanding exploit options
* Payload selection
* Target configuration
* Executing modules

Important Concepts

Exploit

Code used to trigger a vulnerability.

Payload

Code executed after successful exploitation.

Reverse Shell

The target initiates a connection back to the attacker.

Bind Shell

The attacker connects directly to a service opened on the target.

---

# Payload Selection

Different exploits support different payloads.

Payload compatibility must always be verified before execution.

Common payload categories:

* Command payloads
* Reverse payloads
* Bind payloads
* Meterpreter payloads

Learning:

Selecting an incompatible payload results in exploit failure.

---

# Post Exploitation

After obtaining system access:

Perform controlled enumeration.

Areas to inspect:

* Current user
* User accounts
* Home directories
* Installed applications
* Configuration files
* Scheduled tasks
* SSH configuration
* Running services
* File permissions

Goal:

Understand the environment while maintaining evidence collection.

---

# Linux User Enumeration

Important files:

/etc/passwd

Contains:

* Usernames
* User IDs
* Home directories
* Login shells

/etc/shadow

Contains:

* Password hashes
* Password policy information

Only privileged users can access this file.

---

# Password Hashes

Linux stores password hashes rather than plaintext passwords.

Example hash format:

```
$6$salt$hash
```

Where:

* `$6$` → SHA-512 crypt
* Salt → Random value used during hashing
* Hash → Stored password hash

Learning:

Passwords cannot be directly read from hashes. Security assessments use offline password auditing to evaluate password strength in authorized environments.

---

# Password Auditing

Tools introduced:

* John the Ripper
* Hashcat

Concepts learned:

* Password hash extraction
* Hash identification
* Wordlists
* Offline password auditing
* Password recovery workflow

---

# Penetration Testing Workflow

Reconnaissance

↓

Host Discovery

↓

Port Scanning

↓

Service Enumeration

↓

Vulnerability Analysis

↓

Exploitation

↓

Initial Access

↓

Post Exploitation

↓

Credential Discovery

↓

Documentation

---

# Key Commands Practiced

* Host discovery
* Connectivity verification
* Network scanning
* FTP enumeration
* SSH enumeration
* HTTP enumeration
* Metasploit module usage
* Payload selection
* Linux user enumeration
* Password hash extraction

---

# Key Concepts Learned

* Importance of systematic enumeration
* Understanding attack surface
* Difference between enumeration and exploitation
* Service version analysis
* Vulnerability verification
* Payload compatibility
* Reverse shell concepts
* Linux password storage
* Offline password auditing
* Structured penetration testing methodology

---

# Skills Gained

* Virtual lab setup
* Network reconnaissance
* Service enumeration
* Vulnerability assessment
* Metasploit fundamentals
* Linux post-exploitation
* User enumeration
* Password auditing concepts
* Documentation methodology

---

# Lessons Learned

* Enumeration is the most important phase of a penetration test.
* Every detected service should be investigated individually.
* Vulnerabilities must be validated before exploitation.
* Payload selection directly impacts exploit success.
* Post-exploitation is as important as gaining initial access.
* Password hashes should be handled through authorized offline auditing techniques.
* Good documentation is essential for professional penetration testing reports.

---

# Summary

This lab demonstrated a complete penetration testing workflow within a controlled environment. The focus was on understanding the methodology rather than simply exploiting vulnerabilities. Practical experience was gained in reconnaissance, enumeration, vulnerability assessment, post-exploitation, and password auditing concepts while following a structured and repeatable approach suitable for real-world security assessments.
