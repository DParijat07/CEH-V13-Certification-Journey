# Module 08 — Sniffing

This directory contains practical exercises related to **Sniffing** from CEH v13.

The focus is on understanding network traffic capture, protocol analysis, packet inspection, and the security risks associated with unencrypted communications. Exercises are performed in controlled lab environments.

## Practical Areas

- Network traffic capture fundamentals
- Packet structure and protocol analysis
- TCP, UDP, and ICMP traffic inspection
- DNS traffic analysis
- HTTP and HTTPS traffic comparison
- ARP traffic analysis
- Network protocol identification
- Cleartext data exposure analysis
- Network traffic anomaly identification
- Defensive monitoring and mitigation

## Directory Structure

```text
Module-08/
│
├── 01-Network-Traffic-Capture/
├── 02-TCP-UDP-and-ICMP-Analysis/
├── 03-DNS-Traffic-Analysis/
├── 04-HTTP-and-HTTPS-Analysis/
├── 05-ARP-Traffic-Analysis/
├── 06-Cleartext-Data-Exposure/
└── 07-Traffic-Monitoring-and-Defense/
```

## Tools and Resources

Tools may include:

- Wireshark
- tcpdump
- TShark
- Kali Linux
- Browser developer tools
- Isolated virtual machines

Tool selection depends on the exercise objectives and lab environment.

## Practical Workflow

**Prepare Lab → Capture Traffic → Apply Filters → Inspect Packets → Identify Patterns → Analyze Security Implications → Document Findings**

## Evidence and Documentation

Each exercise should document, where applicable:

- Objective and authorized lab scope
- Network topology and environment
- Capture method and tools used
- Relevant packet captures or screenshots
- Protocols and traffic patterns observed
- Potential sensitive-data exposure
- Security implications
- Defensive recommendations
- Lessons learned

## Authorization and Safety

Capture traffic only on networks and systems you own or are explicitly authorized to monitor. Avoid collecting other users' credentials, private communications, or personal information. Use synthetic data and isolated lab traffic wherever possible.

## Learning Outcome

The objective is to develop practical skills in packet capture, protocol interpretation, traffic analysis, and identifying weaknesses caused by insecure network communications.

**CEH v13 Certification Journey — Practical Learning and Proof of Work**
