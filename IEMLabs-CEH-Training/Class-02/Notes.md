## Class 02 Lab Notes

Date- 01/06/2026

### Objective

Learn how to identify hosts in a network, perform reconnaissance, discover services, identify vulnerabilities, and understand the exploitation lifecycle in a controlled lab environment.

---

## Lab Environment

### Attacker Machine

* Kali Linux
* VMware Workstation

### Victim Machine

* Windows 7
* VMware Workstation

### Network Configuration

* NAT Network

Purpose:

* Allow communication between Kali Linux and Windows 7.
* Simulate a small internal network.

---

## Phase 1: Host Discovery

### Netdiscover

Used to identify active hosts on the network.

Command:

```bash
netdiscover
```

Result:

* Identified active devices in the subnet.
* Obtained Windows 7 target IP address.

---

### ARP Scan

Used to enumerate live hosts using ARP requests.

Command:

```bash
arp-scan -l
```

Result:

* Confirmed target system presence.
* Verified local network hosts.

---

## Phase 2: Port Scanning

### Basic Nmap Scan

Command:

```bash
nmap <target-ip>
```

Purpose:

* Discover open ports.

Result:

* Port 445/TCP found open.
* Service identified as Microsoft-DS (SMB).

---

## Phase 3: Service Enumeration

### Version Detection Scan

Command:

```bash
nmap -sV <target-ip>
```

Purpose:

* Identify service versions.

Result:

* Confirmed Windows 7 operating system.
* SMB service detected.

---

## Phase 4: Vulnerability Assessment

### NSE Vulnerability Scan

Command:

```bash
nmap --script vuln <target-ip>
```

Purpose:

* Identify known vulnerabilities.

Finding:

* SMB vulnerability detected.
* MS17-010 (EternalBlue) identified.

Risk:

* Remote Code Execution.
* Potential complete system compromise.

---

## Phase 5: Exploitation Overview

A controlled demonstration was performed using Metasploit Framework against the vulnerable Windows 7 system.

General Steps:

1. Select exploit module.
2. Configure target parameters.
3. Launch exploit.
4. Obtain Meterpreter session.

Outcome:

* Remote access obtained in lab environment.

---

## Phase 6: Post-Exploitation Concepts

Activities demonstrated:

### Process Enumeration

* Viewing active processes.

### Process Migration

* Migrating to a stable process.

Purpose:

* Improve session reliability.

### Credential Access Demonstration

* Password hash extraction techniques demonstrated.

### File System Interaction

* Creation of directories/files on the target machine.

Purpose:

* Understand post-exploitation capabilities.

---

## Key Learning Outcomes

* Host Discovery
* ARP Enumeration
* Nmap Scanning
* Service Enumeration
* Vulnerability Assessment
* Understanding Exploitation Workflow
* Post-Exploitation Concepts
* Importance of Patch Management

---

## Defensive Perspective

Mitigation for MS17-010:

* Apply Microsoft security updates.
* Disable SMBv1.
* Segment networks.
* Enable endpoint protection.
* Monitor SMB traffic.
* Implement vulnerability management programs.

---

## Tools Used

* VMware Workstation
* Kali Linux
* Windows 7
* Netdiscover
* ARP-Scan
* Nmap
* Metasploit Framework

---

## Key Learning Outcomes

- Understand Layer 2 host discovery techniques
- Identify live hosts using ARP-based scanning
- Perform TCP port scanning using Nmap
- Enumerate services and versions
- Understand SMB enumeration concepts
- Conduct vulnerability identification using NSE scripts
- Analyze scan results and prioritize findings
- Learn the network scanning phase of a VAPT assessment

## Ethical Reminder

All testing was performed in a controlled lab environment for educational purposes only.
