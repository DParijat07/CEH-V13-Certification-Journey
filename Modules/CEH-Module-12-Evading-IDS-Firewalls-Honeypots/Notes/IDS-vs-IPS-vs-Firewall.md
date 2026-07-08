# IDS vs IPS vs Firewall

## Overview

Firewalls, Intrusion Detection Systems (IDS), and Intrusion Prevention Systems (IPS) are fundamental components of modern network security. Although they work together, each serves a different purpose within a layered defense strategy.

---

# Quick Comparison

| Feature | Firewall | IDS | IPS |
|----------|----------|-----|-----|
| Full Form | Firewall | Intrusion Detection System | Intrusion Prevention System |
| Primary Function | Filters network traffic | Detects attacks | Detects and blocks attacks |
| Security Control | Preventive | Detective | Preventive + Detective |
| Deployment | Inline | Passive | Inline |
| Blocks Traffic | ✅ Yes | ❌ No | ✅ Yes |
| Generates Alerts | Limited | ✅ Yes | ✅ Yes |
| Monitors Traffic | ✅ Yes | ✅ Yes | ✅ Yes |
| Stops Attacks | ✅ Based on Rules | ❌ No | ✅ Automatically |
| Performance Impact | Low | Very Low | Moderate |
| False Positives | Low | Moderate | Higher (if poorly configured) |

---

# Firewall

## Definition

A **Firewall** is a security device or software that filters incoming and outgoing network traffic based on predefined security rules.

### Primary Purpose

- Control network access
- Block unauthorized connections
- Allow legitimate communication

### Common Types

- Packet Filtering Firewall
- Stateful Inspection Firewall
- Proxy Firewall
- Next-Generation Firewall (NGFW)

### Advantages

- First line of defense
- Controls network access
- Reduces attack surface
- Easy to manage

### Limitations

- Cannot detect every attack
- Limited visibility into encrypted traffic
- Does not analyze endpoint behavior

---

# Intrusion Detection System (IDS)

## Definition

An **Intrusion Detection System (IDS)** monitors network or host activity for suspicious behavior and generates alerts when malicious activity is detected.

### Primary Purpose

- Detect attacks
- Monitor network traffic
- Alert security teams

### Types

### Network IDS (NIDS)

Monitors network traffic.

Examples:

- Snort
- Suricata
- Zeek

### Host IDS (HIDS)

Monitors an individual system.

Examples:

- Wazuh
- OSSEC
- Tripwire

### Advantages

- Excellent visibility
- Supports incident response
- Useful for threat hunting

### Limitations

- Cannot stop attacks
- Requires monitoring
- May generate false positives

---

# Intrusion Prevention System (IPS)

## Definition

An **Intrusion Prevention System (IPS)** monitors traffic and automatically blocks malicious activity before it reaches its destination.

### Primary Purpose

- Detect attacks
- Prevent attacks
- Enforce security policies

### Types

- Network IPS (NIPS)
- Host IPS (HIPS)
- Wireless IPS (WIPS)

### Advantages

- Real-time protection
- Automatic response
- Prevents known attacks

### Limitations

- Requires tuning
- May block legitimate traffic
- Higher resource usage

---

# Detection Methods

| Detection Method | Firewall | IDS | IPS |
|-----------------|----------|-----|-----|
| Rule Based | ✅ | ❌ | ✅ |
| Signature Based | Limited | ✅ | ✅ |
| Anomaly Based | ❌ | ✅ | ✅ |
| Behavioral Analysis | ❌ | Limited | Limited |

---

# Deployment Architecture

```
Internet
    │
Firewall
    │
IPS
    │
IDS
    │
Internal Network
```

### Explanation

- Firewall filters unwanted traffic.
- IPS inspects and blocks malicious traffic in real time.
- IDS monitors network activity and generates alerts.
- SIEM collects logs from all security devices for centralized monitoring.

---

# Integration with SIEM

Security devices commonly send logs to SIEM platforms such as:

- Splunk
- Microsoft Sentinel
- IBM QRadar
- Elastic Security

Benefits include:

- Centralized logging
- Event correlation
- Threat detection
- Incident response
- Compliance reporting

---

# When to Use Each Technology

## Firewall

Use when:

- Controlling network access
- Blocking unauthorized traffic
- Enforcing security policies

---

## IDS

Use when:

- Monitoring networks
- Detecting attacks
- Supporting forensic investigations
- Threat hunting

---

## IPS

Use when:

- Preventing attacks automatically
- Protecting critical infrastructure
- Stopping known threats in real time

---

# Best Practice

Organizations should use **all three technologies together** as part of a **Defense-in-Depth** strategy.

Example layered architecture:

```
Internet
    │
Firewall
    │
IPS
    │
IDS
    │
EDR
    │
SIEM
    │
SOC Team
```

Each layer provides additional visibility and protection.

---

# CEH Exam Tips

Remember:

- **Firewall → Filters traffic**
- **IDS → Detects attacks**
- **IPS → Detects and blocks attacks**

IDS = Passive Monitoring

IPS = Active Protection

Firewall = Access Control

---

# Interview Questions

### What is the difference between IDS and IPS?

**Answer:**

An IDS monitors traffic and generates alerts, whereas an IPS monitors traffic and automatically blocks malicious activity.

---

### Why is an IDS called a passive device?

Because it only observes network traffic and alerts administrators without modifying or blocking the traffic.

---

### Why is an IPS called an inline device?

Because all network traffic passes through it, allowing it to inspect and block malicious packets in real time.

---

### Can a firewall replace an IDS or IPS?

No. A firewall primarily controls network access based on predefined rules, while IDS and IPS provide threat detection and prevention capabilities. These technologies complement each other rather than replace one another.

---

# Key Takeaways

- Firewalls enforce network access control.
- IDS provides visibility through detection and alerting.
- IPS combines detection with automatic prevention.
- A layered security architecture using Firewall, IDS, IPS, EDR, and SIEM offers stronger protection against modern cyber threats.
