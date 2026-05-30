# Module 02 - Class Notes

This directory contains class notes, revision notes, and instructor-led learning materials related to **CEH v13 Module 02: Footprinting and Reconnaissance**.

The notes in this section are based on:

* Institute classes
* Personal research
* CEH v13 syllabus topics
* Practical reconnaissance exercises
* Home lab activities

---

# Topics Covered

## Information Gathering Fundamentals

* What is Footprinting
* What is Reconnaissance
* Importance of Information Gathering
* Intelligence Gathering Process

---

## Reconnaissance Types

### Passive Reconnaissance

Information gathering without directly interacting with the target.

Examples:

* WHOIS lookup
* DNS records analysis
* Search engine research
* Public information gathering

### Active Reconnaissance

Information gathering through direct interaction with the target.

Examples:

* Network scanning
* Host discovery
* Port scanning
* Service enumeration

---

## DNS and Domain Enumeration

Topics include:

* Domain Name System (DNS)
* Domain-to-IP Resolution
* DNS Records
* Subdomain Discovery
* Registrar Information

---

## Reconnaissance Tools

### Online Tools

* WHOIS Lookup
* DNSChecker
* ViewDNS.info
* Subdomain Finder

### Command-Line Tools

#### NSLookup

Used to query DNS information.

Example:

```bash
nslookup example.com
```

#### Nmap

Used for:

* Host discovery
* Port scanning
* Service version detection

Example:

```bash
nmap -sV <target-ip>
```

---

# Home Lab Mapping

The following lab machines are used to practice reconnaissance concepts:

## Kali Linux

Used as:

* Attack Machine
* Scanning Machine
* Enumeration Machine

## Windows 7

Used as:

* Victim Machine
* Service Enumeration Target

## Metasploitable 2

Used as:

* Vulnerable Practice Machine
* Network Scanning Target

---

# Future Learning Goals

* Advanced DNS Enumeration
* Network Mapping
* Service Enumeration
* OS Fingerprinting
* Nmap Practical Labs
* Reconnaissance Automation

---

# Purpose of This Directory

This directory helps me:

* Track institute class learning
* Organize CEH theory notes
* Document practical reconnaissance concepts
* Build future trainer-level reference material
* Create structured cybersecurity documentation

---

# Status

Module 02 Notes Collection In Progress 🚀
