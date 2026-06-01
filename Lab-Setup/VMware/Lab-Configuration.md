# VMware Configuration

## Overview

This document describes the VMware Workstation configuration used for my cybersecurity home lab. The lab is designed to support CEH studies, TryHackMe learning, vulnerability assessments, network scanning, penetration testing practice, and cybersecurity project development.

The environment consists of multiple virtual machines running in an isolated network for safe learning and experimentation.

---

# Lab Objectives

The VMware lab is used to:

* Learn cybersecurity fundamentals
* Practice network scanning and enumeration
* Perform vulnerability assessments
* Understand penetration testing methodologies
* Build hands-on experience with security tools
* Develop cybersecurity projects and reports
* Prepare for CEH certification and practical labs

---

# Virtualization Platform

| Component             | Details                         |
| --------------------- | ------------------------------- |
| Software              | VMware Workstation              |
| Purpose               | Virtual Machine Management      |
| Host Operating System | Windows 10/11                   |
| Lab Type              | Isolated Cybersecurity Home Lab |

---

# Lab Architecture

```text
Host Machine (Windows)
        │
        ▼
VMware Workstation
        │
        ▼
Virtual Network
│
├── Kali Linux
│     (Attacker Machine)
│
├── Windows 7
│     (Victim Machine)
│
└── Metasploitable 2
      (Vulnerable Linux Target)
```

---

# Virtual Machines

## Kali Linux

### Purpose

Primary attacker and security testing machine.

### Use Cases

* Network Scanning
* Service Enumeration
* Vulnerability Assessment
* Security Research
* Penetration Testing Practice
* Report Preparation

### Configuration

| Setting          | Value      |
| ---------------- | ---------- |
| Operating System | Kali Linux |
| Role             | Attacker   |
| RAM              | 4 GB       |
| CPU              | 2 Cores    |
| Storage          | 50 GB      |
| Network Adapter  | NAT        |
| Status           | Active     |

### Common Tools

* Nmap
* Wireshark
* Metasploit Framework
* Netdiscover
* Burp Suite
* Hydra
* John the Ripper

---

## Windows 7

### Purpose

Vulnerable Windows target for security testing and learning.

### Use Cases

* Network Scanning Practice
* Vulnerability Analysis
* Service Enumeration
* CEH Lab Exercises

### Configuration

| Setting          | Value          |
| ---------------- | -------------- |
| Operating System | Windows 7      |
| Role             | Victim Machine |
| RAM              | 2 GB           |
| CPU              | 2 Cores        |
| Storage          | 40 GB          |
| Network Adapter  | NAT            |
| Status           | Active         |

### Notes

This system is maintained for educational purposes only and contains intentionally outdated software suitable for cybersecurity training.

---

## Metasploitable 2

### Purpose

Intentionally vulnerable Linux machine used for learning offensive and defensive security concepts.

### Use Cases

* Enumeration Practice
* Vulnerability Assessment
* Exploitation Labs
* Privilege Escalation Labs
* Service Analysis

### Configuration

| Setting          | Value                  |
| ---------------- | ---------------------- |
| Operating System | Ubuntu Linux           |
| Distribution     | Metasploitable 2       |
| Role             | Vulnerable Target      |
| RAM              | 1 GB                   |
| CPU              | 1 Core                 |
| Storage          | Default Appliance Disk |
| Network Adapter  | NAT                    |
| Status           | Active                 |

### Notes

Metasploitable 2 is prepared for future practical exercises and self-learning activities.

---

# Network Configuration

## Network Type

### NAT (Network Address Translation)

The virtual machines are connected using VMware NAT networking.

### Benefits

* Internet access for virtual machines
* Communication between virtual machines
* Isolation from external networks
* Safe cybersecurity testing environment

### Current Network Members

| Device           | Role              |
| ---------------- | ----------------- |
| Kali Linux       | Attacker          |
| Windows 7        | Victim            |
| Metasploitable 2 | Vulnerable Target |

---

# Host Discovery Workflow

The following workflow is used to identify systems in the lab environment.

### Step 1

Identify Kali Linux network information.

### Step 2

Discover active hosts.

Common tools:

* Netdiscover
* ARP-Scan

### Step 3

Identify target IP addresses.

### Step 4

Verify connectivity.

### Step 5

Perform scanning and enumeration.

---

# VMware Folder Organization

```text
Lab-Setup/
│
└── VMware/
    │
    ├── README.md
    ├── VMware-Configuration.md
    ├── Kali-Linux.md
    ├── Windows7.md
    ├── Metasploitable2.md
    │
    └── Screenshots/
        ├── VMware-Dashboard.png
        ├── Kali-Settings.png
        ├── Windows7-Settings.png
        ├── Metasploitable2-Settings.png
        └── Network-Configuration.png
```

---

# Snapshot Management

To ensure safe testing, snapshots are maintained at key stages.

## Snapshot 1

Fresh Installation

Purpose:

* Clean operating system state

## Snapshot 2

Post Configuration

Purpose:

* Restore point after networking setup

## Snapshot 3

Pre-Lab

Purpose:

* Restore point before practical exercises

## Snapshot 4

Stable Working State

Purpose:

* Quick recovery after testing

---

# Security Guidelines

## Allowed Activities

* Vulnerability Assessment
* Enumeration
* Network Scanning
* CEH Practice Labs
* TryHackMe Learning
* Documentation Projects

## Restricted Activities

* Testing systems without authorization
* Scanning public networks
* Conducting attacks outside the lab environment
* Storing sensitive personal data in lab machines

---

# Current Learning Focus

The VMware lab currently supports:

## CEH Modules

* Module 03 – Scanning Networks
* Module 04 – Enumeration
* Module 05 – Vulnerability Analysis
* Module 06 – System Hacking

## Practical Skills

* Network Discovery
* Host Enumeration
* Service Enumeration
* Vulnerability Assessment
* Security Reporting
* Home Lab Administration

---

# Future Expansion

Planned additions to the lab:

* Windows 10
* Ubuntu Server
* Security Onion
* DVWA
* OWASP Juice Shop
* Active Directory Environment

---

# Maintenance Checklist

* Verify VM functionality
* Confirm network connectivity
* Create snapshots regularly
* Backup important documentation
* Update VMware Workstation
* Maintain lab notes and reports

---

## Conclusion

This VMware-based cybersecurity lab provides a structured and isolated environment for learning, experimentation, and practical cybersecurity training. It serves as the foundation for CEH studies, TryHackMe exercises, vulnerability assessment projects, and future penetration testing practice.

**Maintained By:** Parijat Das

**Purpose:** Cybersecurity Learning, Research, and Professional Development
