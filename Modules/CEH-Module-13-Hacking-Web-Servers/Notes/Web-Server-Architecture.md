# Web Server Architecture

## Overview

A web server is responsible for receiving client requests, processing them, and delivering web content over HTTP or HTTPS.

Web server architecture defines how clients, servers, applications, and databases interact to provide web services securely and efficiently.

---

# Basic Architecture

```
             Internet
                 │
                 ▼
          Web Browser
                 │
          HTTP / HTTPS
                 │
                 ▼
          Web Server
                 │
        Application Layer
                 │
                 ▼
          Database Server
```

---

# Components of Web Server Architecture

## 1. Client

The client initiates communication with the web server.

Examples:

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Safari

Responsibilities:

- Send HTTP requests
- Receive HTTP responses
- Render web pages

---

## 2. DNS Server

The Domain Name System (DNS) translates domain names into IP addresses.

Example:

```
www.example.com
        │
        ▼
93.184.216.34
```

Without DNS, users would need to remember IP addresses instead of domain names.

---

## 3. Web Server

The web server processes incoming requests and serves web content.

Popular web servers:

- Apache HTTP Server
- Nginx
- Microsoft IIS
- LiteSpeed

Responsibilities:

- Serve static content
- Process dynamic requests
- Manage HTTP connections
- Handle SSL/TLS
- Generate logs

---

## 4. Application Server

The application server executes business logic.

Examples:

- PHP
- ASP.NET
- Java (Tomcat)
- Node.js
- Python (Flask, Django)

Functions:

- Process user requests
- Authenticate users
- Communicate with databases
- Generate dynamic content

---

## 5. Database Server

Stores application data.

Examples:

- MySQL
- PostgreSQL
- Microsoft SQL Server
- Oracle Database
- MongoDB

Typical data stored:

- User accounts
- Orders
- Products
- Application settings
- Logs

---

# Request–Response Lifecycle

```
User
 │
 ▼
Browser
 │
 ▼
DNS Lookup
 │
 ▼
Web Server
 │
 ▼
Application
 │
 ▼
Database
 │
 ▼
Application
 │
 ▼
Web Server
 │
 ▼
Browser
 │
 ▼
User
```

---

# Static Website Architecture

```
Browser
    │
HTTP Request
    │
    ▼
Web Server
    │
HTML
CSS
JavaScript
Images
    │
    ▼
Browser
```

Characteristics:

- Fast
- Simple
- No database
- Same content for every user

---

# Dynamic Website Architecture

```
Browser
     │
HTTP Request
     │
     ▼
Web Server
     │
Application
     │
Database
     │
Application
     │
Web Server
     │
HTTP Response
     │
Browser
```

Characteristics:

- Database-driven
- User authentication
- Personalized content
- Interactive applications

---

# Reverse Proxy Architecture

```
Client
    │
    ▼
Reverse Proxy
    │
───────────────
│      │      │
Web1  Web2  Web3
```

Benefits:

- Load balancing
- SSL termination
- Improved security
- High availability

---

# Load Balancer Architecture

```
Users
    │
    ▼
Load Balancer
───────────────
│      │      │
Server1 Server2 Server3
```

Benefits:

- High availability
- Better performance
- Fault tolerance
- Scalability

---

# Virtual Hosting

Virtual hosting allows multiple websites to run on one server.

### Name-Based Virtual Hosting

```
IP Address

│

├── example.com

├── company.com

└── school.edu
```

### IP-Based Virtual Hosting

Each website uses its own IP address.

---

# Web Server Ports

| Port | Service |
|------|----------|
| 80 | HTTP |
| 443 | HTTPS |
| 8080 | HTTP Alternate |
| 8443 | HTTPS Alternate |

---

# Common Web Server Software

## Apache

- Open source
- Linux
- Modular

---

## IIS

- Microsoft
- Windows
- ASP.NET

---

## Nginx

- High performance
- Reverse proxy
- Load balancer

---

# Logging

Common logs:

- Access Log
- Error Log
- Authentication Log
- Audit Log

Logs support:

- Incident Response
- Threat Hunting
- Troubleshooting
- Digital Forensics

---

# Security Considerations

Organizations should:

- Use HTTPS
- Keep software updated
- Disable unnecessary services
- Protect configuration files
- Monitor logs
- Apply least privilege
- Enable centralized logging
- Deploy Web Application Firewalls (WAF)

---

# CEH Exam Tips

Remember:

- DNS resolves domain names.
- Web servers process HTTP requests.
- Application servers execute business logic.
- Databases store application data.
- Reverse proxies improve security.
- Load balancers improve availability.
- Ports 80 and 443 are standard web ports.

---

# Key Takeaways

- Web server architecture consists of multiple interconnected components.
- Understanding request–response flow is fundamental to web security.
- Secure architecture, monitoring, and layered defenses improve the security and availability of web services.
