# CEH Module 02 - Footprinting and Reconnaissance

## Module Overview

Footprinting and Reconnaissance is the first phase of ethical hacking.
In this phase, an ethical hacker gathers information about a target system, network, or organization before performing any attack or vulnerability assessment.

The goal is to collect as much information as possible while understanding:

* target infrastructure
* IP addresses
* domains
* subdomains
* technologies
* operating systems
* exposed services

This module also introduced the importance of setting up a cybersecurity home lab for practical learning.

---

# Learning Objectives

* Understand footprinting and reconnaissance concepts
* Learn passive and active reconnaissance techniques
* Understand information gathering methodology
* Learn basic network scanning concepts
* Explore reconnaissance tools
* Understand practical lab environments

---

# What is Footprinting?

Footprinting is the process of collecting information about a target system or organization.

It helps ethical hackers:

* identify attack surfaces
* understand network structure
* detect exposed services
* gather intelligence before scanning or exploitation

---

# Reconnaissance Types

## Passive Reconnaissance

Information gathering without directly interacting with the target system.

### Examples

* WHOIS lookup
* DNS information gathering
* searching public records
* Google Dorking
* subdomain enumeration

### Advantages

* difficult to detect
* safe information gathering

---

## Active Reconnaissance

Direct interaction with the target system or network.

### Examples

* ping sweep
* port scanning
* Nmap scanning
* service detection

### Risks

* may generate logs
* may trigger alerts or IDS systems

---

# Information Gathered During Reconnaissance

* Domain names
* IP addresses
* DNS records
* Subdomains
* Open ports
* Running services
* Operating systems
* Email addresses
* Network ranges

---

# Tools Introduced

## NSLookup

Used for:

* domain-to-IP resolution
* DNS queries

Example:

```bash
nslookup example.com
```

---

# WHOIS Lookup

Used to gather:

* domain registration details
* registrar information
* registration dates
* expiration dates

---

# DNSChecker

Used to:

* verify DNS propagation
* analyze DNS records

---

# ViewDNS.info

Used for:

* DNS analysis
* reverse IP lookup
* domain information gathering

---

# Subdomain Finder

Used to:

* identify subdomains
* map target infrastructure

---

# Google Dorking

Google Dorking is an information gathering technique that uses advanced search queries to discover exposed or sensitive information.

Example:

```text
site:example.com
```

---

# Nmap Introduction

Nmap is a network scanning tool used for:

* host discovery
* port scanning
* service detection
* operating system detection

---

# Basic Nmap Concepts

## Service Version Detection

```bash
nmap -sV <target-ip>
```

Used to identify:

* service versions
* software information

---

# Aggressive Scan

```bash
nmap -A <target-ip>
```

Performs:

* OS detection
* version detection
* script scanning
* traceroute

---

# Timing Templates

Nmap timing templates:

* T1 (slow)
* T2
* T3
* T4 (faster)
* T5 (very aggressive)

Example:

```bash
nmap -T4 <target-ip>
```

---

# Home Lab Setup

A cybersecurity home lab is important for safe practical learning.

---

# Hypervisor Used

## VMware Workstation

Used to create virtual machines for:

* penetration testing
* vulnerability analysis
* networking practice

---

# Lab Machines Configured

## Attack Machine

### Kali Linux

Purpose:

* reconnaissance
* scanning
* exploitation
* penetration testing

---

# Victim Machines

## Windows 7

Used for:

* Windows testing
* vulnerability practice

## Metasploitable 2

Intentionally vulnerable Linux machine used for:

* exploitation practice
* Nmap scanning
* service enumeration

---

# Future Lab Expansion

## Ubuntu Server with Wazuh

Planned future setup:

* Wazuh SIEM server
* log monitoring
* attack detection
* threat monitoring

Victim machines will contain:

* Wazuh agents

This setup will help in learning:

* SOC operations
* threat analysis
* blue team monitoring

---

# CEH Relevance

Footprinting and reconnaissance are critical because:

* attackers first gather intelligence
* ethical hackers must understand target environments
* proper reconnaissance improves vulnerability assessment accuracy

This phase forms the foundation for:

* scanning
* exploitation
* privilege escalation
* vulnerability analysis

---

# Key Learnings

* Reconnaissance is the first phase of ethical hacking
* Passive reconnaissance avoids direct interaction
* Active reconnaissance directly interacts with targets
* Nmap is one of the most important network scanning tools
* Home labs are essential for practical cybersecurity learning
* Proper documentation improves long-term skill development

---

# Practical Exposure

* WHOIS lookups
* NSLookup usage
* Nmap scanning concepts
* VM-based cybersecurity lab setup
* Network scanning basics
* Linux-based reconnaissance tools
