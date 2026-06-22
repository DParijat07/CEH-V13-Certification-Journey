# IEMLabs CEH Class 07 Notes

**Date:** 22/06/2026
**Module Mapping:** Module 02 (Footprinting & Reconnaissance), Module 03 (Scanning Networks), Module 04 (Enumeration), Module 06 (System Hacking), Module 08 (Sniffing)
**Lab Environment:** TryHackMe AttackBox, Kali Linux, WordPress-Based Lab Environment
**Instructor:** Surjendu Chakraborty

---

# Class Overview

This session focused on practical penetration testing methodology, including:

* Virtual lab setup
* Network configuration
* DNS and domain reconnaissance
* Packet analysis using Wireshark
* Enumeration techniques
* Web application assessment concepts
* Privilege escalation awareness
* Root-level system exploration

The class demonstrated how ethical hackers systematically move from reconnaissance to exploitation and post-exploitation activities within an authorized lab environment.

---

# Learning Objectives

By the end of this session, I was able to:

* Configure a virtual penetration testing environment.
* Verify network connectivity.
* Understand DNS resolution processes.
* Perform basic information gathering.
* Analyze network packets using Wireshark.
* Understand web application attack surfaces.
* Recognize privilege escalation concepts.
* Understand the importance of enumeration during assessments.

---

# Virtual Lab Setup

## Environment Configuration

The lab environment consisted of:

* Kali Linux Attack Machine
* Target Web Application
* Virtual Network Configuration
* VPN Connectivity
* TryHackMe AttackBox

### Activities Performed

* Virtual machine verification
* Network adapter configuration
* IP address verification
* Connectivity validation

### Key Learning

A properly configured lab environment is essential before beginning any security assessment.

---

# Network Connectivity Testing

## Ping Command

Purpose:

* Verify connectivity
* Test reachability
* Validate network communication

Example:

```bash
ping google.com
```

### Concepts Learned

* ICMP Protocol
* Request and Reply Messages
* Basic Connectivity Testing

### Key Learning

Successful responses confirm communication between systems and assist in troubleshooting network issues.

---

# DNS and Domain Name Resolution

## Understanding DNS

DNS converts human-readable domain names into IP addresses.

Example:

```text
google.com
↓
Resolved IP Address
```

### Tools Discussed

#### NSLookup

Used to resolve domain names.

Example:

```bash
nslookup google.com
```

#### Whois

Used to gather registration information.

Example:

```bash
whois google.com
```

### Information Gathered

* Domain Ownership
* Registrar Information
* Name Servers
* Public IP Information

### Key Learning

DNS information forms an important part of the reconnaissance phase.

---

# Reconnaissance and Enumeration

## Information Gathering

The class demonstrated collecting information about a target before beginning deeper assessment activities.

### Objectives

* Identify target information
* Understand attack surface
* Gather public information

### Enumeration Importance

Enumeration often reveals:

* Usernames
* Services
* Directories
* System Information

### Key Learning

Enumeration is frequently the most valuable phase of a penetration test because it identifies potential attack paths.

---

# Wireshark Fundamentals

## Introduction to Wireshark

Wireshark is a network protocol analyzer used to capture and inspect network traffic.

### Activities Performed

* Captured traffic from eth0 interface
* Observed packet communication
* Analyzed network protocols

### Protocols Observed

#### HTTP

* Hypertext Transfer Protocol
* Unencrypted communication

#### TCP

* Transmission Control Protocol
* Reliable connection-oriented communication

#### DNS

* Domain Name System traffic

---

# HTTP Security Observation

## Why HTTP is Insecure

HTTP transmits data in plaintext.

Potential risks include:

* Credential exposure
* Session interception
* Information disclosure

### Security Recommendation

Use HTTPS whenever possible.

### Key Learning

Confidentiality can be compromised when sensitive information is transmitted without encryption.

---

# Web Application Assessment Concepts

## WordPress Environment

The class used a WordPress-based environment to demonstrate common web application assessment concepts.

### Topics Discussed

* Administrative Interfaces
* File Management
* Web Application Architecture
* Server-Side Scripting

### Key Learning

Web applications often become attack surfaces due to misconfigurations, weak credentials, or vulnerable components.

---

# Directory Enumeration

## Purpose

Directory enumeration helps discover:

* Hidden directories
* Sensitive files
* Administrative panels
* Backup files

### Importance

Hidden resources frequently provide useful information during security assessments.

### Key Learning

Enumeration should always be thorough and systematic.

---

# Reverse Shell Concept

## Overview

A reverse shell allows a target system to initiate a connection back to an authorized testing machine.

### Security Perspective

Understanding reverse shell behavior helps:

* Detect malicious activity
* Monitor network communications
* Improve defensive controls

### Key Learning

Reverse shell activity often generates identifiable network traffic and security alerts.

---

# Privilege Escalation Concepts

## Objective

Privilege escalation involves obtaining higher permissions on a system.

### Topics Discussed

* User Privileges
* Administrative Access
* Root Access
* Misconfiguration Abuse

### Resources Referenced

* GTFOBins

### Key Learning

Privilege escalation often occurs because of insecure configurations rather than software vulnerabilities.

---

# Linux System Exploration

## Commands Discussed

### User Verification

```bash
whoami
```

### Directory Listing

```bash
ls
```

### File Reading

```bash
cat filename
```

### File Searching

```bash
find
```

### Purpose

These commands assist security professionals in:

* System enumeration
* Information gathering
* Security assessments

---

# Nmap Usage

## Nmap Overview

Nmap is one of the most important network scanning tools used by security professionals.

### Purposes

* Host Discovery
* Port Scanning
* Service Identification
* Version Detection

### Key Learning

Scanning provides the foundation for vulnerability identification and subsequent testing activities.

---

# CEH Module Mapping

| Topic                         | CEH Module |
| ----------------------------- | ---------- |
| DNS & Whois                   | Module 02  |
| Information Gathering         | Module 02  |
| Nmap                          | Module 03  |
| Enumeration                   | Module 04  |
| Privilege Escalation Concepts | Module 06  |
| Reverse Shell Awareness       | Module 06  |
| Wireshark                     | Module 08  |
| HTTP Analysis                 | Module 08  |

---

# Homework Assigned

* Review Penetration Testing Fundamentals
* Research PHP Concepts
* Practice Enumeration Techniques
* Continue TryHackMe Labs
* Review DNS and Information Gathering Tools

---

# Key Takeaways

1. Proper lab setup is essential before security testing.
2. DNS and Whois provide valuable reconnaissance information.
3. Enumeration often reveals the most useful target information.
4. HTTP traffic can expose sensitive information due to lack of encryption.
5. Wireshark is an essential tool for packet analysis.
6. Privilege escalation commonly results from system misconfigurations.
7. Documentation is critical throughout the penetration testing process.

---

# Reflection

This class connected multiple CEH concepts into a practical workflow, demonstrating how reconnaissance, enumeration, traffic analysis, and system assessment work together during a penetration testing engagement. The session reinforced the importance of methodology, documentation, and understanding both offensive and defensive security perspectives.
