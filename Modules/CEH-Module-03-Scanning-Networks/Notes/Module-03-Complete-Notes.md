# Module 03 – Scanning Networks

## Part 1 – Network Scanning Concepts and Host Discovery

---

# Overview

Network scanning is an important phase of ethical hacking that follows reconnaissance and footprinting. While reconnaissance focuses on collecting information about a target, network scanning is used to identify active systems, reachable hosts, and network resources.

Ethical hackers use scanning techniques to understand the target network and identify systems that require further enumeration and vulnerability assessment.

---

# What is Network Scanning?

## Definition

Network scanning is the process of sending probes or requests to a target network to identify active hosts, open ports, network services, and other characteristics of the target environment.

It provides technical information that helps an ethical hacker understand the attack surface of an authorized network.

---

# Objectives of Network Scanning

The primary objectives are to:

- Identify live hosts
- Discover active IP addresses
- Determine reachable systems
- Identify open ports
- Discover network services
- Identify operating systems
- Support vulnerability assessment
- Map the target network

---

# Network Scanning Process

A typical network scanning process can be represented as:

```text
Target Network
      ↓
Host Discovery
      ↓
Port Scanning
      ↓
Service Detection
      ↓
OS Detection
      ↓
Enumeration
      ↓
Vulnerability Assessment
```

---

# Host Discovery

## Definition

Host discovery is the process of identifying systems that are active or reachable within a target network.

Before performing detailed port scanning, an ethical hacker can first determine which hosts are responding.

---

# Importance of Host Discovery

Host discovery helps ethical hackers to:

- Identify active systems
- Reduce unnecessary scanning
- Save scanning time
- Reduce network traffic
- Build an initial network inventory
- Identify systems for further assessment

---

# ICMP Host Discovery

## Definition

Internet Control Message Protocol (ICMP) is commonly used for network diagnostics and error reporting.

The `ping` utility commonly uses ICMP Echo Request and Echo Reply messages to determine whether a host responds.

Example:

```bash
ping 192.168.1.10
```

Basic communication:

```text
Scanner
   ↓
ICMP Echo Request
   ↓
Target
   ↓
ICMP Echo Reply
   ↓
Scanner
```

---

# Ping Sweep

## Definition

A ping sweep is a technique used to identify multiple active hosts within a network range.

For example, an ethical hacker may test:

```text
192.168.1.1
192.168.1.2
192.168.1.3
...
192.168.1.254
```

The objective is to determine which IP addresses are associated with responding systems.

---

# Limitations of ICMP Discovery

ICMP-based discovery is not always reliable.

A system may be active but fail to respond because of:

- Firewall rules
- ICMP filtering
- Network ACLs
- Host configuration
- Network segmentation

Therefore:

> **No ICMP response does not necessarily mean that the host is offline.**

---

# ARP Discovery

## Definition

Address Resolution Protocol (ARP) is used to resolve IPv4 addresses into MAC addresses within a local network.

ARP discovery can be particularly effective for identifying hosts on the same local network segment.

Basic process:

```text
Scanner
   ↓
ARP Request
   ↓
Local Network
   ↓
ARP Reply
   ↓
Scanner
```

---

# Advantages of ARP Discovery

ARP discovery can:

- Identify local hosts
- Provide MAC address information
- Work when ICMP is filtered
- Effectively discover systems within the local broadcast domain

---

# Limitations of ARP Discovery

ARP is primarily a Layer 2 protocol and is generally limited to the local network segment.

It is not normally used to discover hosts across routed networks.

---

# TCP Host Discovery

TCP-based host discovery uses TCP probes to determine whether a target system is reachable.

Depending on the probe and target configuration, responses such as the following may provide evidence of a reachable host:

```text
SYN/ACK
RST
```

TCP-based discovery can be useful when ICMP is blocked.

---

# UDP Host Discovery

UDP-based host discovery sends UDP probes to selected ports.

Possible responses include:

- UDP application response
- ICMP Port Unreachable
- No response

UDP discovery can be difficult to interpret because many UDP services do not respond to unexpected traffic.

---

# Multiple Host Discovery Techniques

A professional assessment may combine multiple discovery techniques.

```text
ICMP
  +
ARP
  +
TCP
  +
UDP
  ↓
Host Discovery
```

Using multiple techniques can improve visibility when one method is blocked or filtered.

---

# Nmap Host Discovery

Nmap is one of the most widely used network scanning tools.

Nmap provides several host discovery techniques.

The `-sn` option performs host discovery without performing a conventional port scan.

Example:

```bash
nmap -sn 192.168.1.0/24
```

---

# Information Nmap Can Identify

Depending on the network configuration and scanning privileges, Nmap may identify:

- IP address
- Host status
- Hostname
- MAC address
- Hardware vendor
- Network latency

Example:

```text
Nmap scan report for 192.168.1.10
Host is up.
MAC Address: XX:XX:XX:XX:XX:XX
```

---

# Host Discovery and Firewalls

Firewalls can affect host discovery results.

Example:

```text
Scanner
   ↓
ICMP Request
   ↓
Firewall
   ↓
Blocked
```

The scanner may receive no response even though the target system is running.

For this reason, ethical hackers should avoid depending on only one host discovery technique.

---

# Network Scanning vs Footprinting

| Footprinting | Network Scanning |
|---|---|
| Information gathering | Technical verification |
| Often passive | Primarily active |
| Uses public sources | Interacts with target systems |
| Domains and organizational information | Hosts, ports and services |
| Lower detection risk | Higher detection risk |

---

# Network Scanning and Security Monitoring

Network scanning generates traffic that can be detected by security controls.

Security devices may identify:

- ICMP sweeps
- Repeated probes
- Multiple connection attempts
- Traffic directed toward many hosts
- Traffic directed toward many ports

Potential monitoring sources include:

- Firewalls
- IDS
- IPS
- SIEM
- Network monitoring systems

---

# Defensive Measures

Organizations can reduce unnecessary exposure by:

- Restricting unnecessary network traffic
- Using network segmentation
- Closing unnecessary services
- Monitoring network activity
- Deploying IDS/IPS
- Maintaining accurate asset inventories
- Reviewing firewall and ACL configurations

---

# CEH Exam Tips

Remember:

- Network scanning is primarily an active information-gathering technique.
- Host discovery identifies active or reachable systems.
- ICMP Echo Request/Reply is commonly associated with `ping`.
- ARP discovery is particularly useful on local networks.
- ARP operates at Layer 2.
- TCP and UDP can also be used for host discovery.
- Nmap `-sn` performs host discovery without a conventional port scan.
- A host may be online even if it does not respond to ICMP.
- Firewalls can affect host discovery results.
- Multiple discovery techniques can improve accuracy.

---

# Key Takeaways

- Network scanning helps ethical hackers identify active systems and understand the technical attack surface of an authorized network.
- Host discovery is generally performed before detailed port scanning.
- ICMP, ARP, TCP, and UDP are commonly used for host discovery.
- ARP is particularly effective for discovering systems on a local network.
- Firewalls and other security controls can interfere with host discovery, so multiple techniques may be required.
- Nmap provides powerful host discovery capabilities and is an essential tool for network scanning during ethical hacking and penetration testing.







