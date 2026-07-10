# HTTP and HTTPS Fundamentals

## Overview

HTTP (Hypertext Transfer Protocol) and HTTPS (Hypertext Transfer Protocol Secure) are the primary protocols used for communication between web browsers and web servers.

Understanding these protocols is essential for web security, web application testing, incident response, and network analysis.

---

# What is HTTP?

HTTP is an **Application Layer (Layer 7)** protocol in the OSI Model used to transfer web resources over the Internet.

Characteristics:

- Stateless protocol
- Client–Server communication
- Request–Response model
- Plaintext communication
- Default Port: **80**

HTTP is suitable for general web communication but does **not** provide encryption.

---

# What is HTTPS?

HTTPS is the secure version of HTTP.

It combines:

- HTTP
- SSL/TLS encryption

Default Port:

**443**

HTTPS protects data exchanged between clients and servers.

---

# Why HTTPS is Important

HTTPS provides three core security properties:

## Confidentiality

Encrypts communication so that unauthorized parties cannot read transmitted data.

---

## Integrity

Ensures that transmitted data has not been modified during transit.

---

## Authentication

Verifies the identity of the web server using a digital certificate issued by a trusted Certificate Authority (CA).

---

# HTTP vs HTTPS

| Feature | HTTP | HTTPS |
|----------|-------|--------|
| Default Port | 80 | 443 |
| Encryption | No | Yes |
| Confidentiality | No | Yes |
| Integrity | No | Yes |
| Authentication | No | Yes |
| Performance | Slightly Faster | Slightly More Overhead |
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

---

# HTTP Request Structure

A request typically contains:

- Request Line
- HTTP Method
- URL
- Headers
- Cookies
- Optional Body

Example:

```
GET /index.html HTTP/1.1
Host: example.com
User-Agent: Mozilla/5.0
```

---

# HTTP Response Structure

A response contains:

- Status Line
- Status Code
- Headers
- Response Body

Example:

```
HTTP/1.1 200 OK
Content-Type: text/html
Server: Apache
```

---

# HTTP Methods

| Method | Purpose |
|----------|----------|
| GET | Retrieve resources |
| POST | Submit data |
| PUT | Update resources |
| PATCH | Partially update resources |
| DELETE | Remove resources |
| HEAD | Retrieve headers only |
| OPTIONS | Show supported methods |

---

# Common HTTP Status Codes

## 1xx – Informational

- 100 Continue

---

## 2xx – Success

- 200 OK
- 201 Created
- 204 No Content

---

## 3xx – Redirection

- 301 Moved Permanently
- 302 Found
- 304 Not Modified

---

## 4xx – Client Errors

- 400 Bad Request
- 401 Unauthorized
- 403 Forbidden
- 404 Not Found
- 405 Method Not Allowed

---

## 5xx – Server Errors

- 500 Internal Server Error
- 502 Bad Gateway
- 503 Service Unavailable
- 504 Gateway Timeout

---

# URL Components

Example:

```
https://www.example.com:443/products/index.php?id=25
```

| Component | Example |
|-----------|----------|
| Protocol | https |
| Domain | www.example.com |
| Port | 443 |
| Path | /products/ |
| File | index.php |
| Parameter | id=25 |

---

# HTTP Headers

Headers provide additional information about requests and responses.

### Common Request Headers

- Host
- User-Agent
- Accept
- Authorization
- Cookie
- Referer

### Common Response Headers

- Server
- Content-Type
- Content-Length
- Set-Cookie
- Cache-Control
- Location

---

# Cookies

Cookies are small pieces of information stored by the browser.

Uses:

- Session management
- Authentication
- Personalization
- User preferences

Types:

- Session Cookies
- Persistent Cookies
- Secure Cookies
- HttpOnly Cookies

---

# Sessions

A session maintains a user's authenticated state across multiple HTTP requests.

Typical workflow:

```
User Login
      │
Server Creates Session
      │
Session ID Generated
      │
Browser Stores Cookie
      │
Future Requests Include Session ID
```

---

# MIME Types

MIME types identify the type of content being transmitted.

Examples:

| MIME Type | Description |
|------------|-------------|
| text/html | HTML |
| text/css | CSS |
| application/json | JSON |
| image/png | PNG Image |
| application/pdf | PDF |

---

# SSL/TLS Certificates

Digital certificates are used to authenticate web servers.

Certificates contain:

- Domain Name
- Public Key
- Certificate Authority
- Expiration Date
- Digital Signature

---

# Certificate Authority (CA)

A Certificate Authority issues and verifies digital certificates.

Examples:

- DigiCert
- GlobalSign
- Let's Encrypt
- Sectigo

---

# HTTPS Handshake (Simplified)

```
Browser
     │
Request Secure Connection
     │
     ▼
Server
     │
Sends Certificate
     │
Browser Verifies Certificate
     │
Encryption Keys Established
     │
Secure Communication Begins
```

---

# Security Best Practices

Organizations should:

- Enforce HTTPS
- Disable outdated SSL/TLS versions
- Use strong cipher suites
- Enable HSTS
- Protect cookies using Secure and HttpOnly flags
- Renew certificates before expiration
- Redirect HTTP traffic to HTTPS

---

# CEH Exam Tips

Remember:

- HTTP uses Port **80**.
- HTTPS uses Port **443**.
- HTTP is **not encrypted**.
- HTTPS uses **TLS** for encryption.
- Cookies are stored by the browser.
- Sessions are managed by the server.
- Status code **200** indicates success.
- Status code **404** indicates the requested resource was not found.
- Status code **500** indicates an internal server error.

---

# Interview Questions

### What is the difference between HTTP and HTTPS?

HTTP transmits data in plaintext, while HTTPS encrypts communication using TLS to provide confidentiality, integrity, and authentication.

---

### Why is HTTPS preferred?

HTTPS protects sensitive information from interception and tampering, making it the standard for secure web communication.

---

### What is a session?

A session allows a web application to remember a user across multiple HTTP requests after authentication.

---

### What is the purpose of cookies?

Cookies store information on the client to support session management, authentication, and user preferences.

---

# Key Takeaways

- HTTP and HTTPS are the foundation of web communication.
- HTTPS uses TLS to secure data in transit.
- Understanding requests, responses, headers, cookies, sessions, and status codes is essential for web security.
- Secure configuration of HTTPS and proper certificate management significantly improve the security of web applications.
