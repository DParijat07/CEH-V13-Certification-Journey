# Module 12 – Evading IDS, Firewalls, and Honeypots

## Overview

Modern organizations deploy multiple layers of security controls such as firewalls, Intrusion Detection Systems (IDS), Intrusion Prevention Systems (IPS), Web Application Firewalls (WAF), and honeypots to detect and prevent cyber attacks. Security professionals must understand how these technologies work, how attackers attempt to bypass them, and—most importantly—how defenders can detect and respond to such attempts.

This module focuses on the architecture, operation, and defensive considerations of these technologies.

---

# Learning Objectives

After completing this module, you should be able to:

- Understand different types of firewalls.
- Explain how IDS and IPS detect malicious activity.
- Differentiate IDS, IPS, Firewall, and WAF.
- Understand packet filtering and stateful inspection.
- Learn common network traffic obfuscation concepts.
- Understand honeypots and honeynets.
- Apply defensive best practices.
- Recognize MITRE ATT&CK techniques related to defense evasion.

---

# What is a Firewall?

A **Firewall** is a network security device or software that monitors, filters, and controls incoming and outgoing network traffic based on predefined security rules.

It acts as a barrier between trusted and untrusted networks.

### Primary Functions

- Monitor network traffic
- Allow legitimate communication
- Block unauthorized access
- Enforce security policies
- Log network events

---

# Types of Firewalls

## 1. Packet Filtering Firewall

The simplest type of firewall.

It filters packets based on:

- Source IP Address
- Destination IP Address
- Source Port
- Destination Port
- Protocol

### Advantages

- Fast
- Low resource usage
- Easy to configure

### Disadvantages

- No session awareness
- Cannot inspect application data

---

## 2. Stateful Inspection Firewall

Tracks active network connections.

Instead of inspecting individual packets, it examines the **state** of a communication session.

### Advantages

- More secure than packet filtering
- Detects unauthorized packets
- Better connection tracking

### Disadvantages

- Higher resource consumption

---

## 3. Circuit-Level Gateway

Operates at the Session Layer (Layer 5).

It verifies TCP handshakes and session establishment without inspecting packet contents.

### Advantages

- Hides internal network structure
- Low overhead

### Disadvantages

- Does not inspect application payloads

---

## 4. Application Proxy Firewall

Also called an **Application-Level Gateway**.

Acts as an intermediary between clients and servers.

### Advantages

- Deep packet inspection
- Application-layer filtering
- User authentication support

### Disadvantages

- Slower than packet filtering
- Higher resource usage

---

## 5. Next-Generation Firewall (NGFW)

An advanced firewall combining traditional firewall capabilities with modern security features.

### Features

- Deep Packet Inspection (DPI)
- Application Awareness
- User Identity Awareness
- Intrusion Prevention (IPS)
- Malware Detection
- SSL/TLS Inspection
- Threat Intelligence Integration

Examples:

- Palo Alto Networks
- Fortinet FortiGate
- Cisco Firepower
- Check Point
- Sophos XGS

---

# Firewall Deployment Types

## Network Firewall

Protects an entire network.

Example:

Internet → Firewall → Internal Network

---

## Host-Based Firewall

Installed on individual systems.

Examples:

- Windows Defender Firewall
- Linux iptables
- nftables
- UFW

---

## Cloud Firewall

Protects cloud-hosted workloads.

Examples:

- AWS Security Groups
- Azure Firewall
- Google Cloud Firewall

---

# Firewall Rule Components

Typical firewall rules are based on:

- Source Address
- Destination Address
- Source Port
- Destination Port
- Protocol
- Direction
- Action (Allow/Deny)

---

# Common Firewall Actions

- Allow
- Deny
- Reject
- Drop
- Log

---

# Firewall Logging

Firewalls generate logs that help security teams monitor network activity.

Common log information includes:

- Source IP
- Destination IP
- Port Numbers
- Protocol
- Timestamp
- Action Taken
- Rule Triggered

These logs are often forwarded to a SIEM for centralized monitoring.

---

# Best Practices

- Follow the Principle of Least Privilege.
- Deny all traffic by default unless explicitly allowed.
- Review firewall rules regularly.
- Remove unused rules.
- Enable logging and monitoring.
- Keep firewall firmware updated.
- Segment internal networks.
- Use Multi-Factor Authentication (MFA) for firewall administration.

---

# Key Takeaways

- Firewalls are the first line of network defense.
- Different firewall types provide different levels of inspection.
- NGFWs combine traditional filtering with advanced threat detection.
- Proper firewall configuration and continuous monitoring are essential for enterprise security.


---

# Intrusion Detection System (IDS)

## What is an IDS?

An **Intrusion Detection System (IDS)** is a security solution that continuously monitors network traffic or host activities to identify suspicious behavior, security policy violations, or known attack patterns.

Unlike a firewall, an IDS **does not block** malicious traffic. Instead, it detects potential threats and generates alerts so that security teams can investigate and respond.

---

# Objectives of an IDS

- Monitor network traffic
- Detect malicious activities
- Identify known attack signatures
- Detect abnormal behavior
- Generate security alerts
- Assist incident response
- Support forensic investigations

---

# Types of IDS

## 1. Network-based IDS (NIDS)

A Network-based IDS monitors traffic flowing across a network segment.

### Characteristics

- Monitors multiple devices simultaneously
- Detects network attacks
- Usually deployed at strategic network locations
- Passive monitoring (does not modify traffic)

### Examples

- Snort
- Suricata
- Zeek

---

## 2. Host-based IDS (HIDS)

A Host-based IDS is installed on an individual system.

### Characteristics

- Monitors system logs
- Monitors file integrity
- Detects unauthorized changes
- Detects suspicious local activity

### Examples

- OSSEC
- Wazuh
- Tripwire

---

# Detection Methods

## 1. Signature-Based Detection

The IDS compares observed traffic against a database of known attack signatures.

### Advantages

- Fast detection
- Low false positives
- Effective against known attacks

### Disadvantages

- Cannot detect new (zero-day) attacks
- Requires regular signature updates

Example

Known SQL Injection pattern detected.

---

## 2. Anomaly-Based Detection

The IDS builds a baseline of normal behavior and alerts when significant deviations occur.

### Advantages

- Can detect unknown attacks
- Identifies unusual behavior

### Disadvantages

- Higher false positives
- Requires training period

Example

A user suddenly transfers a large amount of data outside normal working hours.

---

## 3. Hybrid Detection

Combines Signature-Based and Anomaly-Based detection.

### Advantages

- Better detection accuracy
- Detects both known and unknown threats

### Disadvantages

- More computational resources required
- More complex to configure

---

# IDS Deployment Locations

Common deployment points include:

- Behind the firewall
- Network perimeter
- Data center
- Internal network segments
- DMZ (Demilitarized Zone)
- Cloud environments

Example Architecture

```
Internet
    │
Firewall
    │
Network IDS
    │
Internal Network
```

---

# Common IDS Alerts

An IDS may generate alerts for:

- Port Scanning
- Brute Force Attempts
- Malware Communication
- SQL Injection
- Cross-Site Scripting (XSS)
- DNS Tunneling Indicators
- Unusual Network Traffic
- Unauthorized File Changes
- Suspicious Login Activity

---

# Advantages of IDS

- Continuous monitoring
- Early threat detection
- Improved visibility
- Supports forensic investigations
- Helps meet compliance requirements
- Integrates with SIEM platforms

---

# Limitations of IDS

- Cannot automatically stop attacks
- May generate false positives
- May generate false negatives
- Requires continuous tuning
- Signature databases must be updated regularly

---

# Common IDS Tools

| Tool | Type |
|------|------|
| Snort | NIDS |
| Suricata | NIDS |
| Zeek | Network Security Monitor |
| Wazuh | HIDS |
| OSSEC | HIDS |
| Tripwire | File Integrity Monitoring |

---

# IDS vs Firewall

| Firewall | IDS |
|-----------|-----|
| Filters network traffic | Monitors network traffic |
| Allows or blocks traffic | Generates alerts |
| Preventive control | Detective control |
| Enforces security policy | Detects suspicious activity |
| Usually inline | Usually passive |

---

# IDS and SIEM Integration

IDS alerts are often forwarded to a Security Information and Event Management (SIEM) platform.

Examples:

- Splunk
- Microsoft Sentinel
- IBM QRadar
- Elastic Security

Benefits include:

- Centralized log management
- Alert correlation
- Threat hunting
- Incident investigation
- Automated response

---

# Best Practices

- Keep IDS signatures updated.
- Deploy sensors at critical network locations.
- Tune detection rules to reduce false positives.
- Integrate IDS with SIEM.
- Regularly review alerts.
- Monitor both network and host activities.
- Combine IDS with firewalls, EDR, and endpoint security.

---

# Key Takeaways

- IDS is a **detective security control**.
- It identifies suspicious activity but does not block attacks.
- Network IDS monitors network traffic, while Host IDS monitors individual systems.
- Signature-based detection is effective for known threats, whereas anomaly-based detection can identify unknown attacks.
- IDS works best when integrated with SIEM, firewalls, and endpoint security solutions.

---

# Intrusion Prevention System (IPS)

## What is an IPS?

An **Intrusion Prevention System (IPS)** is a security solution that continuously monitors network traffic, detects malicious activities, and automatically blocks or prevents attacks in real time.

Unlike an Intrusion Detection System (IDS), an IPS operates **inline** with network traffic, allowing it to stop threats before they reach their target.

---

# Objectives of an IPS

- Monitor network traffic
- Detect malicious activities
- Prevent attacks automatically
- Enforce security policies
- Reduce the attack surface
- Protect network resources
- Support defense-in-depth

---

# How IPS Works

The IPS inspects every packet passing through the network.

Basic workflow:

```
Incoming Traffic
        │
        ▼
Packet Inspection
        │
        ▼
Threat Detection
        │
        ▼
Decision
        │
 ┌──────┴──────┐
 │             │
 ▼             ▼
Allow       Block
Traffic     Traffic
```

---

# Types of IPS

## 1. Network-based IPS (NIPS)

Monitors and protects the entire network.

### Characteristics

- Installed inline
- Monitors network traffic
- Blocks malicious packets
- Protects multiple hosts

Examples

- Cisco Firepower
- Snort IPS Mode
- Suricata IPS Mode

---

## 2. Host-based IPS (HIPS)

Installed on individual endpoints.

### Characteristics

- Protects a single host
- Monitors local processes
- Prevents unauthorized changes
- Detects suspicious behavior

Examples

- Microsoft Defender
- OSSEC (with active response)
- Wazuh Active Response

---

## 3. Wireless IPS (WIPS)

Designed to protect wireless networks.

Functions

- Detect rogue access points
- Detect unauthorized wireless devices
- Monitor Wi-Fi attacks
- Protect wireless infrastructure

---

# Detection Methods

## Signature-Based Detection

Compares traffic against a database of known attack signatures.

### Advantages

- Fast
- Accurate for known attacks
- Low false positives

### Limitations

- Cannot detect unknown attacks
- Requires frequent signature updates

---

## Anomaly-Based Detection

Builds a baseline of normal behavior and identifies unusual activity.

### Advantages

- Detects unknown attacks
- Detects insider threats

### Limitations

- Higher false positives
- Requires tuning

---

## Policy-Based Detection

Traffic is evaluated against predefined organizational security policies.

Example

- Block Telnet (Port 23)
- Block unauthorized protocols
- Restrict administrative services

---

# Common IPS Actions

An IPS can automatically:

- Drop malicious packets
- Reset network connections
- Block IP addresses
- Generate alerts
- Log events
- Rate-limit suspicious traffic

---

# Advantages of IPS

- Real-time protection
- Automatic attack prevention
- Reduced manual intervention
- Protects critical assets
- Works with SIEM and SOC platforms
- Improves overall network security

---

# Limitations of IPS

- Inline deployment may introduce latency
- Incorrect rules can block legitimate traffic
- Requires continuous updates and tuning
- High-speed networks require more powerful hardware

---

# IDS vs IPS

| Feature | IDS | IPS |
|----------|-----|-----|
| Deployment | Passive | Inline |
| Blocks attacks | No | Yes |
| Generates alerts | Yes | Yes |
| Monitors traffic | Yes | Yes |
| Prevents attacks | No | Yes |
| Risk of blocking legitimate traffic | No | Possible |

---

# Firewall vs IDS vs IPS

| Feature | Firewall | IDS | IPS |
|----------|----------|-----|-----|
| Primary Function | Traffic Filtering | Threat Detection | Threat Prevention |
| Blocks Traffic | Yes | No | Yes |
| Detects Attacks | Limited | Yes | Yes |
| Generates Alerts | Limited | Yes | Yes |
| Inline Deployment | Yes | Usually No | Yes |
| Preventive Control | Yes | No | Yes |
| Detective Control | Limited | Yes | Yes |

---

# Common IPS Products

- Cisco Firepower
- Palo Alto Threat Prevention
- Fortinet FortiGate IPS
- Check Point IPS
- Snort (IPS Mode)
- Suricata (IPS Mode)

---

# IPS Integration with SOC

IPS alerts are commonly forwarded to SIEM platforms for centralized monitoring and incident response.

Examples

- Splunk
- Microsoft Sentinel
- IBM QRadar
- Elastic Security

SOC analysts use IPS data to:

- Investigate attacks
- Correlate events
- Prioritize incidents
- Identify attack trends
- Improve detection rules

---

# Best Practices

- Keep IPS signatures updated.
- Deploy IPS at critical network boundaries.
- Regularly review blocked events.
- Tune detection policies to reduce false positives.
- Integrate IPS with SIEM and EDR solutions.
- Test security rules before production deployment.
- Follow the principle of least privilege.

---

# CEH Exam Tips

Remember:

- **Firewall** filters traffic based on rules.
- **IDS** detects suspicious activity and generates alerts.
- **IPS** detects and automatically blocks malicious activity.
- IPS is deployed **inline**, while IDS is typically **passive**.
- Signature-based detection identifies known attacks.
- Anomaly-based detection identifies deviations from normal behavior.

---

# Key Takeaways

- An IPS combines monitoring with automatic prevention.
- It is a preventive security control that operates inline with network traffic.
- IPS solutions complement firewalls and IDS by actively blocking malicious activity.
- A layered defense using Firewalls, IDS, IPS, EDR, and SIEM provides stronger protection against modern cyber threats.

---

# Defense Evasion Concepts

## Overview

Modern security solutions such as Firewalls, Intrusion Detection Systems (IDS), Intrusion Prevention Systems (IPS), Endpoint Detection and Response (EDR), and Security Information and Event Management (SIEM) platforms continuously monitor network traffic and system activity for malicious behavior.

Attackers may attempt to disguise or modify their activity to avoid detection. Understanding these concepts helps defenders recognize suspicious behavior, improve detection rules, and strengthen network security.

---

# What is Defense Evasion?

**Defense Evasion** refers to techniques used to reduce the likelihood that malicious activity will be detected by security controls.

From a defender's perspective, understanding these techniques is important for:

- Improving monitoring
- Creating better detection rules
- Investigating incidents
- Strengthening security controls

---

# Common Defense Evasion Concepts

## Traffic Obfuscation

Traffic obfuscation involves altering the appearance or characteristics of network communications so they are less recognizable.

Examples include:

- Modified communication patterns
- Encrypted communications
- Encapsulated traffic
- Unusual protocols

SOC analysts monitor for these behaviors using network telemetry and behavioral analytics.

---

## Encrypted Network Traffic

Encryption protects confidentiality and integrity during data transmission.

Benefits:

- Prevents unauthorized interception
- Protects sensitive information
- Supports secure communications

Security teams may use TLS inspection, endpoint telemetry, and log correlation to investigate encrypted traffic when appropriate and authorized.

---

## Tunneling

Tunneling is the process of encapsulating one communication protocol within another.

Legitimate Uses:

- Virtual Private Networks (VPNs)
- Remote administration
- Secure enterprise connectivity

Because tunneling can also conceal network activity, organizations monitor for unusual or unauthorized tunneling behavior.

---

## Proxy Servers

A proxy server acts as an intermediary between a client and a destination server.

Legitimate Uses:

- Web filtering
- Content caching
- Privacy
- Enterprise internet access

Security teams monitor proxy logs for abnormal usage patterns or unauthorized services.

---

## Virtual Private Networks (VPN)

A VPN creates an encrypted connection between a device and a remote network.

Legitimate Uses:

- Secure remote work
- Protect data over public networks
- Secure branch connectivity

Organizations typically authenticate VPN users and log VPN activity to detect anomalies.

---

## Living off the Land (LotL)

Living off the Land refers to the use of legitimate operating system tools for administrative tasks.

Examples of legitimate tools include:

- PowerShell
- Windows Management Instrumentation (WMI)
- Bash
- Scheduled Tasks

Because these tools are commonly used by administrators, defenders rely on behavioral monitoring, command auditing, and endpoint telemetry to distinguish normal administration from suspicious activity.

---

# Detection Techniques

Security teams use multiple methods to identify potential defense evasion.

## Signature-Based Detection

Compares observed activity against known attack patterns.

Advantages:

- Fast
- Reliable for known threats

Limitations:

- Less effective against new or modified threats

---

## Anomaly-Based Detection

Compares current activity against a baseline of normal behavior.

Examples:

- Unusual login times
- Unexpected network destinations
- Sudden increase in outbound traffic
- Abnormal protocol usage

Advantages:

- Can identify previously unknown threats

Limitations:

- May produce false positives

---

## Behavioral Analysis

Behavioral analysis focuses on user, device, and application behavior.

Examples:

- Impossible travel
- Unusual authentication patterns
- Abnormal process execution
- Unexpected privilege changes
- Suspicious data transfers

---

# Security Monitoring

Organizations monitor multiple sources to identify suspicious behavior.

Common data sources include:

- Firewall Logs
- IDS Alerts
- IPS Events
- Authentication Logs
- VPN Logs
- DNS Logs
- Proxy Logs
- Endpoint Detection and Response (EDR)
- SIEM Platforms

---

# Defensive Best Practices

To reduce the risk of defense evasion:

- Keep security solutions updated.
- Enable centralized logging.
- Use Multi-Factor Authentication (MFA).
- Monitor privileged accounts.
- Review firewall and IDS/IPS alerts regularly.
- Implement network segmentation.
- Monitor endpoint activity.
- Apply the Principle of Least Privilege.
- Conduct regular security assessments.
- Provide user security awareness training.

---

# MITRE ATT&CK Mapping

This topic is primarily related to the **Defense Evasion** tactic.

Examples of associated techniques include:

- Obfuscated or Encrypted Information
- Proxy
- Indicator Removal on Host
- Masquerading
- Impair Defenses

Understanding these techniques helps defenders improve detection and response capabilities.

---

# CEH Exam Tips

Remember:

- Defense evasion techniques attempt to reduce the visibility of malicious activity.
- Multiple security controls should work together to improve detection.
- Behavioral monitoring is increasingly important because not all attacks match known signatures.
- Layered security significantly improves an organization's ability to detect and respond to threats.

---

# Key Takeaways

- Defense evasion focuses on reducing the visibility of malicious activity.
- Organizations rely on layered security, centralized logging, and behavioral analytics to detect suspicious behavior.
- Understanding defense evasion concepts enables security professionals to improve detection rules, strengthen monitoring, and enhance incident response.

---

# Honeypots and Honeynets

## Overview

A **Honeypot** is a decoy system intentionally designed to attract attackers. It mimics legitimate services, applications, or systems to observe malicious activities without exposing critical production assets.

Honeypots help organizations study attacker behavior, collect threat intelligence, validate detection rules, and improve incident response capabilities.

A **Honeynet** is a network containing multiple interconnected honeypots that simulate a realistic enterprise environment.

---

# Objectives of Honeypots

- Detect unauthorized activities
- Collect threat intelligence
- Study attacker techniques
- Identify Indicators of Compromise (IOCs)
- Improve IDS/IPS detection rules
- Support digital forensics
- Train security teams
- Research emerging threats

---

# How Honeypots Work

Basic Workflow

```
Internet
     │
     ▼
 Attacker
     │
     ▼
 Honeypot
     │
     ▼
 Logs & Monitoring
     │
     ▼
 SOC / Security Team
```

Every interaction with the honeypot is monitored and logged for analysis.

---

# Types of Honeypots

## 1. Production Honeypot

Deployed within an organization's production environment.

### Purpose

- Detect real-world attacks
- Generate security alerts
- Support incident response

### Advantages

- Easy to deploy
- Low maintenance
- Useful for enterprise monitoring

### Limitations

- Limited research capabilities

---

## 2. Research Honeypot

Used by security researchers, universities, and threat intelligence teams.

### Purpose

- Study attacker behavior
- Discover new attack techniques
- Analyze malware
- Collect Indicators of Compromise (IOCs)

### Advantages

- Rich threat intelligence
- Supports malware research

### Limitations

- More complex
- Requires skilled analysts

---

# Interaction Levels

## Low-Interaction Honeypot

Simulates only a few services.

### Characteristics

- Limited attacker interaction
- Safer
- Easier to manage

Examples

- Honeyd
- Glastopf

---

## Medium-Interaction Honeypot

Provides more realistic responses than low-interaction systems while still limiting attacker access.

### Characteristics

- Moderate realism
- Better intelligence collection
- Lower risk than full systems

---

## High-Interaction Honeypot

A fully functional operating system intentionally exposed for research.

### Characteristics

- Real operating system
- Extensive attacker interaction
- Excellent intelligence gathering

### Risks

- Higher operational risk
- Requires isolation and continuous monitoring

---

# Honeynet

A Honeynet consists of multiple honeypots connected together to simulate an enterprise network.

Example

```
Internet
      │
Firewall
      │
-------------------------
│          │           │
Web HP   DB HP    Windows HP
│          │           │
-------------------------
      │
 Logging Server
      │
     SIEM
```

Benefits

- Simulates real enterprise environments
- Captures complex attack behavior
- Supports threat hunting
- Provides richer forensic evidence

---

# Honeytokens

Honeytokens are fake digital assets placed within an environment to detect unauthorized access.

Examples

- Fake credentials
- Fake API keys
- Fake documents
- Fake database records
- Fake cloud storage links

Accessing a honeytoken should trigger an immediate security alert.

---

# Advantages of Honeypots

- Early attack detection
- Low false positives
- Threat intelligence collection
- Malware analysis
- Attacker behavior research
- Incident response support
- Security awareness and training

---

# Limitations of Honeypots

- Do not protect production systems directly
- May not attract every attacker
- Require monitoring and maintenance
- High-interaction deployments increase operational complexity

---

# Common Honeypot Solutions

| Tool | Purpose |
|------|---------|
| Honeyd | Network Honeypot |
| Cowrie | SSH/Telnet Honeypot |
| Dionaea | Malware Collection |
| Glastopf | Web Application Honeypot |
| T-Pot | Multi-Honeypot Platform |
| OpenCanary | Network Detection Honeypot |

---

# Honeypots in SOC Operations

SOC analysts use honeypots to:

- Detect unauthorized access
- Monitor attacker behavior
- Collect Indicators of Compromise (IOCs)
- Improve IDS/IPS signatures
- Validate detection rules
- Support digital forensics
- Enrich threat intelligence

---

# Best Practices

- Deploy honeypots in isolated environments.
- Monitor all interactions continuously.
- Forward logs to a SIEM.
- Restrict outbound connectivity.
- Regularly review collected data.
- Never expose sensitive production information.
- Clearly document deployment and objectives.

---

# CEH Exam Tips

Remember:

- Honeypots are decoy systems.
- Honeynets are networks of honeypots.
- Production honeypots focus on detection.
- Research honeypots focus on intelligence gathering.
- Low-interaction honeypots are safer and easier to maintain.
- High-interaction honeypots provide more intelligence but require stronger isolation and monitoring.
- Honeytokens are fake digital assets used to detect unauthorized access.

---

# Key Takeaways

- Honeypots are valuable tools for detection, research, and incident response.
- Honeynets simulate realistic enterprise environments for advanced analysis.
- Honeytokens help identify unauthorized access with minimal overhead.
- Integrating honeypot telemetry with SIEM and SOC workflows enhances visibility and strengthens an organization's overall security posture.

---

# Security Best Practices

Organizations should implement a layered security strategy to defend against modern cyber threats. No single security control is sufficient to protect an enterprise network.

## Firewall Best Practices

- Follow the Principle of Least Privilege.
- Allow only required ports and services.
- Regularly review and remove unused firewall rules.
- Keep firewall firmware and software updated.
- Enable detailed logging and monitoring.
- Implement network segmentation.

---

## IDS/IPS Best Practices

- Keep detection signatures up to date.
- Deploy sensors at critical network locations.
- Tune detection rules to minimize false positives.
- Monitor alerts continuously.
- Integrate IDS/IPS with SIEM platforms.
- Periodically test detection capabilities.

---

## Honeypot Best Practices

- Deploy honeypots in isolated environments.
- Continuously monitor all interactions.
- Forward logs to a centralized SIEM.
- Restrict outbound network communication.
- Never store sensitive production data on honeypots.
- Regularly analyze collected threat intelligence.

---

## General Security Best Practices

- Use Multi-Factor Authentication (MFA).
- Apply the Principle of Least Privilege.
- Keep operating systems and applications updated.
- Disable unnecessary services and ports.
- Encrypt sensitive data.
- Maintain regular backups.
- Conduct vulnerability assessments and penetration testing.
- Provide regular security awareness training.
- Monitor logs and network traffic continuously.

---

# MITRE ATT&CK Mapping

This module is primarily associated with the following MITRE ATT&CK tactics and techniques:

| ATT&CK Tactic | Examples |
|--------------|----------|
| TA0005 – Defense Evasion | Obfuscated/Encrypted Information, Masquerading, Indicator Removal |
| TA0011 – Command and Control | Proxy, Encrypted Channel |
| TA0007 – Discovery | Network Service Discovery |
| TA0006 – Credential Access | Credential Collection (Detection Perspective) |
| TA0001 – Initial Access | Monitoring Attack Attempts |
| TA0009 – Collection | Data Collection Monitoring |

---

# Detection Opportunities

Security teams can identify suspicious activity using:

- Firewall logs
- IDS alerts
- IPS events
- Windows Event Logs
- Linux system logs
- DNS logs
- Proxy logs
- VPN logs
- Authentication logs
- Endpoint Detection and Response (EDR)
- Security Information and Event Management (SIEM)

---

# Common Security Tools

## Network Security

- Wireshark
- tcpdump
- Nmap

## Intrusion Detection

- Snort
- Suricata
- Zeek

## Firewalls

- Windows Defender Firewall
- pfSense
- Fortinet FortiGate
- Palo Alto Networks
- Cisco Firepower

## Host Security

- Wazuh
- OSSEC
- Microsoft Defender

## SIEM Platforms

- Splunk
- Microsoft Sentinel
- IBM QRadar
- Elastic Security

---

# Key Terminology

| Term | Definition |
|------|------------|
| Firewall | Filters network traffic based on security rules. |
| IDS | Detects suspicious activity and generates alerts. |
| IPS | Detects and automatically blocks malicious activity. |
| Honeypot | A decoy system designed to attract attackers. |
| Honeynet | A network consisting of multiple honeypots. |
| Honeytoken | A fake digital asset used to detect unauthorized access. |
| SIEM | Centralized platform for log collection, correlation, and alerting. |
| IOC | Indicator of Compromise used to identify malicious activity. |
| EDR | Endpoint Detection and Response solution for monitoring endpoints. |

---

# CEH Exam Revision

Remember the following key points:

- Firewalls filter and control network traffic.
- IDS detects attacks but does not block them.
- IPS detects and blocks malicious traffic in real time.
- NGFWs provide advanced inspection and application awareness.
- Signature-based detection identifies known threats.
- Anomaly-based detection identifies deviations from normal behavior.
- Honeypots are decoy systems used for detection and research.
- Honeynets consist of multiple interconnected honeypots.
- Honeytokens are fake digital assets that trigger alerts when accessed.
- Defense-in-depth combines multiple security controls for stronger protection.
- Layered security is more effective than relying on a single defensive mechanism.

---

# Interview Tips

Be prepared to explain:

- Differences between Firewall, IDS, IPS, and WAF.
- Signature-based vs Anomaly-based detection.
- Network IDS vs Host IDS.
- Production vs Research Honeypots.
- Low-, Medium-, and High-Interaction Honeypots.
- Role of SIEM in security monitoring.
- Importance of centralized logging.
- Defense-in-depth strategy.
- MITRE ATT&CK framework.
- Common SOC detection workflows.

---

# Module Summary

In this module, we explored the technologies organizations use to monitor, detect, and respond to cyber threats.

Key topics included:

- Firewall architecture and deployment
- Intrusion Detection Systems (IDS)
- Intrusion Prevention Systems (IPS)
- Defense evasion concepts
- Honeypots and Honeynets
- Security monitoring
- Threat detection
- Incident response support
- MITRE ATT&CK mapping
- Security best practices

These concepts form an important foundation for careers in:

- SOC Analyst
- Security Analyst
- Vulnerability Assessment
- Penetration Testing
- Incident Response
- Blue Team Operations
- Threat Detection
- Cyber Defense

---

# Final Takeaways

- Security is built on multiple layers of defense.
- Continuous monitoring and centralized logging improve threat detection.
- Understanding attacker behavior helps defenders strengthen security controls.
- IDS, IPS, Firewalls, and Honeypots work together to protect enterprise environments.
- Practical experience with labs, SIEM platforms, and network analysis tools is essential for developing real-world cybersecurity skills.
