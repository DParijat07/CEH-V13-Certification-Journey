# Threats, Vulnerabilities and Attacks

## Overview

Every cyber attack follows a common pattern: a threat actor identifies a vulnerability, exploits it through an attack vector, and attempts to compromise an organization's assets.

Understanding the relationship between threats, vulnerabilities, exploits, risks, and attacks is fundamental for ethical hackers, SOC analysts, penetration testers, and security engineers.

This document explains these concepts and introduces common threat actors, hacker types, the Cyber Kill Chain, and attack lifecycles.

---

# Information Assets

## Definition

An asset is anything valuable to an organization that requires protection.

Examples include:

- Customer data
- Financial records
- Source code
- Servers
- Databases
- Cloud resources
- Network devices
- Intellectual property
- User credentials

Attackers target assets because they have value.

---

# What is a Threat?

## Definition

A threat is any event, individual, or circumstance capable of causing harm to an information asset.

A threat represents the **potential** for damage but does not necessarily result in an attack.

---

## Types of Threats

### Human Threats

- Cybercriminals
- Insider threats
- Nation-state attackers
- Hacktivists
- Competitors

---

### Natural Threats

- Floods
- Earthquakes
- Lightning
- Fire
- Storms

---

### Environmental Threats

- Power failures
- Hardware failures
- Cooling system failures
- Water leakage

---

# Examples of Threats

- Malware
- Phishing
- Ransomware
- Data theft
- Denial of Service (DoS)
- Insider misuse
- Supply chain attacks

---

# What is a Vulnerability?

## Definition

A vulnerability is a weakness in hardware, software, configuration, process, or human behaviour that can be exploited by a threat.

---

## Common Vulnerabilities

- Weak passwords
- Default credentials
- Missing security patches
- Misconfigured firewalls
- Open ports
- Outdated software
- Insecure coding
- Excessive user privileges
- Poor physical security

---

## Example

```
Unpatched Web Server
        ↓
Known Vulnerability
        ↓
Remote Code Execution
```

---

# What is an Exploit?

## Definition

An exploit is a technique, script, or program used to take advantage of a vulnerability.

The vulnerability already exists—the exploit is the method used to abuse it.

---

## Examples

- SQL Injection
- Buffer Overflow
- SMB Exploits
- Cross-Site Scripting (XSS)
- Remote Code Execution (RCE)
- Privilege Escalation

---

# Relationship Between Threat, Vulnerability and Exploit

```
Information Asset
        ↓
Vulnerability
        ↓
Threat
        ↓
Exploit
        ↓
Successful Attack
```

---

# What is Risk?

## Definition

Risk is the likelihood that a threat will exploit a vulnerability and negatively impact an organization.

---

## Risk Formula

```
Risk = Likelihood × Impact
```

Risk increases when:

- Valuable assets exist
- Serious vulnerabilities exist
- Capable threat actors are present
- Business impact is high

---

# Types of Risk

- Operational Risk
- Financial Risk
- Strategic Risk
- Compliance Risk
- Reputational Risk

---

# Risk Management Process

1. Identify assets
2. Identify threats
3. Identify vulnerabilities
4. Assess risks
5. Implement controls
6. Monitor continuously
7. Review and improve

---

# What is an Attack?

An attack is a deliberate attempt to compromise:

- Confidentiality
- Integrity
- Availability

Attackers exploit vulnerabilities to achieve malicious objectives.

---

# Attack Surface

## Definition

The attack surface is the total number of possible entry points that an attacker can target.

---

## Types of Attack Surface

### Physical

Examples:

- Servers
- Workstations
- USB ports
- Network equipment

---

### Digital

Examples:

- Websites
- APIs
- Email servers
- VPN gateways
- Cloud services
- Mobile applications

---

### Human

Examples:

- Employees
- Contractors
- Vendors
- Help Desk personnel

Humans remain one of the largest attack surfaces due to social engineering.

---

# Attack Vector

## Definition

An attack vector is the path or method used by an attacker to gain unauthorized access.

---

## Common Attack Vectors

- Phishing emails
- Malicious attachments
- Weak passwords
- Open RDP services
- Vulnerable web applications
- USB devices
- Compromised VPNs
- Misconfigured cloud storage
- Third-party software

---

# Threat Actors

A threat actor is any individual or group responsible for malicious activities.

---

## Cybercriminals

**Motivation:**

- Financial gain

Common activities:

- Ransomware
- Banking fraud
- Credit card theft

---

## Nation-State Actors

**Motivation:**

- Espionage
- Cyber warfare
- Intelligence gathering

Typical targets:

- Governments
- Military
- Critical infrastructure

---

## Hacktivists

**Motivation:**

- Political
- Social
- Ideological

Typical attacks:

- Website defacement
- DDoS
- Data leaks

---

## Insider Threats

Individuals with legitimate access who intentionally or accidentally compromise security.

Types:

- Malicious insiders
- Negligent insiders
- Compromised accounts

---

## Organized Cybercrime

Well-funded criminal groups conducting sophisticated attacks for profit.

---

## Script Kiddies

Individuals with limited technical knowledge who use publicly available hacking tools.

---

# Types of Hackers

| Hacker Type | Description |
|-------------|-------------|
| White Hat | Authorized ethical hacker |
| Black Hat | Malicious attacker |
| Gray Hat | Unauthorized but not always malicious |
| Script Kiddie | Uses existing tools with limited knowledge |
| Hacktivist | Motivated by ideology |
| Nation-State Hacker | Government-sponsored attacker |
| Insider | Abuses legitimate access |

---

# Cyber Kill Chain

Developed by **Lockheed Martin**, the Cyber Kill Chain describes the stages of a cyber attack.

---

## Stages

1. Reconnaissance
2. Weaponization
3. Delivery
4. Exploitation
5. Installation
6. Command and Control (C2)
7. Actions on Objectives

```
Reconnaissance
        ↓
Weaponization
        ↓
Delivery
        ↓
Exploitation
        ↓
Installation
        ↓
Command & Control
        ↓
Actions on Objectives
```

Breaking the chain at any stage can disrupt the attack.

---

# Attack Lifecycle

Ethical hackers and attackers often follow a similar technical workflow.

```
Reconnaissance
        ↓
Scanning
        ↓
Enumeration
        ↓
Vulnerability Assessment
        ↓
Exploitation
        ↓
Privilege Escalation
        ↓
Persistence
        ↓
Covering Tracks
```

Understanding this lifecycle helps defenders detect attacks early.

---

# Common Attack Categories

## Malware Attacks

Examples:

- Virus
- Worm
- Trojan
- Spyware
- Ransomware

---

## Network Attacks

Examples:

- DoS
- DDoS
- ARP Spoofing
- DNS Poisoning
- Man-in-the-Middle (MITM)

---

## Web Application Attacks

Examples:

- SQL Injection
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- Server-Side Request Forgery (SSRF)

---

## Credential Attacks

Examples:

- Brute Force
- Dictionary Attack
- Password Spraying
- Credential Stuffing

---

## Social Engineering Attacks

Examples:

- Phishing
- Spear Phishing
- Whaling
- Vishing
- Smishing
- Pretexting
- Baiting

---

# Security Best Practices

Organizations should:

- Apply security patches promptly
- Use Multi-Factor Authentication
- Enforce strong password policies
- Reduce unnecessary attack surface
- Conduct vulnerability assessments
- Perform penetration testing
- Monitor logs continuously
- Train employees against phishing
- Implement the Principle of Least Privilege

---

# CEH Exam Tips

Remember:

- Threat = Potential cause of harm.
- Vulnerability = Weakness.
- Exploit = Method used to abuse a vulnerability.
- Risk = Likelihood and impact of exploitation.
- Attack Surface = Total possible entry points.
- Attack Vector = Method used to compromise a system.
- White Hat = Authorized.
- Black Hat = Malicious.
- Gray Hat = Unauthorized but not always malicious.
- The Cyber Kill Chain has seven stages from Reconnaissance to Actions on Objectives.

---

# Key Takeaways

- Successful cyber attacks occur when threat actors exploit vulnerabilities through specific attack vectors to compromise valuable assets.
- Understanding threats, vulnerabilities, exploits, risk, hacker types, and attack lifecycles enables cybersecurity professionals to prioritize defenses, improve detection, and reduce organizational risk.
