# CEH v13 Module 03 – Scanning Networks

# README.md

## Overview

Network scanning is the second operational phase of ethical hacking, performed after reconnaissance and footprinting. During this phase, ethical hackers actively interact with target systems to discover live hosts, open ports, running services, operating systems, and potential attack vectors.

The primary objective of network scanning is to identify accessible systems and collect technical information that will be used during enumeration, vulnerability assessment, and exploitation.

Scanning provides visibility into the target's network infrastructure and helps security professionals understand which services are exposed, which operating systems are running, and what security mechanisms may be present.

Because network scanning directly communicates with target systems, it is considered **active reconnaissance** and should only be performed with proper authorization.

---

# Learning Objectives

After completing this module, you should be able to:

- Understand the purpose of network scanning.
- Explain the network scanning methodology.
- Discover live hosts on a network.
- Identify open TCP and UDP ports.
- Perform port scanning using different scan techniques.
- Identify running services and service versions.
- Perform operating system fingerprinting.
- Understand banner grabbing.
- Use Nmap and other scanning tools.
- Understand firewall and IDS/IPS detection.
- Recognize scan evasion concepts.
- Recommend defensive countermeasures.

---

# Why Network Scanning Matters

Reconnaissance identifies **what may exist**.

Scanning verifies **what actually exists**.

Network scanning helps identify:

- Live hosts
- Network topology
- Open ports
- Running services
- Service versions
- Operating systems
- Firewalls
- IDS/IPS
- Security controls
- Potential vulnerabilities

Without proper scanning, later penetration testing phases become significantly less effective.

---

# Network Scanning Methodology

The general workflow is:

```
Target Identification
        ↓
Host Discovery
        ↓
Port Scanning
        ↓
Service Enumeration
        ↓
Operating System Detection
        ↓
Version Detection
        ↓
Vulnerability Assessment
```

Each stage provides additional technical information about the target environment.

---

# Module Topics

This module covers:

- Network Scanning Fundamentals
- Host Discovery
- Ping Sweeps
- ARP Discovery
- ICMP Discovery
- TCP Discovery
- UDP Discovery
- Port Scanning
- TCP Port Scanning
- UDP Port Scanning
- Port States
- Banner Grabbing
- Service Enumeration
- Version Detection
- Operating System Fingerprinting
- Nmap
- Zenmap
- Masscan
- Angry IP Scanner
- Netcat
- Hping3
- Unicornscan
- Wireshark (Scanning Perspective)
- Firewall Detection
- IDS/IPS
- Scan Evasion Concepts
- Countermeasures

---

# Common Scanning Tools

The following tools are commonly used during network scanning.

## Host Discovery

- Ping
- ARP
- Traceroute

---

## Network Scanners

- Nmap
- Zenmap
- Masscan
- Angry IP Scanner
- Unicornscan

---

## Enumeration Tools

- Netcat
- Telnet
- Nmap NSE
- Banner Grabbing Utilities

---

## Packet Analysis

- Wireshark
- tcpdump

---

## Packet Crafting

- Hping3

---

# Practical Skills You'll Learn

After completing this module, you should be able to:

- Discover live hosts.
- Perform TCP and UDP scans.
- Identify open ports.
- Enumerate running services.
- Detect operating systems.
- Capture banners.
- Use Nmap effectively.
- Interpret scan results.
- Understand firewall behavior.
- Produce professional scanning reports.

---

# Real-World Applications

Network scanning is widely used in:

- Penetration Testing
- Vulnerability Assessment
- Security Audits
- Red Team Operations
- Blue Team Validation
- Asset Discovery
- Network Inventory
- Compliance Assessments
- Incident Response

---

# Defensive Perspective

Organizations should:

- Monitor scanning activity.
- Restrict unnecessary services.
- Close unused ports.
- Deploy host-based firewalls.
- Configure IDS/IPS.
- Enable logging.
- Perform regular vulnerability assessments.
- Conduct internal asset inventories.

---

# CEH Exam Tips

Remember:

- Network scanning follows reconnaissance.
- Host discovery identifies live systems.
- Port scanning identifies accessible services.
- Banner grabbing identifies software.
- Service enumeration identifies running applications.
- OS fingerprinting identifies operating systems.
- Nmap is the most commonly used scanning tool.
- Firewalls and IDS/IPS may detect active scans.
- Scanning should always be authorized.

---

# Module Summary

Module 03 introduces the active information gathering techniques used to identify hosts, ports, services, and operating systems. Ethical hackers use scanning tools such as Nmap to verify the information collected during reconnaissance and to build a detailed understanding of the target's network.

Effective network scanning enables security professionals to identify exposed services, validate attack surfaces, prioritize vulnerability assessments, and support later penetration testing activities while also helping defenders identify and secure unnecessary network exposure.

---

# Recommended Practice

To reinforce this module:

- Scan a lab network using Nmap.
- Perform host discovery using ICMP and ARP.
- Identify open TCP and UDP ports.
- Practice service version detection.
- Perform OS fingerprinting in a lab.
- Compare different Nmap scan types.
- Observe scanning traffic using Wireshark.

---

# Key Takeaways

- Network scanning transforms passive reconnaissance into verified technical information by identifying live hosts, open ports, running services, and operating systems.
- Understanding scanning techniques and defensive controls enables both ethical hackers and defenders to accurately assess network exposure while minimizing unnecessary security risks.
