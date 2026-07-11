# OWASP Top 10 (2025)

## Overview

The **OWASP (Open Worldwide Application Security Project)** is a global non-profit organization dedicated to improving software security.

The **OWASP Top 10** is the world's most recognized awareness document for web application security. It represents a broad industry consensus regarding the most critical security risks affecting modern web applications.

The current version is **OWASP Top 10:2025**.

---

# Why OWASP Top 10 Matters

OWASP Top 10 helps organizations:

- Identify common application security risks
- Prioritize security improvements
- Improve secure software development
- Guide penetration testing and security assessments
- Train developers and security professionals
- Build security-aware development teams

It is widely used by:

- Ethical Hackers
- SOC Analysts
- VAPT Engineers
- Penetration Testers
- Application Security Engineers
- Security Architects
- Developers
- Security Auditors

---

# OWASP Top 10 (2025)

| Rank | Category | Overview |
|------|----------|----------|
| A01 | Broken Access Control | Users gain unauthorized access to resources or functions. |
| A02 | Security Misconfiguration | Insecure configurations expose applications to attack. |
| A03 | Software Supply Chain Failures | Risks from compromised or vulnerable dependencies, build systems, and software supply chains. |
| A04 | Cryptographic Failures | Weak or improper protection of sensitive information. |
| A05 | Injection | Untrusted input is interpreted as commands or queries. |
| A06 | Insecure Design | Security weaknesses introduced during architecture and design. |
| A07 | Authentication Failures | Weak authentication or session management mechanisms. |
| A08 | Software or Data Integrity Failures | Failure to verify software, updates, or critical data integrity. |
| A09 | Security Logging & Alerting Failures | Insufficient logging, monitoring, or alerting delays incident detection. |
| A10 | Mishandling of Exceptional Conditions | Improper handling of errors, failures, or unexpected conditions leading to security weaknesses. |

---

# Major Changes from OWASP Top 10 (2021)

## Security Misconfiguration moved to #2

Configuration errors continue to be one of the most common causes of real-world compromises.

---

## Software Supply Chain Failures

This replaces and expands the previous **Vulnerable and Outdated Components** category.

It now includes risks involving:

- Third-party libraries
- Software dependencies
- Build systems
- Package repositories
- CI/CD pipelines
- Software distribution infrastructure

---

## Authentication Failures

Previously named **Identification and Authentication Failures**.

The updated name better reflects authentication-related weaknesses while maintaining emphasis on secure identity management.

---

## Security Logging & Alerting Failures

The category now explicitly highlights **alerting**, recognizing that logs alone are insufficient unless security teams are notified of important events.

---

## Mishandling of Exceptional Conditions

A new category introduced in 2025.

Examples include:

- Improper error handling
- Failing open instead of failing securely
- Unhandled exceptions
- Logic errors during abnormal conditions

---

# Defensive Security Focus

Organizations should prioritize:

- Secure software design
- Strong authentication
- Proper authorization
- Secure configuration
- Input validation
- Secure dependency management
- Encryption of sensitive information
- Continuous logging and alerting
- Regular vulnerability management
- Secure software development lifecycle (SSDLC)

---

# Security Testing

Recommended security assessments include:

- Secure Code Review
- Static Application Security Testing (SAST)
- Dynamic Application Security Testing (DAST)
- Interactive Application Security Testing (IAST)
- Software Composition Analysis (SCA)
- Vulnerability Assessment
- Penetration Testing

---

# Recommended Security Controls

| Control | Purpose |
|----------|---------|
| HTTPS/TLS | Encrypt communication |
| Multi-Factor Authentication (MFA) | Strengthen authentication |
| Role-Based Access Control (RBAC) | Restrict access by role |
| Web Application Firewall (WAF) | Protect web applications |
| Secure Configuration | Reduce attack surface |
| Patch Management | Address known vulnerabilities |
| Dependency Management | Reduce supply chain risk |
| SIEM | Centralized logging and alerting |
| Vulnerability Management | Continuous identification and remediation |

---

# CEH Exam Notes

Although **CEH v13** training materials may reference **OWASP Top 10 (2021)**, security professionals should stay current with **OWASP Top 10:2025** and understand the latest categories and industry practices.

---

# Quick Revision Table

| Category | Primary Defensive Focus |
|----------|-------------------------|
| Broken Access Control | Server-side authorization |
| Security Misconfiguration | Secure configuration and hardening |
| Software Supply Chain Failures | Dependency and build pipeline security |
| Cryptographic Failures | Strong encryption and key management |
| Injection | Input validation and secure query handling |
| Insecure Design | Threat modeling and secure architecture |
| Authentication Failures | MFA and secure session management |
| Software or Data Integrity Failures | Trusted software and integrity verification |
| Security Logging & Alerting Failures | SIEM, monitoring, and alerting |
| Mishandling of Exceptional Conditions | Secure error handling and fail-secure design |

---

# Key Takeaways

- OWASP Top 10:2025 reflects the latest trends in web application security.
- Security Misconfiguration and Software Supply Chain Failures have become increasingly important.
- Secure design, proper configuration, continuous monitoring, and secure software supply chains are critical for protecting modern web applications.
- Every cybersecurity professional should understand the OWASP Top 10 and apply its principles throughout the software development lifecycle.
