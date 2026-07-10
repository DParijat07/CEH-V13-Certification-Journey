# Common Web Server Attacks

## Overview

Web servers are publicly accessible and therefore frequent targets for cyber attacks. While attackers may use a variety of techniques, many successful compromises result from insecure configurations, outdated software, weak authentication, or poor operational practices.

Understanding these attack categories helps security professionals identify risks, strengthen defenses, and improve detection capabilities.

---

# Common Attack Categories

The following are common security risks associated with web servers:

- Information Disclosure
- Security Misconfiguration
- Default Credentials
- Directory Listing
- File Upload Risks
- Directory Traversal
- File Inclusion
- Web Shell Deployment (Concept)
- Brute Force Attacks
- Denial-of-Service (DoS)
- SSL/TLS Misconfiguration

---

# Information Disclosure

## Overview

Information disclosure occurs when a web server unintentionally exposes sensitive information.

Examples include:

- Server version
- Operating system details
- Software versions
- Internal IP addresses
- Configuration files
- Backup files
- Error messages

### Risks

- Assists reconnaissance
- Helps identify vulnerable software
- Exposes internal infrastructure

### Defensive Measures

- Remove unnecessary banners
- Disable verbose error messages
- Restrict access to configuration files
- Remove backup files from public directories

---

# Security Misconfiguration

## Overview

Improper server configuration is one of the leading causes of web server compromise.

Examples include:

- Default settings
- Unused services enabled
- Weak permissions
- Debug mode enabled
- Open administrative interfaces
- Insecure directory permissions

### Defensive Measures

- Follow vendor hardening guides
- Remove unused components
- Disable unnecessary services
- Review configurations regularly

---

# Default Credentials

## Overview

Default usernames and passwords should never remain on production systems.

### Risks

- Unauthorized administrative access
- Privilege escalation
- Complete system compromise

### Defensive Measures

- Change all default credentials
- Enforce strong password policies
- Enable Multi-Factor Authentication (MFA)
- Audit privileged accounts

---

# Directory Listing

## Overview

Directory listing allows users to browse directory contents when no default page is present.

Example:

```
/backup/
/uploads/
/documents/
/images/
```

### Risks

- Exposure of sensitive files
- Disclosure of project structure
- Leakage of confidential information

### Defensive Measures

- Disable directory browsing
- Configure default index pages
- Restrict permissions

---

# File Upload Risks

## Overview

Many web applications allow users to upload files.

Without proper validation, uploads may introduce security risks.

### Defensive Measures

- Validate file types
- Restrict file size
- Scan uploaded files
- Store uploads outside the web root
- Prevent execution in upload directories

---

# Directory Traversal (Concept)

## Overview

Directory traversal refers to attempts to access files or directories outside the intended application structure.

### Potential Risks

- Exposure of sensitive files
- Disclosure of configuration data
- Access to restricted resources

### Defensive Measures

- Validate user input
- Restrict filesystem access
- Apply least privilege
- Use secure path validation

---

# File Inclusion (Concept)

## Overview

Some applications dynamically include files during execution.

Improper validation can introduce security risks.

Types:

- Local File Inclusion (LFI)
- Remote File Inclusion (RFI)

### Defensive Measures

- Validate input
- Use allowlists
- Restrict file inclusion
- Keep frameworks updated

---

# Web Shells (Concept)

## Overview

A web shell is a script or program that provides unauthorized remote access through a compromised web server.

### Risks

- Persistence
- Unauthorized command execution
- Data theft
- Further compromise

### Defensive Measures

- Monitor file integrity
- Restrict upload functionality
- Review web server logs
- Deploy EDR solutions
- Perform regular integrity checks

---

# Brute Force Attacks

## Overview

Attackers may repeatedly attempt to guess authentication credentials.

### Defensive Measures

- Strong password policy
- Account lockout
- Multi-Factor Authentication
- Rate limiting
- Login monitoring

---

# Denial-of-Service (DoS)

## Overview

DoS attacks attempt to overwhelm server resources, making services unavailable to legitimate users.

Distributed DoS (DDoS) attacks originate from multiple systems simultaneously.

### Defensive Measures

- Rate limiting
- Load balancing
- Reverse proxies
- Content Delivery Networks (CDNs)
- DDoS protection services

---

# SSL/TLS Misconfiguration

## Examples

- Expired certificates
- Weak cipher suites
- Deprecated protocol versions
- Self-signed certificates in production

### Defensive Measures

- Use valid certificates
- Disable outdated TLS versions
- Renew certificates before expiration
- Regularly review TLS configurations

---

# Web Application Firewall (WAF)

A Web Application Firewall filters HTTP and HTTPS traffic before it reaches the web server.

### Benefits

- Blocks malicious requests
- Reduces exposure to common web attacks
- Provides detailed logging
- Supports incident investigations

Examples:

- ModSecurity
- Cloudflare WAF
- AWS WAF
- Azure Web Application Firewall

---

# Logging and Detection

Security teams should monitor for:

- Unusual HTTP methods
- Repeated authentication failures
- Unexpected file uploads
- Requests to restricted resources
- High request volumes
- Repeated server errors
- Suspicious user agents
- Configuration changes

Forward logs to a SIEM for centralized monitoring and correlation.

---

# Security Best Practices

- Keep software updated.
- Apply security patches promptly.
- Remove unnecessary services.
- Disable directory listing.
- Protect configuration files.
- Use HTTPS with modern TLS.
- Enforce strong authentication.
- Enable centralized logging.
- Conduct regular vulnerability assessments.
- Perform periodic penetration testing.

---

# CEH Exam Tips

Remember:

- Security misconfiguration is one of the most common web server risks.
- Directory listing should generally be disabled.
- Default credentials must always be changed.
- Information disclosure often assists reconnaissance.
- WAFs provide an additional layer of protection.
- Continuous monitoring is essential for detecting suspicious activity.

---

# Interview Questions

### Why are web servers common attack targets?

Because they are publicly accessible and often host sensitive applications and data.

---

### What is information disclosure?

The unintended exposure of sensitive information by a web server.

---

### Why should directory listing be disabled?

To prevent unauthorized users from browsing files and directories.

---

### What is the purpose of a Web Application Firewall?

A WAF filters and monitors HTTP/HTTPS traffic to help protect web applications from common attacks.

---

### How can organizations reduce web server risk?

By applying patches, securely configuring systems, enforcing strong authentication, monitoring logs, and following defense-in-depth principles.

---

# Key Takeaways

- Many web server compromises result from poor configuration rather than flaws in the server software itself.
- Secure configuration, continuous monitoring, timely patching, and layered defenses significantly improve web server security.
- Understanding common attack categories enables defenders to identify risks and strengthen organizational security.
