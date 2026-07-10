# MITRE ATT&CK Mapping – Module 13: Hacking Web Servers

## Overview

The MITRE ATT&CK Framework is a globally recognized knowledge base that documents adversary tactics and techniques observed during real-world cyber attacks.

Although CEH Module 13 focuses on web servers, many concepts align with ATT&CK techniques across the attack lifecycle. Understanding these mappings helps SOC analysts, defenders, and incident responders improve detection and mitigation strategies.

---

# ATT&CK Tactics Relevant to Web Servers

| Tactic ID | Tactic | Relevance |
|-----------|---------|-----------|
| TA0001 | Initial Access | Public-facing web servers are common entry points. |
| TA0002 | Execution | Malicious code may execute after a server is compromised. |
| TA0003 | Persistence | Attackers may attempt to maintain long-term access. |
| TA0005 | Defense Evasion | Adversaries may try to avoid detection or disable security controls. |
| TA0007 | Discovery | Compromised servers may be used to gather system and network information. |
| TA0008 | Lateral Movement | A compromised web server can be used as a pivot to other internal systems. |
| TA0009 | Collection | Sensitive data hosted by the web application may be targeted. |
| TA0010 | Exfiltration | Stolen information may be transferred out of the environment. |
| TA0011 | Command and Control | Compromised servers may communicate with attacker-controlled infrastructure. |

---

# Initial Access (TA0001)

## Description

Internet-facing web servers are often among the first systems targeted because they are publicly accessible.

### Defensive Focus

- Reduce attack surface
- Keep software updated
- Perform regular vulnerability assessments
- Use secure configurations
- Deploy a Web Application Firewall (WAF)

---

# Execution (TA0002)

## Description

If a web server is compromised, attackers may attempt to execute unauthorized code or scripts.

### Defensive Focus

- Application allowlisting
- Endpoint Detection and Response (EDR)
- File Integrity Monitoring (FIM)
- Continuous monitoring
- Secure file permissions

---

# Persistence (TA0003)

## Description

Adversaries may attempt to maintain access to a compromised web server.

### Defensive Focus

- Monitor configuration changes
- Review scheduled tasks and services
- Audit privileged accounts
- Perform integrity checks
- Rotate credentials when necessary

---

# Defense Evasion (TA0005)

## Description

Attackers often attempt to hide their activity or bypass security controls.

### Defensive Focus

- Centralized logging
- Security Information and Event Management (SIEM)
- Regular log reviews
- Tamper detection
- Alerting on unusual behavior

---

# Discovery (TA0007)

## Description

Once access is obtained, attackers may gather information about the system, applications, and surrounding environment.

### Defensive Focus

- Limit unnecessary information exposure
- Disable verbose error messages
- Remove server version banners
- Restrict access to configuration files

---

# Lateral Movement (TA0008)

## Description

A compromised web server may be used to access additional systems within the network.

### Defensive Focus

- Network segmentation
- Least Privilege
- Strong authentication
- Multi-Factor Authentication (MFA)
- Firewall rules

---

# Collection (TA0009)

## Description

Sensitive information stored or processed by web applications may be targeted.

Examples include:

- Customer records
- Credentials
- Financial data
- Internal documents

### Defensive Focus

- Encrypt sensitive data
- Implement access controls
- Monitor unusual data access
- Maintain audit logs

---

# Exfiltration (TA0010)

## Description

After collecting information, attackers may attempt to transfer it outside the organization.

### Defensive Focus

- Monitor outbound traffic
- Data Loss Prevention (DLP)
- Network monitoring
- SIEM correlation
- Alert on abnormal transfers

---

# Command and Control (TA0011)

## Description

Compromised systems may attempt to communicate with attacker-controlled infrastructure.

### Defensive Focus

- DNS monitoring
- Proxy logging
- Firewall monitoring
- Network Detection and Response (NDR)
- Threat intelligence integration

---

# Detection Opportunities

Security teams should monitor for:

- Unusual HTTP/HTTPS requests
- Repeated authentication failures
- Unexpected file uploads
- Requests to restricted resources
- Configuration changes
- Unexpected administrative activity
- New or modified web content
- Suspicious outbound connections
- Excessive error responses
- High request volumes from a single source

---

# Defensive Security Controls

| Security Control | Purpose |
|------------------|---------|
| Firewall | Restricts unauthorized network access |
| Web Application Firewall (WAF) | Filters malicious web traffic |
| Reverse Proxy | Provides additional protection and traffic management |
| HTTPS/TLS | Encrypts client-server communication |
| SIEM | Centralized log collection and analysis |
| EDR | Detects suspicious endpoint activity |
| File Integrity Monitoring (FIM) | Detects unauthorized file changes |
| Vulnerability Management | Identifies and prioritizes weaknesses |
| Patch Management | Reduces exposure to known vulnerabilities |
| Backup & Recovery | Supports restoration after incidents |

---

# Blue Team Perspective

SOC analysts should focus on:

- Monitoring web server logs
- Reviewing WAF alerts
- Detecting abnormal authentication events
- Investigating unexpected file changes
- Monitoring outbound network connections
- Correlating events in the SIEM
- Responding to alerts quickly
- Verifying secure configurations
- Supporting incident response and recovery

---

# CEH Exam Tips

Remember:

- Internet-facing web servers are common targets.
- Defense-in-depth improves resilience.
- Centralized logging supports investigations.
- WAFs provide additional protection for web applications.
- MITRE ATT&CK helps defenders understand and categorize adversary behavior.

---

# Key Takeaways

- Many ATT&CK tactics can involve web servers at different stages of an attack.
- Secure configuration, continuous monitoring, and layered security controls reduce organizational risk.
- Understanding MITRE ATT&CK improves threat detection, incident response, and communication within security teams.
