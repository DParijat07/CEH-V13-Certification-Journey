# Common Web Application Vulnerabilities

## Overview

Web application vulnerabilities are weaknesses in the design, implementation, configuration, or deployment of a web application that may compromise its confidentiality, integrity, or availability.

Understanding these vulnerabilities enables security professionals to identify risks, recommend mitigations, and improve application security.

---

# Common Causes

Most vulnerabilities arise from:

- Poor secure coding practices
- Inadequate input validation
- Weak authentication
- Improper authorization
- Security misconfiguration
- Outdated software components
- Insufficient logging and monitoring
- Lack of security testing

---

# Common Web Application Vulnerabilities

## 1. Broken Access Control

Users gain unauthorized access to resources or functions beyond their permissions.

Examples:

- Viewing another user's data
- Accessing administrative pages
- Privilege escalation

Mitigation:

- Role-Based Access Control (RBAC)
- Principle of Least Privilege
- Server-side authorization checks

---

## 2. Authentication Weaknesses

Improper authentication mechanisms may allow unauthorized access.

Examples:

- Weak passwords
- Missing MFA
- Password reuse
- Poor session management

Mitigation:

- Strong password policy
- Multi-Factor Authentication
- Secure session management
- Account lockout mechanisms

---

## 3. Security Misconfiguration

Improper system or application configuration exposes unnecessary attack surfaces.

Examples:

- Default credentials
- Debug mode enabled
- Directory listing
- Unnecessary services
- Weak permissions

Mitigation:

- Secure configuration
- System hardening
- Regular configuration reviews

---

## 4. Injection Vulnerabilities

Injection occurs when untrusted input is interpreted as commands or queries.

Common types include:

- SQL Injection
- NoSQL Injection
- Command Injection
- LDAP Injection
- XML Injection

Mitigation:

- Input validation
- Parameterized queries
- Allowlist validation
- Secure coding practices

---

## 5. Cryptographic Weaknesses

Sensitive information is not properly protected.

Examples:

- Weak encryption
- Plaintext passwords
- Insecure key storage
- Weak TLS configuration

Mitigation:

- Modern encryption algorithms
- HTTPS
- Secure key management
- Password hashing

---

## 6. Session Management Weaknesses

Poor session handling may expose authenticated users.

Examples:

- Predictable session IDs
- Sessions that never expire
- Insecure cookies

Mitigation:

- Random session identifiers
- Secure and HttpOnly cookies
- Session timeout
- Session regeneration after login

---

## 7. File Upload Risks

Applications allowing user uploads may introduce security risks.

Mitigation:

- Restrict file types
- Validate extensions
- Limit file size
- Scan uploads for malware
- Store uploads securely

---

## 8. API Security Issues

Modern applications rely heavily on APIs.

Common risks:

- Weak authentication
- Excessive data exposure
- Missing authorization
- Insecure endpoints

Mitigation:

- API authentication
- Authorization checks
- Rate limiting
- API gateways

---

## 9. Business Logic Flaws

Application workflows may be abused without exploiting technical vulnerabilities.

Examples:

- Bypassing payment restrictions
- Unlimited discount usage
- Workflow manipulation

Mitigation:

- Threat modeling
- Business rule validation
- Security testing

---

## 10. Sensitive Data Exposure

Sensitive information should always be protected.

Examples:

- Personal information
- Financial records
- Medical records
- Authentication credentials

Mitigation:

- Encrypt sensitive data
- HTTPS
- Data minimization
- Secure storage

---

## 11. Security Logging and Monitoring Failures

Insufficient visibility delays incident detection.

Mitigation:

- Centralized logging
- SIEM integration
- Security alerting
- Regular log reviews

---

## 12. Software Supply Chain Risks

Applications depend on third-party software components.

Examples:

- Vulnerable libraries
- Compromised packages
- Outdated dependencies

Mitigation:

- Software Composition Analysis (SCA)
- Dependency management
- Patch management
- Trusted repositories

---

# General Security Best Practices

Organizations should:

- Validate all user input
- Apply least privilege
- Enforce strong authentication
- Encrypt sensitive information
- Keep software updated
- Conduct regular vulnerability assessments
- Perform penetration testing
- Implement secure software development lifecycle (SSDLC)
- Monitor applications continuously

---

# CEH Exam Tips

Remember:

- Broken Access Control remains one of the highest-risk vulnerabilities.
- Security Misconfiguration is extremely common.
- Strong authentication reduces account compromise.
- Secure coding prevents many application vulnerabilities.
- Logging and monitoring support incident detection and response.
- Regular updates reduce exposure to known vulnerabilities.

---

# Quick Revision Table

| Vulnerability | Primary Defense |
|--------------|-----------------|
| Broken Access Control | Server-side authorization |
| Authentication Weakness | MFA and secure authentication |
| Security Misconfiguration | System hardening |
| Injection | Input validation |
| Cryptographic Weakness | Strong encryption |
| Session Weakness | Secure session management |
| File Upload Risk | File validation |
| API Security Issues | Authentication and authorization |
| Business Logic Flaws | Secure design |
| Sensitive Data Exposure | Encryption |
| Logging Failures | SIEM and monitoring |
| Supply Chain Risks | Dependency management |

---

# Key Takeaways

- Most web application vulnerabilities are preventable through secure design, secure coding, proper configuration, and continuous security testing.
- Security should be integrated throughout the software development lifecycle rather than added after deployment.
- Understanding these vulnerabilities enables cybersecurity professionals to better assess, defend, and improve modern web applications.
