# Module 08 - Sniffing

## Overview

Sniffing is the process of capturing, monitoring, and analyzing network traffic as it traverses a network. Understanding packet analysis is a fundamental skill for both ethical hackers and security defenders. This module covers network traffic analysis, packet capture techniques, Man-in-the-Middle (MITM) attacks, protocol analysis, and the use of tools such as Wireshark, Tcpdump, Ettercap, and Bettercap.

This module is particularly important for SOC Analysts, Incident Responders, Threat Hunters, and Penetration Testers because many cyberattacks leave traces within network traffic.

---

## Learning Objectives

After completing this module, I should be able to:

* Understand network packet structure and communication.
* Explain passive and active sniffing techniques.
* Understand ARP and ARP Spoofing attacks.
* Explain Man-in-the-Middle (MITM) attacks.
* Analyze packets using Wireshark.
* Use display filters effectively.
* Capture and inspect network traffic.
* Understand DNS Spoofing and DHCP attacks.
* Investigate suspicious network behavior.
* Identify Indicators of Compromise (IOCs) from network traffic.
* Understand defensive mechanisms against sniffing attacks.

---

## Module Topics

### 1. Network Communication Fundamentals

* OSI Model Review
* TCP/IP Model
* Packet Structure
* Protocol Communication
* MAC Addresses
* IP Addresses

### 2. Sniffing Fundamentals

* What is Sniffing?
* Passive Sniffing
* Active Sniffing
* Network Visibility
* Attack and Defense Perspectives

### 3. Address Resolution Protocol (ARP)

* ARP Basics
* ARP Tables
* ARP Requests
* ARP Replies
* ARP Cache

### 4. ARP Spoofing

* ARP Poisoning
* MITM Attacks
* Traffic Interception
* Credential Theft Risks

### 5. DHCP Attacks

* DHCP Starvation
* Rogue DHCP Servers
* DHCP Security Risks

### 6. DNS Spoofing

* DNS Poisoning
* Traffic Redirection
* Phishing Risks

### 7. MAC Flooding

* CAM Table Overflow
* Switch Security Weaknesses
* Network Visibility Attacks

### 8. Wireshark

* Packet Capture
* Display Filters
* Protocol Analysis
* Follow TCP Stream
* Packet Inspection
* Traffic Analysis

### 9. Packet Analysis

* TCP Analysis
* UDP Analysis
* DNS Analysis
* HTTP Analysis
* HTTPS Considerations
* ICMP Analysis

### 10. Malware Traffic Analysis

* Command and Control (C2)
* DNS Tunneling
* Beaconing Activity
* Data Exfiltration Detection

### 11. Defensive Controls

* HTTPS
* VPN
* IDS/IPS
* Secure Switching
* ARP Protection

---

## Tools Covered

### Wireshark

Primary packet analysis tool used to:

* Capture network traffic
* Analyze packets
* Investigate incidents
* Detect malicious activity

### Tcpdump

Command-line packet capture utility.

### Tshark

Command-line version of Wireshark.

### Ettercap

Tool used for:

* ARP Spoofing
* MITM Attacks
* Traffic Interception

### Bettercap

Modern network attack and monitoring framework.

---

## Directory Structure

```text
CEH-Module-08-Sniffing/
│
├── README.md
│
├── Network-Fundamentals/
│   ├── OSI-Model.md
│   ├── TCP-IP-Model.md
│   └── Packet-Structure.md
│
├── Sniffing-Fundamentals/
│   ├── Passive-Sniffing.md
│   └── Active-Sniffing.md
│
├── ARP/
│   ├── ARP-Basics.md
│   └── ARP-Tables.md
│
├── ARP-Spoofing/
│   └── ARP-Poisoning.md
│
├── MITM/
│   └── MITM-Attacks.md
│
├── DHCP-Attacks/
│   └── DHCP-Starvation.md
│
├── DNS-Spoofing/
│   └── DNS-Poisoning.md
│
├── Wireshark/
│   ├── Installation.md
│   ├── Filters.md
│   ├── Packet-Analysis.md
│   ├── Follow-TCP-Stream.md
│   └── Labs.md
│
├── Tcpdump/
│   └── Basic-Commands.md
│
├── Ettercap/
│   └── Ettercap-Basics.md
│
├── Bettercap/
│   └── Bettercap-Basics.md
│
├── IOC-CheatSheet/
│   └── Network-IOCs.md
│
├── TryHackMe-Labs/
│   ├── Wireshark-The-Basics.md
│   ├── Packet-Operations.md
│   └── Traffic-Analysis.md
│
└── Screenshots/
```

---

## CEHv13 Mapping

| Topic            | CEH Module |
| ---------------- | ---------- |
| Packet Analysis  | Module 08  |
| ARP Spoofing     | Module 08  |
| MITM Attacks     | Module 08  |
| Traffic Analysis | Module 08  |
| Wireshark        | Module 08  |
| DNS Spoofing     | Module 08  |

---

## Related CEH Modules

### Previous Modules

* Module 03 – Network Scanning
* Module 04 – Enumeration

### Next Modules

* Module 09 – Social Engineering
* Module 10 – Denial of Service
* Module 11 – Session Hijacking

---

## Practical Labs

### TryHackMe

* Intro to LAN
* Wireshark: The Basics
* Wireshark Packet Operations
* Wireshark Traffic Analysis
* Network Services

### Home Lab

* Capture ICMP traffic.
* Capture DNS queries.
* Analyze HTTP requests.
* Analyze HTTPS traffic.
* Practice Wireshark filtering.
* Observe ARP communication.

---

## Key Takeaways

* Network traffic contains valuable security information.
* Sniffing can be used for both offensive and defensive purposes.
* Wireshark is one of the most important tools for network analysis.
* ARP Spoofing enables Man-in-the-Middle attacks.
* Packet analysis is a critical skill for SOC Analysts and Incident Responders.
* Understanding network traffic helps detect malware, intrusions, and suspicious behavior.

---

## Status

* [ ] Theory Completed
* [ ] Wireshark Fundamentals Completed
* [ ] Packet Analysis Practice Completed
* [ ] TryHackMe Labs Completed
* [ ] Documentation Completed
* [ ] Screenshots Added
* [ ] Module Revision Completed

---

## Notes

This module provides foundational knowledge for network traffic analysis, threat hunting, malware investigations, incident response, and SOC operations. Mastering Wireshark and packet analysis will significantly improve both offensive and defensive cybersecurity skills.
