# Web Server Hardening

## Overview

Web server hardening is the process of securely configuring a web server to reduce its attack surface, minimize security risks, and improve resilience against cyber threats.

Hardening is not a one-time task—it is an ongoing process that includes secure configuration, patch management, monitoring, and regular security assessments.

---

# Objectives

The primary objectives of web server hardening are:

- Reduce the attack surface
- Prevent unauthorized access
- Protect sensitive data
- Improve system reliability
- Support compliance requirements
- Enhance monitoring and incident response

---

# Hardening Checklist

## 1. Keep Software Updated

Regularly update:

- Operating System
- Web Server Software
- Application Frameworks
- Plugins and Extensions
- SSL/TLS Libraries

Benefits:

- Fixes known vulnerabilities
- Improves stability
- Enhances performance

---

## 2. Remove Unnecessary Components

Disable or uninstall:

- Unused services
- Unused modules
- Sample applications
- Default web pages
- Test scripts
- Unused user accounts

Reducing unnecessary components lowers the attack surface.

---

## 3. Secure Configuration

Configure the server to:

- Disable directory listing
- Hide unnecessary server information
- Protect configuration files
- Disable unused HTTP methods
- Use secure file permissions
- Restrict administrative interfaces

Review configurations regularly.

---

## 4. Enforce HTTPS

Always encrypt web traffic using HTTPS.

Best practices:

- Use valid SSL/TLS certificates
- Redirect HTTP to HTTPS
- Disable deprecated SSL/TLS versions
- Use strong cipher suites
- Enable HTTP Strict Transport Security (HSTS)

---

## 5. Strong Authentication

Protect administrative access by:

- Using strong passwords
- Enabling Multi-Factor Authentication (MFA)
- Limiting privileged accounts
- Implementing Role-Based Access Control (RBAC)
- Reviewing accounts periodically

---

## 6. Apply the Principle of Least Privilege

Grant users and services only the permissions necessary to perform their tasks.

Benefits:

- Reduces misuse
- Limits the impact of compromised accounts
- Improves accountability

---

## 7. Protect Sensitive Files

Restrict access to:

- Configuration files
- Backup files
- Log files
- Certificates
- Private keys

Store sensitive files outside publicly accessible directories whenever possible.

---

## 8. Secure File Uploads

If file uploads are supported:

- Validate file types
- Restrict file sizes
- Scan uploads for malware
- Store uploads securely
- Prevent execution in upload directories

---

## 9. Logging

Enable and retain:

- Access Logs
- Error Logs
- Authentication Logs
- Audit Logs
- Application Logs

Logs support:

- Troubleshooting
- Threat detection
- Incident response
- Compliance

---

## 10. Continuous Monitoring

Monitor for:

- Failed login attempts
- Unusual HTTP requests
- Unexpected file uploads
- Configuration changes
- High request volumes
- Suspicious user agents
- Unauthorized administrative actions

Integrate monitoring with a SIEM where possible.

---

## 11. File Integrity Monitoring (FIM)

Monitor critical files for unauthorized changes.

Examples:

- Configuration files
- Website content
- Application binaries
- Security policies

Benefits:

- Detects tampering
- Supports forensic investigations
- Improves incident response

---

## 12. Backup and Recovery

Maintain regular backups of:

- Website files
- Databases
- Configuration files
- SSL/TLS certificates

Backup best practices:

- Encrypt backup data
- Test restoration procedures
- Store backups securely
- Maintain offline or immutable copies

---

## 13. Web Application Firewall (WAF)

Deploy a WAF to inspect and filter HTTP/HTTPS traffic.

Benefits:

- Blocks malicious requests
- Improves visibility
- Supports security monitoring
- Provides an additional defensive layer

Examples:

- ModSecurity
- Cloudflare WAF
- AWS WAF
- Azure Web Application Firewall

---

## 14. Vulnerability Assessments

Conduct periodic assessments to identify weaknesses.

Typical activities include:

- Configuration reviews
- Patch verification
- Exposure analysis
- Security baseline validation

Assessments should be scheduled regularly and after significant system changes.

---

## 15. Security Audits

Perform regular security audits to verify:

- Secure configurations
- Access controls
- Logging practices
- Patch levels
- Compliance with organizational policies

---

# Defense-in-Depth

Effective web server security combines multiple layers of protection.

```
Internet
     │
Firewall
     │
Web Application Firewall
     │
Reverse Proxy
     │
Web Server
     │
Application Server
     │
Database
     │
Logging
     │
SIEM
     │
SOC Team
```

No single security control is sufficient on its own.

---

# Security Best Practices Summary

- Keep software updated.
- Remove unused components.
- Disable unnecessary services.
- Use HTTPS everywhere.
- Protect configuration files.
- Enforce strong authentication.
- Apply least privilege.
- Enable centralized logging.
- Monitor continuously.
- Perform regular vulnerability assessments.
- Maintain secure backups.
- Review configurations periodically.

---

# CEH Exam Tips

Remember:

- Hardening reduces the attack surface.
- Patch management fixes known vulnerabilities.
- HTTPS protects data in transit.
- File Integrity Monitoring detects unauthorized changes.
- WAFs help protect web applications.
- Logging is essential for investigations.
- Defense-in-depth provides stronger protection than relying on a single control.

---

# Interview Questions

### What is web server hardening?

The process of securely configuring and maintaining a web server to reduce security risks and improve resilience.

---

### Why is patch management important?

It addresses known vulnerabilities and helps prevent exploitation.

---

### Why should organizations use HTTPS?

HTTPS encrypts communication, ensuring confidentiality, integrity, and server authentication.

---

### What is the Principle of Least Privilege?

Users and services should receive only the minimum permissions required to perform their tasks.

---

### Why is centralized logging valuable?

It enables event correlation, faster investigations, improved monitoring, and better incident response.

---

# Key Takeaways

- Web server hardening is a continuous process.
- Secure configuration, timely updates, strong authentication, and continuous monitoring are fundamental to protecting web servers.
- Layered defenses, regular assessments, and effective logging significantly improve an organization's security posture.
