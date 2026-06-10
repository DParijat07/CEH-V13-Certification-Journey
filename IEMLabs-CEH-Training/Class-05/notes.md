# Class Notes - IEMLabs CEH Training

## Class 05 - Metasploitable 2 Enumeration and Exploitation

**Date:** 10/06/2026

---

# Objective

Learn the methodology of:

1. Host Discovery
2. Network Enumeration
3. Service Enumeration
4. Operating System Identification
5. Basic Exploitation using Metasploit Framework

Target Machine: **Metasploitable 2**

Attacker Machine: **Kali Linux**

---

# 1. Host Discovery

Before performing any attack, the target machine must be identified on the network.

## ARP Scan

ARP (Address Resolution Protocol) scanning is used to discover live hosts within the local network.

### Command

```bash
sudo arp-scan --localnet
```

### Purpose

* Identify active hosts.
* Obtain IP addresses.
* Collect MAC addresses.

### Advantages

* Fast host discovery.
* Effective on local networks.
* Useful when ICMP is blocked.

---

## Netdiscover

Netdiscover is another tool used for discovering hosts on a LAN.

### Command

```bash
sudo netdiscover
```

### Purpose

* Passive and active host discovery.
* Identify devices connected to the network.

### Information Gathered

* IP Address
* MAC Address
* Vendor Information

---

# 2. Port Scanning and Service Enumeration

After identifying the target machine, Nmap is used to enumerate services.

## Nmap Scan

### Service Version Detection

```bash
nmap -sV <target-ip>
```

### Aggressive Scan

```bash
nmap -A <target-ip>
```

### Full TCP Port Scan

```bash
nmap -p- <target-ip>
```

### Purpose

* Discover open ports.
* Identify running services.
* Detect service versions.
* Gather information for vulnerability assessment.

---

# 3. Operating System Identification

## TTL Analysis

TTL (Time To Live) values can provide clues about the target operating system.

### Command

```bash
ping <target-ip>
```

### Common TTL Values

| TTL Value | Possible OS               |
| --------- | ------------------------- |
| 64        | Linux / Unix              |
| 128       | Windows                   |
| 255       | Network Devices / Routers |

### Example

```bash
ping 192.168.1.10
```

Output:

```text
ttl=64
```

Likely Operating System:

```text
Linux
```

### Note

TTL values are indicators only and should not be considered definitive OS identification.

---

# 4. Metasploit Framework

Metasploit Framework is a penetration testing platform used for vulnerability validation and exploitation.

## Starting Metasploit

```bash
msfconsole
```

---

# Important Metasploit Commands

## Search Modules

```bash
search <service-name>
```

Example:

```bash
search ftp
```

---

## Use a Module

```bash
use <module-path>
```

Example:

```bash
use exploit/unix/ftp/...
```

---

## Show Options

```bash
show options
```

Displays required parameters.

---

## Configure Target

```bash
set RHOSTS <target-ip>
```

---

## Run Module

```bash
run
```

or

```bash
exploit
```

---

# 5. Port 21 - FTP Enumeration and Exploitation

## FTP Overview

FTP (File Transfer Protocol) is used for transferring files between systems.

### Default Port

```text
21/TCP
```

### Enumeration Goals

* Anonymous login
* Weak credentials
* Service version identification
* Vulnerable FTP software

### Basic FTP Connection

```bash
ftp <target-ip>
```

---

## Metasploit Usage

Search FTP-related modules:

```bash
search ftp
```

### Learning Outcome

* Identify FTP vulnerabilities.
* Understand FTP service exploitation workflow.

---

# 6. Port 22 - SSH Enumeration

## SSH Overview

SSH (Secure Shell) provides encrypted remote access.

### Default Port

```text
22/TCP
```

### Enumeration Goals

* Service version detection
* Weak credential identification
* User enumeration opportunities

### Manual Connection

```bash
ssh username@<target-ip>
```

---

## Metasploit Usage

Search SSH modules:

```bash
search ssh
```

### Learning Outcome

* Understand SSH attack surface.
* Learn auxiliary modules used for SSH enumeration.

---

# 7. Port 23 - Telnet Enumeration and Exploitation

## Telnet Overview

Telnet is an unencrypted remote administration protocol.

### Default Port

```text
23/TCP
```

### Risks

* Plain-text authentication.
* Credentials transmitted without encryption.

### Manual Connection

```bash
telnet <target-ip>
```

---

## Metasploit Usage

Search Telnet modules:

```bash
search telnet
```

### Learning Outcome

* Understand the insecurity of Telnet.
* Learn how attackers identify and validate Telnet weaknesses.

---

# Penetration Testing Workflow Learned

```text
Host Discovery
      ↓
Port Scanning
      ↓
Service Enumeration
      ↓
OS Identification
      ↓
Vulnerability Identification
      ↓
Exploitation
      ↓
Post Exploitation
```

---

# Key Takeaways

* Use arp-scan and netdiscover for host discovery.
* Use Nmap for service and version enumeration.
* Use TTL values as a basic OS fingerprinting technique.
* Understand Metasploit Framework structure.
* Learn the purpose of auxiliary and exploit modules.
* Enumerate FTP, SSH, and Telnet services before attempting exploitation.
* Follow a structured penetration testing methodology.

---

# Next Class Goals

* Enumerate remaining Metasploitable 2 services.
* Explore SMB enumeration.
* Perform web service enumeration.
* Investigate database services.
* Learn SQL Injection basics.
* Continue Metasploit practice.
* Improve manual enumeration skills.

---

**Class:** 05
**Training Program:** CEH v13 AI (IEMLabs)
**Target Machine:** Metasploitable 2
**Attacker Machine:** Kali Linux
**Status:** Completed
