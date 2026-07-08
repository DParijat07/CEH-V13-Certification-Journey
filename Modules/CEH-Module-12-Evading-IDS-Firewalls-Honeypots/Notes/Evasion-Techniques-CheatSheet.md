# Evasion Techniques Cheat Sheet

## Overview

This cheat sheet provides a quick revision of common defense evasion concepts covered in **CEH Module 12**. Understanding these concepts helps security professionals improve detection, strengthen defensive controls, and support incident response.

---

# What is Defense Evasion?

Defense Evasion refers to techniques used to reduce the visibility of malicious activity and avoid detection by security controls.

Security teams study these techniques to:

- Improve detection rules
- Enhance monitoring
- Reduce false negatives
- Strengthen incident response

---

# Common Defense Evasion Concepts

| Concept | Description |
|----------|-------------|
| Traffic Obfuscation | Alters the appearance of network traffic. |
| Encryption | Protects data confidentiality during transmission. |
| Tunneling | Encapsulates one protocol inside another. |
| Proxy Usage | Routes traffic through intermediary systems. |
| VPN | Creates encrypted communication channels. |
| Living off the Land (LotL) | Uses legitimate operating system tools. |
| Masquerading | Makes malicious files or processes appear legitimate. |
| Log Manipulation | Attempts to hide evidence of activity. |

---

# Common Security Controls

Organizations deploy multiple security controls to detect suspicious activity.

- Firewall
- IDS
- IPS
- Web Application Firewall (WAF)
- Endpoint Detection and Response (EDR)
- SIEM
- Network Detection and Response (NDR)

---

# Detection Methods

## Signature-Based Detection

- Matches known attack patterns
- Fast detection
- Effective against known threats

Limitations:

- Cannot detect unknown attacks

---

## Anomaly-Based Detection

- Detects deviations from normal behavior
- Identifies previously unseen threats

Limitations:

- Higher false positive rate

---

## Behavioral Detection

Focuses on:

- User behavior
- Process execution
- Authentication events
- Network communication
- Endpoint activity

---

# Security Monitoring

Common log sources include:

- Firewall Logs
- IDS Alerts
- IPS Events
- Windows Event Logs
- Linux Logs
- DNS Logs
- VPN Logs
- Proxy Logs
- Authentication Logs
- EDR Telemetry

---

# Defensive Best Practices

- Keep security tools updated.
- Enable centralized logging.
- Deploy IDS and IPS at critical locations.
- Monitor privileged accounts.
- Implement Multi-Factor Authentication (MFA).
- Apply the Principle of Least Privilege.
- Perform regular vulnerability assessments.
- Conduct periodic penetration testing.
- Train users on cybersecurity awareness.

---

# MITRE ATT&CK Mapping

| ATT&CK Tactic | Description |
|--------------|-------------|
| TA0005 | Defense Evasion |
| TA0011 | Command and Control |
| TA0007 | Discovery |
| TA0009 | Collection |

---

# SOC Analyst Notes

During investigations, analysts should monitor for:

- Unusual authentication attempts
- Abnormal network traffic
- Unexpected encrypted connections
- Suspicious process execution
- Unusual outbound communication
- Unexpected privilege changes
- High volumes of failed logins

---

# CEH Exam Tips

Remember:

- Firewalls filter traffic.
- IDS detects attacks.
- IPS detects and blocks attacks.
- Honeypots collect threat intelligence.
- SIEM centralizes logs and alerts.
- Layered security improves detection and response.

---

# Key Takeaways

- Defense evasion techniques attempt to reduce the visibility of malicious activity.
- Organizations rely on layered security, centralized logging, and behavioral monitoring to identify suspicious behavior.
- Understanding defense evasion concepts helps defenders improve security posture and incident response.
