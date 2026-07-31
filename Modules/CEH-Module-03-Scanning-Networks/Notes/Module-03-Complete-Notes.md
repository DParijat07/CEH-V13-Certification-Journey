# Module 03 – Scanning Networks

---

## Part 1 – Network Scanning Concepts and Host Discovery

---

# Overview

Network scanning is an important phase of ethical hacking that follows reconnaissance and footprinting. While reconnaissance focuses on collecting information about a target, network scanning is used to identify active systems, reachable hosts, network resources, open ports, and available services.

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
- Prepare for enumeration

---

# Network Scanning Process

A typical network scanning process can be represented as:

```text
Reconnaissance
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
      ↓
Reporting
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

> **Important:** No ICMP response does not necessarily mean that the host is offline.

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

---

## Part 2 – Port Scanning and Scanning Techniques

---

# Overview

After identifying active hosts, the next stage of network scanning is to determine which ports are accessible and what services may be running on those ports.

Port scanning helps an ethical hacker understand the exposed services of an authorized target.

---

# What is Port Scanning?

## Definition

Port scanning is the process of probing TCP or UDP ports on a target system to determine their state and identify potentially accessible services.

A port acts as a logical communication endpoint for network applications.

---

# Port Number Ranges

TCP and UDP ports range from:

```text
0 – 65535
```

They are commonly divided into:

| Range | Category |
|---|---|
| 0–1023 | Well-Known Ports |
| 1024–49151 | Registered Ports |
| 49152–65535 | Dynamic / Private Ports |

---

# Common Ports and Services

| Port | Protocol | Service |
|---:|---|---|
| 20 | TCP | FTP Data |
| 21 | TCP | FTP |
| 22 | TCP | SSH |
| 23 | TCP | Telnet |
| 25 | TCP | SMTP |
| 53 | TCP/UDP | DNS |
| 67/68 | UDP | DHCP |
| 69 | UDP | TFTP |
| 80 | TCP | HTTP |
| 110 | TCP | POP3 |
| 123 | UDP | NTP |
| 135 | TCP | MS RPC |
| 139 | TCP | NetBIOS |
| 143 | TCP | IMAP |
| 161 | UDP | SNMP |
| 389 | TCP/UDP | LDAP |
| 443 | TCP | HTTPS |
| 445 | TCP | SMB |
| 3389 | TCP | RDP |

> Services can also operate on non-standard ports.

---

# Port States

Nmap commonly identifies several port states.

---

# Open Port

An open port means that an application is actively accepting connections.

Example:

```text
22/tcp open ssh
```

An open port does not automatically mean that the service is vulnerable.

---

# Closed Port

A closed port means that the target host is reachable but no application is currently listening on that port.

Example:

```text
23/tcp closed
```

---

# Filtered Port

A filtered port indicates that a firewall or filtering mechanism prevents Nmap from determining whether the port is open.

Example:

```text
445/tcp filtered
```

Possible causes include:

- Firewall
- ACL
- Packet filtering
- IDS/IPS
- Network security devices

---

# Unfiltered Port

An unfiltered port means that the port is accessible, but Nmap cannot determine whether it is open or closed using the particular scanning technique.

This state is commonly associated with ACK scanning.

---

# Open|Filtered

`open|filtered` means that Nmap cannot determine whether the port is open or filtered.

This state is commonly encountered during UDP scanning and certain stealth scanning techniques.

---

# Closed|Filtered

`closed|filtered` means that Nmap cannot determine whether the port is closed or filtered.

---

# TCP Scanning

## Definition

TCP scanning uses TCP packets to determine the state of TCP ports.

Different TCP scanning techniques use different TCP flags and connection behaviors.

---

# TCP Three-Way Handshake

A normal TCP connection uses a three-way handshake:

```text
Client
   ↓
SYN
   ↓
Server
   ↓
SYN/ACK
   ↓
Client
   ↓
ACK
   ↓
Connection Established
```

---

# TCP Connect Scan

## Definition

TCP Connect scanning establishes a complete TCP connection with the target.

Nmap option:

```bash
nmap -sT <target>
```

---

# TCP Connect Scan Process

```text
Scanner
   ↓
SYN
   ↓
Target
   ↓
SYN/ACK
   ↓
Scanner
   ↓
ACK
   ↓
Connection Established
```

---

# Advantages of TCP Connect Scan

- Reliable
- Easy to perform
- Useful when raw packet privileges are unavailable
- Provides clear connection results

---

# Disadvantages of TCP Connect Scan

- Completes the TCP connection
- Generates more network activity
- Can appear in application logs
- Can be detected by security monitoring systems

---

# SYN Scan

## Definition

SYN scanning is commonly called a half-open scan because the TCP connection is normally not completed.

Nmap option:

```bash
sudo nmap -sS <target>
```

---

# SYN Scan Process

```text
Scanner
   ↓
SYN
   ↓
Target
   ↓
SYN/ACK
   ↓
Scanner
   ↓
RST
```

---

# SYN Scan Interpretation

```text
SYN/ACK → Open

RST → Closed

No Response / ICMP Error → Filtered or Inconclusive
```

---

# Advantages of SYN Scan

- Fast
- Efficient
- Does not normally complete the TCP connection
- Commonly used for TCP port scanning

---

# ACK Scan

## Definition

An ACK scan sends TCP packets with the ACK flag set.

Nmap option:

```bash
sudo nmap -sA <target>
```

---

# Purpose of ACK Scan

ACK scanning is mainly used to determine firewall filtering.

It helps classify ports as:

- Filtered
- Unfiltered

> **Important:** ACK scanning is not primarily used to determine whether a port is open.

---

# FIN Scan

A FIN scan sends a TCP packet with the FIN flag set.

Nmap option:

```bash
sudo nmap -sF <target>
```

It relies on the target's response to an unexpected FIN packet.

---

# NULL Scan

A NULL scan sends a TCP packet without setting TCP flags.

Nmap option:

```bash
sudo nmap -sN <target>
```

The response can provide information about the target port state.

---

# Xmas Scan

An Xmas scan sends a TCP packet with multiple TCP flags enabled.

Common flags include:

```text
FIN + PSH + URG
```

Nmap option:

```bash
sudo nmap -sX <target>
```

The name comes from the multiple TCP flags being enabled.

---

# TCP Scan Comparison

| Scan Type | Nmap Option | Main Purpose |
|---|---|---|
| TCP Connect | `-sT` | Full TCP connection |
| SYN | `-sS` | Half-open TCP scanning |
| ACK | `-sA` | Firewall filtering |
| FIN | `-sF` | FIN-based scanning |
| NULL | `-sN` | No TCP flags |
| Xmas | `-sX` | Multiple TCP flags |

---

# UDP Scanning

## Definition

UDP scanning identifies accessible UDP services.

Nmap option:

```bash
sudo nmap -sU <target>
```

UDP is connectionless and does not use the TCP three-way handshake.

---

# UDP Scan Interpretation

A simplified interpretation is:

```text
UDP Response
     ↓
Open

ICMP Port Unreachable
     ↓
Closed

No Response
     ↓
Open|Filtered
```

---

# Why UDP Scanning is Difficult

UDP scanning can be slower and more difficult to interpret because:

- UDP is connectionless
- Many UDP services do not respond to unexpected traffic
- Firewalls may silently drop packets
- ICMP responses may be rate-limited
- No response can be ambiguous

---

# Common UDP Services

| Port | Service |
|---:|---|
| 53 | DNS |
| 67/68 | DHCP |
| 69 | TFTP |
| 123 | NTP |
| 161 | SNMP |
| 500 | IKE |
| 514 | Syslog |

---

# Specifying Ports

## Specific Ports

The `-p` option specifies ports to scan.

Example:

```bash
nmap -p 22,80,443 <target>
```

---

# Port Range

Example:

```bash
nmap -p 1-1000 <target>
```

This scans ports 1 through 1000.

---

# All TCP Ports

Example:

```bash
nmap -p- <target>
```

This scans all TCP ports.

---

# Fast Scan

The `-F` option performs a fast scan using a smaller set of commonly used ports.

Example:

```bash
nmap -F <target>
```

---

# CEH Exam Tips

Remember:

- TCP Connect scan = `-sT`
- SYN scan = `-sS`
- SYN scan is commonly called a half-open scan.
- ACK scan = `-sA`
- ACK scanning is mainly used for firewall filtering.
- FIN scan = `-sF`
- NULL scan = `-sN`
- Xmas scan = `-sX`
- UDP scan = `-sU`
- `-p` specifies ports.
- `-p-` scans all TCP ports.
- `-F` performs a fast scan.
- Open means a service is accepting connections.
- Closed means the host is reachable but no service is listening.
- Filtered means filtering prevents the scanner from determining the port state.
- UDP is connectionless.
- UDP scanning is generally slower and more difficult to interpret.

---

# Key Takeaways

- Port scanning identifies accessible TCP and UDP ports.
- Different TCP scanning techniques use different TCP flags and connection behaviors.
- SYN scanning is one of the most commonly used TCP scanning techniques.
- ACK scanning is primarily useful for determining firewall filtering.
- UDP scanning is more difficult because UDP is connectionless and many services do not respond to unexpected packets.
- Understanding port states is essential for interpreting Nmap results.

---

## Part 3 – Service Detection, OS Detection and Nmap Features

---

# Overview

After identifying open ports, the next step is to determine what services are running and which software versions are associated with those services.

Service detection and operating system detection provide additional information that can be used during enumeration and vulnerability assessment.

---

# Service Detection

## Definition

Service detection identifies the application or service running on an open port.

Nmap option:

```bash
nmap -sV <target>
```

Example:

```text
22/tcp   open  ssh
80/tcp   open  http
443/tcp  open  https
```

---

# Version Detection

Version detection attempts to identify the software and version associated with a service.

Possible information includes:

- Service name
- Product name
- Software version
- Protocol information
- Service configuration details

Example:

```text
22/tcp open ssh OpenSSH 8.2
80/tcp open http Apache httpd 2.4.x
```

Version information can help identify outdated or vulnerable software.

---

# Why Service Detection is Important

Service detection helps an ethical hacker:

- Identify technologies
- Understand the attack surface
- Identify outdated software
- Select appropriate enumeration techniques
- Correlate services with known vulnerabilities
- Plan further security testing

---

# Banner Grabbing

## Definition

Banner grabbing is the process of obtaining information provided by a network service when a connection is established.

A banner may reveal:

- Software name
- Version
- Operating system information
- Server information
- Protocol information

Example:

```bash
nc -nv <target> 80
```

Banner information should be validated because it can be hidden, modified, or inaccurate.

---

# Operating System Detection

## Definition

OS detection attempts to determine the operating system running on a target host.

Nmap option:

```bash
sudo nmap -O <target>
```

Nmap analyzes characteristics of network responses and TCP/IP behavior.

---

# Information from OS Detection

OS detection may identify:

- Operating system family
- OS version or generation
- Device type
- Network characteristics

OS detection is not always perfectly accurate and should be validated with other information.

---

# Aggressive Scan

Nmap's `-A` option enables several advanced detection features.

Example:

```bash
sudo nmap -A <target>
```

It can include:

- OS detection
- Version detection
- Script scanning
- Traceroute

Aggressive scanning can generate more traffic and may be more easily detected.

---

# Nmap Scripting Engine

## Definition

The Nmap Scripting Engine (NSE) extends Nmap functionality through scripts.

NSE scripts can assist with:

- Service enumeration
- Network discovery
- Security auditing
- Vulnerability detection
- Authentication testing

Example:

```bash
nmap --script <script-name> <target>
```

---

# Default NSE Scripts

Nmap can run its default script set using:

```bash
nmap -sC <target>
```

Default scripts can provide additional information about discovered services.

---

# NSE Categories

Common NSE categories include:

- `auth`
- `broadcast`
- `brute`
- `default`
- `discovery`
- `dos`
- `exploit`
- `external`
- `fuzzer`
- `intrusive`
- `malware`
- `safe`
- `version`
- `vuln`

Scripts should be selected carefully because some can generate significant traffic or interact aggressively with services.

---

# Vulnerability Scanning

## Definition

Vulnerability scanning is the process of identifying known security weaknesses in systems, applications, services, and configurations.

Typical workflow:

```text
Host Discovery
      ↓
Port Scanning
      ↓
Service Detection
      ↓
Version Detection
      ↓
Vulnerability Scanning
```

---

# Common Vulnerability Scanners

Common tools include:

- Nessus
- Greenbone / OpenVAS
- Qualys
- Nexpose / InsightVM
- Nmap NSE

---

# Common Vulnerability Findings

Vulnerability scanners may identify:

- Missing security patches
- Outdated software
- Weak configurations
- Known vulnerabilities
- Exposed services
- Insecure protocols

---

# Vulnerability Scanning vs Penetration Testing

| Vulnerability Scanning | Penetration Testing |
|---|---|
| Identifies potential weaknesses | Attempts to validate security impact |
| Often automated | Uses automated and manual techniques |
| Broad coverage | More targeted |
| Produces potential findings | Demonstrates exploitability |
| Usually lower interaction | May involve deeper interaction |

A vulnerability scanner may report a potential vulnerability, but additional validation is often required.

---

# Nmap Timing Templates

Nmap provides timing templates:

```text
-T0  Paranoid
-T1  Sneaky
-T2  Polite
-T3  Normal
-T4  Aggressive
-T5  Insane
```

The default timing template is generally:

```text
-T3
```

Faster scanning can increase:

- Network traffic
- Detection
- Packet loss
- Service impact
- Inaccurate results

---

# Nmap Output Formats

## Normal Output

```bash
nmap -oN scan.txt <target>
```

## XML Output

```bash
nmap -oX scan.xml <target>
```

Saving scan results is important for:

- Documentation
- Evidence
- Comparison
- Reporting
- Reproducibility

---

# Useful Nmap Commands

## Host Discovery

```bash
nmap -sn 192.168.1.0/24
```

## Basic Scan

```bash
nmap <target>
```

## Specific Ports

```bash
nmap -p 22,80,443 <target>
```

## Port Range

```bash
nmap -p 1-1000 <target>
```

## All TCP Ports

```bash
nmap -p- <target>
```

## Service Detection

```bash
nmap -sV <target>
```

## OS Detection

```bash
sudo nmap -O <target>
```

## SYN Scan

```bash
sudo nmap -sS <target>
```

## UDP Scan

```bash
sudo nmap -sU <target>
```

## Default NSE Scripts

```bash
nmap -sC <target>
```

## Aggressive Scan

```bash
sudo nmap -A <target>
```

## Fast Scan

```bash
nmap -F <target>
```

## Save Normal Output

```bash
nmap -oN scan.txt <target>
```

---

# Other Network Scanning Tools

## Masscan

Masscan is a high-speed port scanner designed for scanning very large address ranges.

Main characteristics:

- Very high scanning speed
- Large-scale port scanning
- Rapid port discovery

Because of its speed, it must be used carefully in authorized environments.

---

## Unicornscan

Unicornscan is a network information-gathering and port-scanning tool.

It supports asynchronous TCP and UDP scanning and can provide information about network services.

---

## Netcat

Netcat is a network utility capable of establishing TCP and UDP connections.

Example:

```bash
nc -nv <target> 80
```

Common uses include:

- Connectivity testing
- Service interaction
- Banner grabbing
- Network troubleshooting

---

## Hping3

Hping3 is a command-line network testing and packet-crafting tool.

It can be used to:

- Generate custom TCP/IP packets
- Test firewall behavior
- Analyze network responses
- Perform network diagnostics

Example:

```bash
hping3 -S -p 80 <target>
```

---

# Scanning Tool Comparison

| Tool | Primary Use |
|---|---|
| Nmap | Network scanning and security auditing |
| Masscan | High-speed large-scale port scanning |
| Unicornscan | Asynchronous TCP/UDP scanning |
| Netcat | Connectivity and service interaction |
| Hping3 | Packet crafting and network testing |
| Nessus | Vulnerability assessment |
| Greenbone/OpenVAS | Vulnerability assessment |

---

# Network Scanning and Firewalls

Firewalls can affect scanning results by:

- Blocking packets
- Dropping packets
- Filtering specific ports
- Allowing only specific sources
- Rate-limiting traffic

Example:

```text
Scanner
   ↓
Scan Request
   ↓
Firewall
   ↓
Blocked
   ↓
No Response
```

Therefore, a lack of response does not always mean that a service is unavailable.

---

# Network Scanning and IDS/IPS

Intrusion Detection Systems (IDS) and Intrusion Prevention Systems (IPS) can identify scanning activity.

Potential indicators include:

- Sequential port probes
- Large numbers of connection attempts
- ICMP sweeps
- Multiple TCP SYN packets
- Unusual TCP flags
- Large volumes of UDP traffic
- Scanning multiple hosts

An IDS may generate an alert, while an IPS may additionally block or disrupt the traffic.

---

# Scanning Countermeasures

Organizations can reduce unnecessary exposure by:

- Closing unused ports
- Disabling unnecessary services
- Restricting management interfaces
- Implementing firewalls
- Using network segmentation
- Configuring ACLs
- Deploying IDS/IPS
- Monitoring network traffic
- Applying security patches
- Maintaining accurate asset inventories
- Regularly reviewing Internet-facing services

---

# False Positives and False Negatives

## False Positive

A false positive occurs when a scanner reports a potential security issue that does not actually exist.

Example:

```text
Scanner reports vulnerability
        ↓
Manual validation
        ↓
Vulnerability not actually present
```

## False Negative

A false negative occurs when a real security issue exists but the scanner fails to identify it.

Possible causes:

- Firewall filtering
- Authentication requirements
- Network instability
- Incorrect scanner configuration
- Unsupported service
- Rate limiting

Automated scanning should therefore not be considered a complete substitute for manual security assessment.

---

# Scan Result Validation

Professional security testing requires validation of important findings.

Basic workflow:

```text
Scan
 ↓
Identify Finding
 ↓
Review Evidence
 ↓
Validate
 ↓
Correlate
 ↓
Document
```

Validation helps reduce inaccurate findings and improves the quality of the final security report.

---

# Network Scanning vs Enumeration

| Network Scanning | Enumeration |
|---|---|
| Identifies hosts and services | Extracts detailed information from services |
| Focuses on attack surface discovery | Focuses on service-specific information |
| Finds open ports | Identifies users, shares, banners, resources, etc. |
| Usually comes first | Usually follows scanning |

Example:

```text
Nmap
 ↓
445/tcp open
 ↓
SMB detected
 ↓
SMB Enumeration
 ↓
Users / Shares / Domain Information
```

---

# Network Scanning vs Footprinting

| Footprinting | Network Scanning |
|---|---|
| Information gathering | Technical discovery |
| Often passive | Primarily active |
| Uses public sources | Directly probes target systems |
| Domains and organizational information | Hosts, ports and services |
| Lower detection risk | Higher detection risk |

---

# Ethical and Legal Considerations

Network scanning is an active security-testing activity.

Before scanning a system, an ethical hacker should have:

- Proper authorization
- Defined target IP ranges
- Defined testing scope
- Approved scanning techniques
- Testing schedule
- Excluded systems
- Traffic limitations
- Emergency procedures

> **Never scan systems without authorization.**

Unauthorized scanning can violate laws, organizational policies, or terms of service and may cause service disruption.

---

# Practical CEH Scanning Workflow

A basic authorized scanning workflow is:

```text
1. Define Target Scope
        ↓
2. Discover Live Hosts
        ↓
3. Scan Common Ports
        ↓
4. Scan Required Port Ranges
        ↓
5. Identify Services
        ↓
6. Identify Versions
        ↓
7. Identify Operating System
        ↓
8. Perform NSE / Vulnerability Checks
        ↓
9. Validate Findings
        ↓
10. Document Results
```

---

# Important Nmap Options

| Option | Function |
|---|---|
| `-sn` | Host discovery |
| `-sS` | SYN scan |
| `-sT` | TCP Connect scan |
| `-sU` | UDP scan |
| `-sA` | ACK scan |
| `-sF` | FIN scan |
| `-sN` | NULL scan |
| `-sX` | Xmas scan |
| `-sV` | Service/version detection |
| `-O` | OS detection |
| `-A` | Aggressive scan |
| `-sC` | Default NSE scripts |
| `-p` | Specify ports |
| `-p-` | Scan all TCP ports |
| `-F` | Fast scan |
| `-T0` | Paranoid timing |
| `-T3` | Normal timing |
| `-T5` | Insane timing |
| `-oN` | Normal output |
| `-oX` | XML output |

---

# CEH Exam Tips

Remember:

- Network scanning is primarily an active information-gathering technique.
- Host discovery identifies active or reachable systems.
- `ping` commonly uses ICMP Echo Request and Echo Reply.
- ARP discovery is particularly useful on local networks.
- ARP operates at Layer 2.
- Nmap `-sn` performs host discovery without conventional port scanning.
- TCP Connect scan = `-sT`.
- SYN scan = `-sS`.
- SYN scanning is commonly called a half-open scan.
- ACK scan = `-sA`.
- ACK scanning is mainly used to identify firewall filtering.
- FIN scan = `-sF`.
- NULL scan = `-sN`.
- Xmas scan = `-sX`.
- UDP scan = `-sU`.
- `-sV` performs service/version detection.
- `-O` performs OS detection.
- `-A` enables several advanced detection features.
- `-sC` runs default NSE scripts.
- `-p` specifies ports.
- `-p-` scans all TCP ports.
- `-F` performs a fast scan.
- Open means a service is accepting connections.
- Closed means the host is reachable but no service is listening.
- Filtered means filtering prevents the scanner from determining the port state.
- UDP is connectionless.
- UDP scanning is generally slower and more difficult to interpret.
- Masscan is designed for high-speed large-scale scanning.
- Netcat can be used for connectivity testing and banner grabbing.
- Hping3 is useful for packet crafting and network testing.
- Vulnerability scanning identifies potential security weaknesses.
- Scanning results should be validated before reporting.
- Firewalls, IDS/IPS, ACLs, and rate limiting can affect scanning results.
- Network scanning should always be performed within an authorized scope.

---

# Key Takeaways

- Network scanning is a fundamental stage of ethical hacking that provides technical information about a target environment.
- Host discovery identifies systems that are active or reachable.
- Port scanning identifies accessible TCP and UDP ports.
- Port states such as open, closed, filtered, and unfiltered provide information about how a target responds to scanning.
- TCP scanning techniques use different connection behaviors and TCP flags.
- SYN scanning is a common half-open TCP scanning technique.
- ACK scanning is primarily useful for analyzing firewall filtering.
- UDP scanning is more difficult because UDP is connectionless and many services do not respond to unexpected packets.
- Service and version detection identifies applications running on discovered ports.
- OS detection attempts to identify the operating system and device type.
- Nmap NSE extends Nmap with additional discovery, enumeration, auditing, and vulnerability-testing capabilities.
- Vulnerability scanners can identify potential security weaknesses, but important findings should be validated.
- Firewalls, IDS/IPS, ACLs, rate limiting, and network configuration can affect scanning results.
- Nmap, Masscan, Unicornscan, Netcat, Hping3, Nessus, and Greenbone/OpenVAS serve different purposes within network security testing.
- Network scanning should always be performed with proper authorization and within the defined assessment scope.
