# MITRE ATT&CK Mapping – Module 14: Hacking Web Applications

## Overview

The **MITRE ATT&CK Framework** is a globally recognized knowledge base that documents adversary tactics and techniques based on real-world cyber attacks.

Web applications are among the most common attack vectors because they are Internet-facing and often process sensitive business and customer data.

Understanding how web application attacks align with MITRE ATT&CK helps defenders improve detection, response, and overall security posture.

---

# ATT&CK Tactics Relevant to Web Applications

| Tactic | Purpose |
|---------|---------|
| Initial Access | Gain entry through Internet-facing applications |
| Execution | Execute malicious code or scripts |
| Persistence | Maintain long-term access |
| Privilege Escalation | Obtain higher privileges |
| Defense Evasion | Avoid detection by security controls |
| Credential Access | Obtain authentication credentials |
| Discovery | Gather information about the application or environment |
| Collection | Collect sensitive information |
| Exfiltration | Transfer stolen information |
| Command and Control | Communicate with attacker-controlled infrastructure |

---

# Initial Access

## Description

Internet-facing web applications are common entry points for attackers.

Potential targets include:

- Customer portals
- Login pages
- Web APIs
- Content management systems
- E-commerce platforms

### Defensive Focus

- Secure coding
- Web Application Firewall (WAF)
- Vulnerability Management
- Patch Management
- Secure configuration

---

# Execution

## Description

If an application is compromised, attackers may attempt to execute unauthorized code or abuse application functionality.

### Defensive Focus

- Input validation
- Secure coding
- Application allowlisting
- Runtime application protection
- Continuous monitoring

---

# Persistence

## Description

Attackers may attempt to maintain long-term access after compromising an application.

### Defensive Focus

- Monitor privileged accounts
- Audit configuration changes
- Review application logs
- Remove unauthorized accounts
- Regular integrity checks

---

# Privilege Escalation

## Description

Weak authorization controls may allow attackers to gain elevated privileges.

### Defensive Focus

- Role-Based Access Control (RBAC)
- Principle of Least Privilege
- Server-side authorization checks
- Privileged Access Management (PAM)

---

# Defense Evasion

## Description

Adversaries may attempt to bypass application logging or security controls.

### Defensive Focus

- Centralized logging
- SIEM integration
- File Integrity Monitoring
- Web Application Firewall
- Security alerting

---

# Credential Access

## Description

Weak authentication mechanisms may expose user credentials.

### Defensive Focus

- Multi-Factor Authentication (MFA)
- Secure password storage
- Strong password policies
- Login monitoring
- Account lockout policies

---

# Discovery

## Description

After compromising an application, attackers may gather information about the system and surrounding environment.

Examples:

- Application version
- Server configuration
- User roles
- API endpoints

### Defensive Focus

- Minimize information disclosure
- Disable verbose error messages
- Remove unnecessary banners
- Restrict administrative interfaces

---

# Collection

## Description

Applications often store valuable business information.

Examples include:

- Customer records
- Payment information
- Personal data
- Business documents
- Authentication tokens

### Defensive Focus

- Encryption
- Data classification
- Access controls
- Audit logging

---

# Exfiltration

## Description

After collecting information, attackers may attempt to transfer it outside the organization.

### Defensive Focus

- Monitor outbound traffic
- Data Loss Prevention (DLP)
- SIEM correlation
- Network monitoring
- Alert on abnormal transfers

---

# Command and Control

## Description

Compromised applications may communicate with attacker-controlled infrastructure.

### Defensive Focus

- DNS monitoring
- Firewall monitoring
- Proxy logging
- Network Detection and Response (NDR)
- Threat intelligence feeds

---

# Blue Team Detection Opportunities

Security teams should monitor for:

- Repeated login failures
- Privilege changes
- Unexpected administrative actions
- Large numbers of HTTP requests
- Suspicious API activity
- Unexpected file uploads
- Unauthorized configuration changes
- Excessive error responses
- Abnormal outbound traffic
- Large data transfers

---

# Defensive Security Controls

| Security Control | Purpose |
|------------------|---------|
| Web Application Firewall (WAF) | Protects web applications from common attacks |
| HTTPS/TLS | Encrypts communications |
| Multi-Factor Authentication (MFA) | Strengthens authentication |
| Role-Based Access Control (RBAC) | Restricts user permissions |
| SIEM | Centralized logging and monitoring |
| File Integrity Monitoring (FIM) | Detects unauthorized changes |
| Vulnerability Management | Identifies and prioritizes weaknesses |
| Patch Management | Addresses known vulnerabilities |
| Endpoint Detection & Response (EDR) | Detects malicious activity on hosts |
| Backup & Recovery | Supports recovery after incidents |

---

# MITRE ATT&CK Benefits

Using MITRE ATT&CK helps organizations:

- Understand attacker behavior
- Improve threat detection
- Enhance incident response
- Prioritize defensive controls
- Strengthen security operations
- Improve threat hunting

---

# CEH Exam Tips

Remember:

- Web applications are common Internet-facing targets.
- Broken Access Control remains one of the most significant risks.
- Strong authentication and authorization reduce attack opportunities.
- Logging and monitoring are essential for detection.
- Defense in Depth provides multiple layers of protection.
- MITRE ATT&CK helps defenders map attacker behavior throughout the attack lifecycle.

---

# Key Takeaways

- Web application attacks can occur at multiple stages of the MITRE ATT&CK framework.
- Layered defenses, secure development, continuous monitoring, and strong authentication significantly reduce risk.
- Understanding MITRE ATT&CK enables SOC analysts, VAPT professionals, and security engineers to better detect, investigate, and respond to attacks targeting web applications.
