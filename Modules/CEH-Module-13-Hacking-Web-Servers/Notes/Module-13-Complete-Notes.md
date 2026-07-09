# Module 13 – Hacking Web Servers

---

# Overview

Web servers are one of the most critical components of modern IT infrastructure. They host websites, web applications, APIs, and online services that are accessed by users across the Internet.

Because web servers are publicly accessible, they are frequent targets for cyber attacks. Understanding how web servers operate, common vulnerabilities, and defensive security practices is essential for ethical hackers, penetration testers, SOC analysts, and security professionals.

---

# Learning Objectives

After completing this module, you should be able to:

- Understand web server architecture
- Explain the HTTP and HTTPS protocols
- Identify common web server software
- Understand web server components
- Perform basic web server enumeration
- Recognize common web server attacks
- Apply web server hardening techniques
- Understand logging and monitoring
- Implement defensive security best practices

---

# What is a Web Server?

A **Web Server** is hardware and software that stores, processes, and delivers web content to clients over a network using the HTTP or HTTPS protocols.

A web server receives requests from clients (usually web browsers), processes them, and returns the requested resources.

Examples of resources include:

- HTML pages
- CSS files
- JavaScript files
- Images
- Videos
- Documents
- APIs
- Dynamic web content

---

# Web Server Architecture

Basic Architecture

```
             User
              │
              ▼
        Web Browser
              │
      HTTP / HTTPS
              │
              ▼
         Web Server
              │
     Static / Dynamic Content
              │
              ▼
        Database Server
```

---

# Components of a Web Server

## Client

The client is the device requesting resources.

Examples:

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

---

## Web Server Software

Processes client requests and serves web content.

Common web servers include:

- Apache HTTP Server
- Microsoft IIS
- Nginx
- LiteSpeed
- Caddy

---

## Application Server

Executes application logic.

Examples:

- PHP
- ASP.NET
- Node.js
- Java (Tomcat)
- Python (Flask, Django)

---

## Database Server

Stores application data.

Examples:

- MySQL
- PostgreSQL
- Microsoft SQL Server
- Oracle Database
- MongoDB

---

# Static vs Dynamic Websites

## Static Website

Characteristics:

- Fixed content
- HTML and CSS only
- Same content for every user
- Faster performance
- Easier to host

Examples:

- Portfolio websites
- Company landing pages
- Documentation sites

---

## Dynamic Website

Characteristics:

- Content generated in real time
- Uses databases
- User authentication
- Interactive features
- Server-side scripting

Examples:

- Facebook
- Amazon
- Gmail
- Online Banking
- E-commerce websites

---

# Common Web Server Software

## Apache HTTP Server

- Open source
- Cross-platform
- Highly configurable
- Supports modules
- Widely used in Linux environments

---

## Microsoft Internet Information Services (IIS)

- Developed by Microsoft
- Runs on Windows Server
- Supports ASP.NET applications
- Integrates with Active Directory

---

## Nginx

- Lightweight
- High performance
- Reverse proxy support
- Load balancing
- Popular for cloud deployments

---

## LiteSpeed

Features:

- High performance
- Apache compatible
- Efficient resource usage
- Built-in caching

---

# Web Server Functions

A web server performs several important tasks:

- Receive HTTP/HTTPS requests
- Process client requests
- Deliver static content
- Generate dynamic content
- Authenticate users
- Manage sessions
- Log requests
- Handle SSL/TLS encryption
- Communicate with databases

---

# Web Server Ports

| Port | Protocol | Service |
|------|----------|----------|
| 80 | HTTP | Unencrypted Web Traffic |
| 443 | HTTPS | Encrypted Web Traffic |
| 8080 | HTTP Alternate | Development / Proxy |
| 8443 | HTTPS Alternate | Secure Administration |

---

# Web Server Logs

Web servers generate logs for monitoring and troubleshooting.

Common log types:

- Access Logs
- Error Logs
- Authentication Logs
- Audit Logs

Security teams analyze these logs to detect suspicious activity and investigate incidents.

---

# Importance of Web Server Security

Compromised web servers can lead to:

- Data breaches
- Website defacement
- Malware distribution
- Credential theft
- Unauthorized access
- Service disruption
- Financial loss
- Reputational damage

Protecting web servers is therefore a critical part of an organization's cybersecurity strategy.

---

# CEH Exam Tips

Remember:

- A web server delivers web content using HTTP or HTTPS.
- Apache, IIS, and Nginx are the most common web server software.
- Static websites deliver fixed content, while dynamic websites generate content based on user interaction.
- Web servers commonly communicate with databases and application servers.
- Ports 80 and 443 are the standard ports for HTTP and HTTPS.

---

# Key Takeaways

- Web servers host websites, applications, and APIs.
- Understanding web server architecture is essential for both offensive and defensive security.
- Apache, IIS, and Nginx are the most widely used web servers.
- Logs provide valuable information for monitoring, incident response, and forensic investigations.
- Strong web server security reduces the risk of cyber attacks and protects sensitive information.

---

# HTTP and HTTPS Fundamentals

## Overview

Communication between a client (web browser) and a web server primarily occurs using the **Hypertext Transfer Protocol (HTTP)** or its secure version, **HTTPS (Hypertext Transfer Protocol Secure)**.

Understanding these protocols is essential for web security, vulnerability assessment, penetration testing, and network traffic analysis.

---

# HTTP

## What is HTTP?

HTTP (Hypertext Transfer Protocol) is an **application-layer protocol** used to transfer web resources between clients and web servers.

Characteristics:

- Stateless protocol
- Client-server architecture
- Request-response communication
- Default Port: **80**
- Data is transmitted in plaintext

Because HTTP traffic is not encrypted, attackers may intercept or modify transmitted data if appropriate security controls are not in place.

---

# HTTPS

## What is HTTPS?

HTTPS (Hypertext Transfer Protocol Secure) is the secure version of HTTP.

It combines:

- HTTP
- SSL/TLS Encryption

Default Port:

**443**

HTTPS provides:

- Confidentiality
- Integrity
- Authentication

Most modern websites use HTTPS to protect user data.

---

# HTTP vs HTTPS

| Feature | HTTP | HTTPS |
|----------|-------|--------|
| Default Port | 80 | 443 |
| Encryption | No | Yes |
| Confidentiality | No | Yes |
| Integrity | No | Yes |
| Authentication | No | Yes (Certificate Based) |
| Security | Low | High |

---

# Client–Server Communication

```
Browser
   │
HTTP Request
   │
   ▼
Web Server
   │
Process Request
   │
HTTP Response
   │
   ▼
Browser
```

The browser sends an HTTP request, and the server responds with the requested resource.

---

# HTTP Request

A request sent by the client typically contains:

- Request Method
- URL
- HTTP Version
- Headers
- Cookies
- Request Body (optional)

Example:

```
GET /index.html HTTP/1.1
Host: example.com
User-Agent: Chrome
```

---

# HTTP Response

A server response generally includes:

- Status Code
- Response Headers
- Response Body

Example:

```
HTTP/1.1 200 OK
Content-Type: text/html
Server: Apache
```

---

# HTTP Methods

HTTP methods define the action the client wants the server to perform.

| Method | Purpose |
|---------|----------|
| GET | Retrieve data |
| POST | Submit data |
| PUT | Update a resource |
| DELETE | Remove a resource |
| HEAD | Retrieve headers only |
| OPTIONS | Display supported methods |
| PATCH | Partially update a resource |

---

# Common HTTP Status Codes

## 1xx – Informational

Example:

- 100 Continue

---

## 2xx – Success

Examples:

- 200 OK
- 201 Created
- 204 No Content

---

## 3xx – Redirection

Examples:

- 301 Moved Permanently
- 302 Found
- 304 Not Modified

---

## 4xx – Client Errors

Examples:

- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 405 Method Not Allowed

---

## 5xx – Server Errors

Examples:

- 500 Internal Server Error
- 502 Bad Gateway
- 503 Service Unavailable
- 504 Gateway Timeout

---

# URL Structure

Example:

```
https://www.example.com:443/login/index.php?id=5
```

Components:

| Component | Example |
|-----------|----------|
| Protocol | https |
| Domain | www.example.com |
| Port | 443 |
| Path | /login/ |
| File | index.php |
| Parameter | id=5 |

---

# HTTP Headers

Headers provide additional information about requests and responses.

Common Request Headers:

- Host
- User-Agent
- Accept
- Cookie
- Authorization
- Referer

Common Response Headers:

- Server
- Content-Type
- Content-Length
- Set-Cookie
- Cache-Control
- Location

---

# Cookies

A **Cookie** is a small piece of data stored by the browser on behalf of a website.

Uses:

- Session management
- User preferences
- Authentication
- Personalization

Types:

- Session Cookies
- Persistent Cookies
- Secure Cookies
- HttpOnly Cookies

---

# Sessions

A **Session** is a mechanism used by web applications to maintain a user's authenticated state.

Typical workflow:

```
User Login
      │
Server Creates Session
      │
Session ID Generated
      │
Browser Stores Session Cookie
      │
Future Requests Include Session ID
```

Sessions allow web applications to remember users between requests.

---

# MIME Types

MIME (Multipurpose Internet Mail Extensions) specifies the type of content being transferred.

Examples:

| MIME Type | Description |
|------------|-------------|
| text/html | HTML Page |
| text/css | CSS File |
| application/json | JSON Data |
| image/png | PNG Image |
| application/pdf | PDF Document |

---

# Virtual Hosting

Virtual hosting enables a single web server to host multiple websites.

Types:

- Name-Based Virtual Hosting
- IP-Based Virtual Hosting

Benefits:

- Efficient resource usage
- Lower infrastructure costs
- Simplified management

---

# Web Server Directory Structure

Common directories may include:

- Document Root
- Configuration Files
- Log Files
- Temporary Files
- Upload Directory

Administrators should restrict access to sensitive directories.

---

# Logging

Important web server logs include:

- Access Log
- Error Log
- Authentication Log
- Audit Log

These logs support:

- Troubleshooting
- Incident Response
- Threat Hunting
- Digital Forensics

---

# Security Considerations

Organizations should:

- Use HTTPS instead of HTTP
- Configure strong TLS settings
- Disable unnecessary HTTP methods
- Protect session cookies
- Monitor server logs
- Apply regular security updates
- Implement secure authentication

---

# CEH Exam Tips

Remember:

- HTTP uses Port 80.
- HTTPS uses Port 443.
- HTTP is stateless.
- GET retrieves data.
- POST submits data.
- Cookies are stored on the client.
- Sessions are managed by the server.
- Status code 200 indicates success.
- Status code 404 indicates the requested resource was not found.
- Status code 500 indicates an internal server error.

---

# Key Takeaways

- HTTP and HTTPS are the foundation of web communication.
- HTTPS provides confidentiality, integrity, and authentication through TLS.
- Understanding HTTP methods, status codes, headers, cookies, and sessions is essential for web security analysis.
- Proper configuration and monitoring help secure web servers against common threats.

---

# Web Server Technologies

## Overview

A web server is responsible for receiving client requests, processing them, and delivering web content. Modern organizations use different web server software depending on their operating systems, performance requirements, and application stack.

The three most common web servers are:

- Apache HTTP Server
- Microsoft Internet Information Services (IIS)
- Nginx

---

# Apache HTTP Server

## Overview

Apache HTTP Server (Apache) is one of the world's most widely used open-source web servers. It is known for its flexibility, modular architecture, and cross-platform compatibility.

### Key Features

- Open source
- Cross-platform (Linux, Windows, macOS)
- Modular architecture
- Virtual Host support
- SSL/TLS support
- Extensive documentation

### Common Uses

- Hosting websites
- Web applications
- APIs
- Content management systems (WordPress, Drupal, Joomla)

---

# Apache Architecture

Basic request flow:

```
Client
   │
HTTP/HTTPS Request
   │
Apache Web Server
   │
Modules
   │
Application
   │
Database
```

Apache processes client requests using configurable modules and serves either static or dynamic content.

---

# Microsoft IIS

## Overview

Internet Information Services (IIS) is Microsoft's web server platform for Windows Server.

### Features

- Windows integration
- Active Directory support
- ASP.NET support
- PowerShell management
- SSL/TLS support
- Logging and monitoring

### Common Uses

- Enterprise applications
- Microsoft web services
- Internal business portals
- SharePoint
- Exchange-related web services

---

# Nginx

## Overview

Nginx is a lightweight, high-performance web server commonly used in cloud environments.

### Features

- High concurrency
- Reverse proxy
- Load balancing
- Low resource consumption
- Fast performance
- SSL/TLS support

### Common Uses

- High-traffic websites
- Cloud infrastructure
- Reverse proxy
- API gateway
- Containerized applications

---

# Reverse Proxy

## What is a Reverse Proxy?

A reverse proxy sits in front of one or more web servers and forwards client requests to the appropriate backend server.

```
Client
   │
Reverse Proxy
   │
-----------------------
│          │          │
Web 1    Web 2     Web 3
```

### Benefits

- Load balancing
- SSL termination
- Improved performance
- Enhanced security
- High availability

Common reverse proxy solutions include:

- Nginx
- Apache
- HAProxy

---

# Load Balancing

## Overview

Load balancing distributes incoming traffic across multiple servers to improve availability and performance.

### Benefits

- Increased reliability
- Improved scalability
- Better fault tolerance
- Reduced server overload

Common algorithms:

- Round Robin
- Least Connections
- IP Hash

---

# Virtual Hosts

Virtual hosting allows multiple websites to run on a single web server.

### Types

#### Name-Based Virtual Hosting

Multiple domains share one IP address.

Example:

- example1.com
- example2.com

#### IP-Based Virtual Hosting

Each website has its own dedicated IP address.

---

# Web Server Components

Typical web server environment includes:

- Web Server Software
- Operating System
- Web Application
- Database Server
- DNS
- SSL/TLS Certificates
- Log Files
- Configuration Files

Each component contributes to the overall security of the web server.

---

# Web Server Configuration Files

Configuration files define how a web server operates.

They may include:

- Listening ports
- Virtual hosts
- SSL/TLS settings
- Access control rules
- Logging configuration
- Directory permissions

Misconfigurations can expose systems to security risks.

---

# Web Server Logs

Important log files include:

## Access Log

Records client requests.

Useful for:

- Monitoring traffic
- Detecting unusual requests
- Investigating incidents

---

## Error Log

Records server-side errors.

Useful for:

- Troubleshooting
- Application debugging
- Security investigations

---

## Authentication Log

Records login events and authentication attempts.

Useful for:

- Detecting brute-force attempts
- Monitoring privileged access

---

# Web Server Enumeration

## Overview

Enumeration is the process of gathering information about a web server to understand its configuration and exposed services.

From a defensive perspective, administrators perform enumeration to identify unnecessary exposure and verify secure configurations.

Typical information that may be identified includes:

- Server software
- Server version
- Operating system
- Open ports
- Supported protocols
- Enabled services
- HTTP headers
- SSL/TLS configuration

This information helps defenders validate configurations and identify potential weaknesses before attackers do.

---

# Common Web Technologies

Web servers often work with additional technologies such as:

### Server-Side Languages

- PHP
- ASP.NET
- Java
- Python
- Node.js

### Databases

- MySQL
- PostgreSQL
- Microsoft SQL Server
- Oracle Database
- MongoDB

### Content Management Systems (CMS)

- WordPress
- Joomla
- Drupal

These technologies extend web server functionality and support dynamic web applications.

---

# Security Considerations

Administrators should:

- Remove unnecessary services
- Disable directory listing
- Keep software updated
- Protect configuration files
- Restrict administrative access
- Enable logging
- Use HTTPS
- Monitor server health
- Apply security patches regularly

---

# CEH Exam Tips

Remember:

- Apache is the most common open-source web server.
- IIS is Microsoft's web server platform.
- Nginx is widely used as a reverse proxy and load balancer.
- Reverse proxies sit between clients and backend servers.
- Load balancers distribute traffic across multiple servers.
- Web server logs are essential for troubleshooting and security monitoring.
- Enumeration helps identify exposed services and verify secure configurations.

---

# Key Takeaways

- Apache, IIS, and Nginx are the most widely used web servers.
- Reverse proxies and load balancers improve security, scalability, and availability.
- Configuration files and logs play a critical role in server administration and incident response.
- Regular monitoring, secure configuration, and timely patching are essential for maintaining a secure web server environment.

---

# Common Web Server Security Risks

## Overview

Web servers are frequently targeted because they are publicly accessible and often host critical applications and sensitive data.

Many successful attacks result from insecure configurations, outdated software, weak authentication, or poor security practices rather than flaws in the web server software itself.

Understanding these risks helps organizations improve their security posture and reduce the likelihood of compromise.

---

# Information Disclosure

## What is Information Disclosure?

Information disclosure occurs when a web server unintentionally exposes sensitive information to unauthorized users.

Examples include:

- Server version information
- Operating system details
- Software versions
- Internal IP addresses
- Backup files
- Configuration files
- Error messages
- Directory structures

### Risks

- Assists reconnaissance
- Helps attackers identify potential weaknesses
- May expose sensitive organizational information

### Defensive Measures

- Disable unnecessary server banners
- Use generic error pages
- Remove backup files from public directories
- Restrict access to configuration files
- Regularly review exposed content

---

# Directory Listing

## Overview

Directory listing occurs when a web server displays the contents of a directory instead of serving a default page.

Example:

```
/images/
/backup/
/uploads/
/documents/
```

### Risks

- Exposure of sensitive files
- Disclosure of internal project structure
- Leakage of confidential documents

### Defensive Measures

- Disable directory browsing
- Configure default index pages
- Restrict permissions
- Monitor web server logs

---

# Default Credentials

## Overview

Many applications and management interfaces are deployed with default usernames and passwords.

If administrators fail to change these credentials, unauthorized users may gain access.

### Best Practices

- Change default credentials immediately
- Enforce strong password policies
- Enable Multi-Factor Authentication (MFA)
- Review administrative accounts regularly

---

# Security Misconfiguration

## Overview

Security misconfiguration is one of the most common causes of web server compromise.

Examples include:

- Unnecessary services enabled
- Weak permissions
- Default settings
- Open administrative interfaces
- Debug mode enabled
- Improper access controls

### Best Practices

- Apply secure baseline configurations
- Remove unused services
- Disable unnecessary features
- Review configurations regularly
- Follow vendor hardening guides

---

# File Upload Risks

## Overview

Many web applications allow users to upload files.

Without proper validation and access controls, uploaded content may introduce security risks.

### Secure Practices

- Validate file types
- Enforce file size limits
- Store uploads outside the web root when possible
- Scan uploaded files with anti-malware solutions
- Restrict execute permissions on upload directories

---

# Web Shells (Concept)

## Overview

A web shell is a script or program that can provide unauthorized remote access through a web server.

Web shells are commonly associated with compromised systems and are often used for persistence after an initial breach.

### Defensive Measures

- Monitor file integrity
- Restrict upload functionality
- Keep applications updated
- Review server logs
- Use Endpoint Detection and Response (EDR)
- Deploy Web Application Firewalls (WAF)

---

# Directory Traversal (Concept)

## Overview

Directory traversal refers to attempts to access files or directories outside the intended web application structure.

### Potential Impact

- Access to sensitive files
- Disclosure of configuration data
- Exposure of application resources

### Defensive Measures

- Validate user input
- Restrict file system access
- Use least privilege permissions
- Perform secure path validation

---

# File Inclusion (Concept)

## Overview

Some web applications dynamically include files during execution.

Improper validation can introduce security risks.

Types include:

- Local File Inclusion (LFI)
- Remote File Inclusion (RFI)

### Defensive Measures

- Validate input
- Use allowlists
- Restrict file inclusion mechanisms
- Keep frameworks updated

---

# HTTP Security Headers

Security headers improve browser-side protection.

Common examples:

| Header | Purpose |
|---------|----------|
| Content-Security-Policy | Reduces content injection risks |
| X-Frame-Options | Protects against clickjacking |
| X-Content-Type-Options | Prevents MIME-type confusion |
| Referrer-Policy | Controls referrer information |
| Strict-Transport-Security (HSTS) | Enforces HTTPS usage |

---

# Logging and Monitoring

Continuous monitoring helps identify suspicious behavior.

Important logs include:

- Access Logs
- Error Logs
- Authentication Logs
- Reverse Proxy Logs
- Web Application Firewall Logs

Logs should be forwarded to a SIEM platform for centralized monitoring and correlation.

---

# Security Monitoring

Organizations should monitor for:

- Unusual login attempts
- Repeated authentication failures
- Unexpected HTTP methods
- Excessive error responses
- Access to restricted resources
- Large numbers of requests from a single source
- Unexpected file uploads
- Configuration changes

---

# Web Application Firewall (WAF)

A Web Application Firewall protects web applications by filtering and monitoring HTTP and HTTPS traffic.

### Benefits

- Blocks malicious requests
- Helps protect against common web attacks
- Reduces application exposure
- Provides additional logging and visibility

Common WAF solutions include:

- ModSecurity
- Cloudflare WAF
- AWS WAF
- Azure Web Application Firewall

---

# Security Best Practices

Organizations should:

- Keep web server software updated.
- Remove unused modules and services.
- Disable directory listing.
- Use HTTPS with strong TLS configurations.
- Implement strong authentication.
- Apply the Principle of Least Privilege.
- Enable centralized logging.
- Perform regular vulnerability assessments.
- Monitor web server logs continuously.
- Conduct periodic penetration testing.
- Maintain secure backups.
- Review configurations regularly.

---

# CEH Exam Tips

Remember:

- Misconfiguration is one of the most common causes of web server compromise.
- Information disclosure often assists reconnaissance.
- Directory listing should be disabled unless explicitly required.
- Default credentials should always be changed.
- Web shells provide unauthorized remote access after compromise.
- HTTP security headers improve browser-side security.
- Continuous monitoring and logging are essential for detecting suspicious activity.

---

# Key Takeaways

- Web servers should be securely configured, regularly updated, and continuously monitored.
- Strong authentication, secure configurations, and proper logging significantly reduce security risks.
- Defense-in-depth, combined with secure development and operational practices, provides the best protection for modern web servers.

---

# Web Server Hardening

## Overview

Web server hardening is the process of reducing the attack surface by securely configuring the server, removing unnecessary components, applying security updates, and implementing security controls.

A hardened web server is more resistant to attacks and easier to monitor and maintain.

---

# Objectives of Hardening

- Reduce the attack surface
- Prevent unauthorized access
- Protect sensitive information
- Improve system stability
- Meet security compliance requirements
- Support incident response

---

# Patch Management

Keeping software updated is one of the most effective security measures.

Regularly update:

- Operating System
- Web Server Software
- Application Frameworks
- Plugins and Extensions
- SSL/TLS Libraries

Benefits:

- Fixes security vulnerabilities
- Improves stability
- Enhances performance

---

# Remove Unnecessary Components

Disable or uninstall:

- Unused services
- Unused modules
- Sample applications
- Default web pages
- Test scripts
- Unused user accounts

Reducing unnecessary components minimizes potential attack vectors.

---

# Secure Configuration

Key configuration practices:

- Disable directory listing
- Use secure file permissions
- Protect configuration files
- Disable unnecessary HTTP methods
- Configure secure error pages
- Restrict administrative interfaces
- Enable HTTPS by default

---

# Access Control

Restrict access based on the Principle of Least Privilege.

Examples:

- Limit administrator accounts
- Restrict remote administration
- Use role-based access control (RBAC)
- Enforce Multi-Factor Authentication (MFA)

---

# TLS and Certificate Management

Use valid SSL/TLS certificates to secure communication.

Best practices:

- Use strong TLS versions
- Disable deprecated protocols
- Renew certificates before expiration
- Protect private keys
- Redirect HTTP traffic to HTTPS

---

# Logging

Logging is essential for troubleshooting, auditing, and detecting suspicious activity.

Common logs:

- Access Logs
- Error Logs
- Authentication Logs
- Audit Logs
- Application Logs

Logs should be retained according to organizational policies.

---

# Log Monitoring

Security teams should monitor logs for:

- Failed login attempts
- Unauthorized access
- Unexpected administrative actions
- Configuration changes
- High request volumes
- Repeated client errors
- Suspicious user agents

---

# Centralized Logging

Organizations often collect logs from multiple systems into a central platform.

Benefits:

- Simplified monitoring
- Event correlation
- Faster investigations
- Compliance reporting
- Long-term log retention

Common SIEM platforms:

- Splunk
- Microsoft Sentinel
- IBM QRadar
- Elastic Security

---

# File Integrity Monitoring (FIM)

File Integrity Monitoring detects unauthorized changes to important files.

Typical targets:

- Configuration files
- Web application files
- System binaries
- Security policies

Benefits:

- Detects tampering
- Supports incident response
- Helps identify persistence mechanisms

---

# Backup and Recovery

Maintain regular backups of:

- Website files
- Databases
- Configuration files
- SSL/TLS certificates

Backup best practices:

- Test restoration procedures
- Encrypt backup data
- Store backups securely
- Keep offline or immutable copies

---

# Incident Response

If a web server is suspected of being compromised:

1. Identify the incident.
2. Contain affected systems.
3. Preserve logs and evidence.
4. Investigate the root cause.
5. Remove malicious artifacts.
6. Recover services from trusted backups if necessary.
7. Monitor for recurring activity.
8. Document lessons learned.

---

# Secure Administration

Administrative interfaces should be protected by:

- Strong passwords
- Multi-Factor Authentication
- Restricted network access
- Secure remote management
- Regular account reviews

Administrative access should never be exposed unnecessarily to the public Internet.

---

# Continuous Monitoring

Continuous monitoring helps identify security issues early.

Monitor:

- System performance
- Service availability
- Authentication events
- Network traffic
- Security alerts
- File changes
- Configuration changes

---

# Defense-in-Depth

Web server security should use multiple layers of protection.

Example:

```
Internet
    │
Firewall
    │
Web Application Firewall (WAF)
    │
Reverse Proxy
    │
Web Server
    │
Application
    │
Database
    │
Logging / SIEM
    │
SOC Team
```

Each layer contributes to the overall security posture.

---

# Security Best Practices Checklist

- Keep software updated.
- Remove unused components.
- Disable unnecessary services.
- Enforce HTTPS.
- Implement strong authentication.
- Apply the Principle of Least Privilege.
- Enable centralized logging.
- Monitor logs continuously.
- Perform regular vulnerability assessments.
- Conduct periodic penetration testing.
- Maintain tested backups.
- Review configurations regularly.

---

# CEH Exam Tips

Remember:

- Patch management reduces known vulnerabilities.
- Hardening minimizes the attack surface.
- Centralized logging improves visibility.
- File Integrity Monitoring detects unauthorized file changes.
- Defense-in-depth combines multiple security controls.
- Regular backups support business continuity and incident recovery.

---

# Key Takeaways

- Hardening is an ongoing process rather than a one-time task.
- Secure configuration, timely patching, access control, and monitoring significantly improve web server security.
- Effective logging and incident response enable organizations to detect, investigate, and recover from security events efficiently.

---

# Security Best Practices

A secure web server requires multiple layers of protection. Security should be implemented throughout the server lifecycle—from deployment and configuration to monitoring and maintenance.

## Web Server Security Checklist

- Keep the operating system updated.
- Keep web server software up to date.
- Remove unnecessary services and modules.
- Disable directory listing.
- Configure secure file permissions.
- Enforce HTTPS using modern TLS versions.
- Use valid SSL/TLS certificates.
- Enable Multi-Factor Authentication (MFA) for administrative accounts.
- Apply the Principle of Least Privilege.
- Protect configuration files.
- Restrict administrative interfaces.
- Enable centralized logging.
- Monitor logs continuously.
- Perform regular vulnerability assessments.
- Conduct periodic penetration testing.
- Maintain tested backups.
- Review configurations regularly.

---

# Web Server Security Layers

Modern organizations protect web servers using multiple security technologies.

```
Internet
     │
Firewall
     │
Web Application Firewall (WAF)
     │
Reverse Proxy
     │
Web Server
     │
Application Server
     │
Database
     │
SIEM
     │
SOC Team
```

Each layer helps reduce risk and improve detection capabilities.

---

# MITRE ATT&CK Mapping

The concepts covered in this module relate to several MITRE ATT&CK tactics.

| ATT&CK Tactic | Description |
|--------------|-------------|
| TA0001 | Initial Access |
| TA0002 | Execution |
| TA0003 | Persistence |
| TA0005 | Defense Evasion |
| TA0007 | Discovery |
| TA0009 | Collection |
| TA0010 | Exfiltration |
| TA0011 | Command and Control |

Understanding these tactics helps defenders map observed behaviors to known adversary techniques and improve detection strategies.

---

# Detection Opportunities

Security teams should monitor for:

- Unusual HTTP requests
- Excessive failed authentication attempts
- Unexpected file uploads
- Access to restricted directories
- Abnormal HTTP methods
- High request volumes
- Repeated client or server errors
- Configuration changes
- Unexpected outbound connections
- Suspicious administrative activity

Logs from web servers, WAFs, reverse proxies, and operating systems should be correlated in a SIEM for effective monitoring.

---

# Common Security Tools

## Web Server Assessment

- Nmap
- Nikto
- WhatWeb
- Gobuster
- Curl
- OpenSSL

## Network Analysis

- Wireshark
- tcpdump

## Web Security Testing

- Burp Suite
- OWASP ZAP

## Monitoring

- Wazuh
- Splunk
- Microsoft Sentinel
- Elastic Security

---

# Key Terminology

| Term | Definition |
|------|------------|
| Web Server | Software that delivers web content over HTTP/HTTPS. |
| HTTP | Hypertext Transfer Protocol. |
| HTTPS | Secure version of HTTP using TLS encryption. |
| Reverse Proxy | Forwards client requests to backend servers. |
| Load Balancer | Distributes traffic across multiple servers. |
| Virtual Host | Hosts multiple websites on a single server. |
| WAF | Web Application Firewall that filters HTTP/HTTPS traffic. |
| SIEM | Platform for centralized log collection and analysis. |
| FIM | File Integrity Monitoring to detect unauthorized file changes. |

---

# CEH Exam Revision

Remember:

- HTTP uses Port **80**.
- HTTPS uses Port **443**.
- Apache, IIS, and Nginx are the most common web servers.
- Reverse proxies improve scalability and security.
- Load balancers distribute client requests.
- Directory listing should generally be disabled.
- Strong TLS configurations improve confidentiality and integrity.
- Logs are essential for monitoring and incident response.
- Defense-in-depth provides stronger protection than a single security control.

---

# Interview Tips

Be prepared to explain:

- HTTP vs HTTPS
- Apache vs IIS vs Nginx
- Reverse Proxy vs Load Balancer
- Static vs Dynamic websites
- Common web server security risks
- Importance of patch management
- Role of Web Application Firewalls (WAF)
- Importance of centralized logging
- Principle of Least Privilege
- File Integrity Monitoring (FIM)
- Defense-in-depth
- MITRE ATT&CK mapping

---

# Module Summary

This module introduced the fundamentals of web server technologies and their role in modern IT infrastructure.

Topics covered include:

- Web server architecture
- HTTP and HTTPS
- Apache, IIS, and Nginx
- Reverse proxies and load balancing
- Web server security risks
- Hardening techniques
- Logging and monitoring
- Incident response
- MITRE ATT&CK mapping
- Security best practices

These concepts form a strong foundation for careers in:

- SOC Analyst
- Security Analyst
- VAPT Analyst
- Penetration Tester
- Incident Responder
- Web Security Analyst

---

# Final Takeaways

- Web servers are high-value targets and must be securely configured.
- Regular patching, hardening, and monitoring significantly reduce risk.
- Logging, SIEM integration, and continuous monitoring improve threat detection and response.
- Layered security—including firewalls, WAFs, reverse proxies, and secure administration—is essential for protecting web infrastructure.
- Understanding both web server technologies and defensive security practices prepares cybersecurity professionals for real-world environments and CEH certification.
