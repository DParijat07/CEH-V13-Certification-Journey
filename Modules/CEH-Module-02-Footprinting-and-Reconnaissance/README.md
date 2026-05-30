# CEH Module 02 - Footprinting and Reconnaissance

## Overview

This module focuses on Footprinting and Reconnaissance, the first phase of ethical hacking. The objective is to gather information about a target system, organization, or network before performing vulnerability assessment or penetration testing activities.

Reconnaissance helps ethical hackers understand the target environment and identify potential attack surfaces.

---

# CEH v13 Module Mapping

**Official CEH v13 Module:**

* Module 02: Footprinting and Reconnaissance

---

# Learning Objectives

* Understand the importance of reconnaissance
* Differentiate between passive and active reconnaissance
* Learn information gathering methodologies
* Identify target infrastructure components
* Understand domain and DNS enumeration
* Learn basic network scanning concepts
* Explore common reconnaissance tools

---

# Topics Covered

## Footprinting Fundamentals

* What is Footprinting
* Purpose of Information Gathering
* Attack Surface Identification
* Intelligence Gathering

---

## Reconnaissance Types

### Passive Reconnaissance

Information gathering without directly interacting with the target.

Examples:

* WHOIS lookup
* DNS record analysis
* Search engine research
* Public information gathering

### Active Reconnaissance

Information gathering through direct interaction with the target.

Examples:

* Ping sweeps
* Port scanning
* Service enumeration
* Nmap scanning

---

## Information Collected

* Domain names
* IP addresses
* DNS records
* Subdomains
* Open ports
* Running services
* Operating systems
* Network ranges

---

# Tools Introduced

## Online Tools

* WHOIS Lookup
* DNSChecker
* ViewDNS.info
* Subdomain Finder

## Command-Line Tools

### NSLookup

Used to query DNS information.

Example:

```bash
nslookup example.com
```

### Nmap

Used for:

* Host discovery
* Port scanning
* Service detection
* OS detection

Example:

```bash
nmap -sV <target-ip>
```

---

# Home Lab Mapping

## Attack Machine

### Kali Linux

Used for:

* Reconnaissance
* Scanning
* Enumeration
* Ethical Hacking Practice

---

## Victim Machines

### Windows 7

Used for:

* Windows Security Testing
* Enumeration Practice

### Metasploitable 2

Used for:

* Vulnerability Discovery
* Service Enumeration
* Nmap Practice

---

# Future Lab Expansion

## Ubuntu Server + Wazuh

Planned implementation:

* Wazuh Manager
* Security Monitoring
* Log Analysis
* Threat Detection

Victim machines will have:

* Wazuh Agents Installed

---

# Practical Activities

* WHOIS Lookups
* DNS Enumeration
* Domain Investigation
* Subdomain Discovery
* Nmap Scanning Concepts
* Network Identification
* Lab Environment Preparation

---

# Hands-On Platforms

* TryHackMe
* VMware Workstation
* Kali Linux
* Metasploitable 2
* Windows 7

---

# Repository Structure

## Class-Notes

Contains module-related theory and class notes.

## Daily-Journal

Contains daily learning reflections and progress tracking.

## TryHackMe-Writeups

Contains room writeups mapped to reconnaissance and networking concepts.

## Screenshots

Contains screenshots of tools, labs, scans, and practical activities.

---

# Key Takeaways

* Reconnaissance is the foundation of ethical hacking.
* Information gathering helps identify attack surfaces.
* Passive reconnaissance minimizes detection risk.
* Active reconnaissance provides deeper technical insights.
* Proper reconnaissance improves the effectiveness of vulnerability assessments and penetration tests.

---

# Status

Module In Progress 🚀
