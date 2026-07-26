# Security Controls and Defense

## Overview

No single security mechanism can completely protect an organization from cyber threats. Modern cybersecurity relies on multiple layers of security controls working together to reduce risk, detect attacks, and ensure business continuity.

Security controls are safeguards implemented to protect information assets, reduce vulnerabilities, prevent attacks, detect malicious activity, and recover from security incidents.

This document explains the major categories of security controls, defense strategies, governance, security frameworks, and incident response concepts.

---

# What are Security Controls?

## Definition

Security controls are safeguards, countermeasures, or mechanisms implemented to protect information systems from threats and vulnerabilities.

Their primary objectives are to:

- Protect information assets
- Reduce risk
- Prevent unauthorized access
- Detect malicious activities
- Support recovery
- Ensure regulatory compliance

---

# Categories of Security Controls

Security controls are generally classified into three major categories:

```
Security Controls
        │
 ┌──────┼──────┐
 │      │      │
Administrative
Technical
Physical
```

---

# Administrative Controls

## Definition

Administrative controls are management policies, procedures, and practices that guide how people interact with information systems.

These controls influence employee behaviour and establish organizational security requirements.

---

## Examples

- Information Security Policy
- Password Policy
- Acceptable Use Policy
- Security Awareness Training
- Background Verification
- Risk Assessments
- Vendor Management
- Incident Response Plan
- Change Management

---

## Advantages

- Reduces human error
- Defines responsibilities
- Supports compliance
- Improves security awareness

---

# Technical Controls

## Definition

Technical controls use hardware and software to enforce security policies and protect systems.

---

## Examples

### Network Security

- Firewalls
- IDS
- IPS
- VPN

### Endpoint Security

- Antivirus
- Endpoint Detection and Response (EDR)
- Host Firewalls

### Identity Security

- Multi-Factor Authentication (MFA)
- Access Control Lists (ACLs)
- Role-Based Access Control (RBAC)

### Data Security

- Encryption
- Data Loss Prevention (DLP)
- Digital Signatures

### Monitoring

- SIEM
- Log Management
- File Integrity Monitoring (FIM)

---

## Benefits

- Automated protection
- Real-time monitoring
- Continuous enforcement
- Scalable deployment

---

# Physical Controls

## Definition

Physical controls protect facilities, personnel, and equipment from unauthorized physical access.

---

## Examples

- Security Guards
- CCTV
- Biometric Authentication
- Smart Cards
- Door Locks
- Fencing
- Security Lighting
- Visitor Logs
- Alarm Systems

---

## Objectives

- Prevent theft
- Restrict physical access
- Protect hardware
- Ensure personnel safety

---

# Functional Classification of Security Controls

Security controls can also be categorized by their purpose.

---

# Preventive Controls

Prevent security incidents before they occur.

Examples:

- Firewalls
- MFA
- Encryption
- Access Control
- Secure Configuration
- Security Awareness Training

---

# Detective Controls

Identify malicious activities after they occur.

Examples:

- IDS
- SIEM
- Audit Logs
- Security Monitoring
- CCTV
- File Integrity Monitoring

---

# Corrective Controls

Restore systems after an incident.

Examples:

- Malware Removal
- Patch Management
- Password Reset
- System Restoration

---

# Deterrent Controls

Discourage attackers from attempting malicious actions.

Examples:

- Warning Banners
- Visible CCTV
- Security Guards
- Legal Notices

---

# Compensating Controls

Alternative controls implemented when primary controls are not feasible.

Example:

Enhanced monitoring when MFA cannot be deployed.

---

# Recovery Controls

Restore business operations after disruption.

Examples:

- Backups
- Disaster Recovery
- Business Continuity
- System Restore

---

# Defense in Depth

## Definition

Defense in Depth is a layered security strategy where multiple independent controls protect organizational assets.

If one control fails, other layers continue providing protection.

---

## Security Layers

```
Users
      ↓
Policies
      ↓
Identity & Access Management
      ↓
Endpoints
      ↓
Network Security
      ↓
Application Security
      ↓
Data Protection
      ↓
Monitoring & Logging
      ↓
Backup & Recovery
```

---

# Zero Trust

## Principle

**Never Trust, Always Verify**

Every request must be authenticated, authorized, and continuously validated regardless of whether it originates inside or outside the organization's network.

---

## Core Principles

- Verify explicitly
- Assume breach
- Least privilege access
- Continuous monitoring
- Strong identity verification

---

# Security Policies

## Definition

A security policy is a high-level document that defines an organization's security objectives and expectations.

---

## Common Policies

- Information Security Policy
- Password Policy
- Remote Access Policy
- Acceptable Use Policy
- Incident Response Policy
- Backup Policy
- Data Classification Policy

---

# Standards

Standards define mandatory technical requirements.

Examples:

- Password complexity
- Encryption algorithms
- Secure network configurations

Standards are compulsory within an organization.

---

# Baselines

Baselines establish the minimum acceptable level of security.

Examples:

- Minimum password length
- Required antivirus software
- Approved operating system versions

---

# Procedures

Procedures provide detailed step-by-step instructions.

Example:

Password Reset Procedure

1. Verify user identity
2. Reset password
3. Require password change
4. Document the request

---

# Guidelines

Guidelines are recommended best practices rather than mandatory requirements.

Example:

Recommendations for creating strong passphrases.

---

# Governance

## Definition

Governance ensures cybersecurity supports business objectives while maintaining accountability and regulatory compliance.

Governance defines:

- Roles
- Responsibilities
- Decision-making
- Oversight
- Accountability

---

# Risk Management

Risk management is the ongoing process of identifying, assessing, treating, and monitoring cybersecurity risks.

Typical process:

```
Identify Assets
        ↓
Identify Threats
        ↓
Identify Vulnerabilities
        ↓
Assess Risk
        ↓
Implement Controls
        ↓
Monitor & Review
```

---

# Compliance

Organizations must comply with legal and industry regulations.

Examples include:

- GDPR
- HIPAA
- PCI DSS
- ISO/IEC 27001
- Local data protection laws

Compliance reduces legal, financial, and reputational risks.

---

# NIST Cybersecurity Framework (CSF)

The NIST CSF provides a structured approach to cybersecurity.

## Five Core Functions

```
Identify
    ↓
Protect
    ↓
Detect
    ↓
Respond
    ↓
Recover
```

### Identify

Understand assets, risks, and business environment.

### Protect

Implement safeguards to reduce risk.

### Detect

Identify cybersecurity events quickly.

### Respond

Contain and mitigate incidents.

### Recover

Restore operations and improve resilience.

---

# ISO/IEC 27001

ISO/IEC 27001 is an international standard for Information Security Management Systems (ISMS).

Key objectives:

- Risk-based security management
- Continuous improvement
- Security governance
- Compliance
- Information asset protection

---

# CIS Critical Security Controls

The CIS Controls provide prioritized security best practices.

Examples include:

- Asset Inventory
- Secure Configuration
- Continuous Vulnerability Management
- Controlled Use of Administrative Privileges
- Account Management
- Logging and Monitoring
- Malware Defences
- Data Recovery

---

# Incident Response

## Definition

Incident Response (IR) is the structured process used to identify, contain, eradicate, and recover from cybersecurity incidents.

---

# Incident Response Lifecycle

```
Preparation
      ↓
Identification
      ↓
Containment
      ↓
Eradication
      ↓
Recovery
      ↓
Lessons Learned
```

---

## Preparation

- Policies
- Playbooks
- Security tools
- Training
- Backups

---

## Identification

Determine whether suspicious activity represents a genuine security incident.

Sources include:

- SIEM alerts
- IDS/IPS
- User reports
- EDR alerts

---

## Containment

Limit the spread of an incident.

Examples:

- Isolate infected systems
- Disable compromised accounts
- Block malicious IP addresses

---

## Eradication

Remove the root cause.

Examples:

- Delete malware
- Patch vulnerabilities
- Remove backdoors

---

## Recovery

Restore systems safely.

Examples:

- Restore backups
- Verify system integrity
- Resume normal operations

---

## Lessons Learned

Conduct a post-incident review.

Questions include:

- What happened?
- Why did it happen?
- What worked well?
- What improvements are needed?

---

# Business Continuity Planning (BCP)

Business Continuity Planning ensures that critical business functions continue during disruptive events.

Examples of disruptions:

- Natural disasters
- Cyber attacks
- Power failures
- Hardware failures

---

# Disaster Recovery (DR)

Disaster Recovery focuses specifically on restoring IT systems and infrastructure after a major incident.

Examples:

- Server recovery
- Database restoration
- Network recovery
- Cloud environment recovery

---

# BCP vs DR

| Business Continuity Planning | Disaster Recovery |
|------------------------------|-------------------|
| Focuses on business operations | Focuses on IT systems |
| Broader organizational scope | Technology-focused |
| Keeps critical services running | Restores infrastructure |

---

# Security Best Practices

Organizations should:

- Apply security patches promptly
- Enable Multi-Factor Authentication
- Enforce strong password policies
- Follow the Principle of Least Privilege
- Encrypt sensitive information
- Conduct regular vulnerability assessments
- Perform penetration testing
- Monitor security logs continuously
- Train employees regularly
- Maintain tested backups
- Review security policies periodically

---

# CEH Exam Tips

Remember:

- Administrative controls manage people and processes.
- Technical controls protect systems using hardware and software.
- Physical controls protect facilities and equipment.
- Preventive controls stop attacks.
- Detective controls identify attacks.
- Corrective controls restore systems.
- Defense in Depth uses multiple layers of protection.
- Zero Trust follows the principle: **Never Trust, Always Verify.**
- NIST CSF consists of Identify, Protect, Detect, Respond, and Recover.
- Incident Response follows: Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned.

---

# Key Takeaways

- Effective cybersecurity requires a balanced combination of administrative, technical, and physical controls supported by governance, risk management, and compliance.
- Layered security, continuous monitoring, structured incident response, and established frameworks such as NIST CSF and ISO/IEC 27001 help organizations reduce cyber risk and improve resilience against evolving threats.
