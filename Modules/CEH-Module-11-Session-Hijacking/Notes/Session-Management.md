# Session Management

## Overview

Session Management is the process of securely creating, maintaining, validating, and terminating a user's authenticated session within a web application.

Since HTTP is a stateless protocol, session management enables web applications to remember users between multiple requests.

Poor session management is one of the leading causes of account compromise and is included in the OWASP Top 10 under **Identification and Authentication Failures**.

---

# Why Session Management is Needed

HTTP treats every request independently.

Without session management:

- Users would need to log in for every page request.
- Shopping carts would not work.
- Online banking sessions could not be maintained.
- User preferences would be lost.

Session management allows a web server to associate multiple HTTP requests with a single authenticated user.

---

# Session Lifecycle

```
User Opens Website
        │
        ▼
Login Page
        │
        ▼
User Authenticates
        │
        ▼
Server Validates Credentials
        │
        ▼
Session Created
        │
        ▼
Unique Session ID Generated
        │
        ▼
Session Cookie Sent
        │
        ▼
Browser Stores Cookie
        │
        ▼
Browser Sends Cookie with Every Request
        │
        ▼
Server Validates Session
        │
        ▼
User Access Granted
        │
        ▼
Logout / Session Timeout
        │
        ▼
Session Destroyed
```

---

# Authentication vs Authorization vs Session

| Authentication | Authorization | Session |
|----------------|--------------|----------|
| Verifies identity | Determines permissions | Maintains authenticated state |
| Username + Password | User Roles | Session ID / Token |
| Happens once | Happens after login | Continues until logout or timeout |

---

# Session ID

A Session ID is a unique identifier assigned to every authenticated user.

Example:

```
PHPSESSID=12ab98cd45ef67
```

Properties of a Secure Session ID

- Random
- Unique
- Long
- Unpredictable
- Cryptographically Secure

---

# Session Storage

Sessions may be stored in:

## Server Side

- RAM
- Database
- Redis
- Memcached
- File System

Advantages

- More secure
- Easy to invalidate
- Recommended

---

## Client Side

Commonly stored as:

- Cookies
- JWT Tokens
- Local Storage
- Session Storage

---

# Cookies

A cookie stores information in the browser.

Example

```
Set-Cookie:

PHPSESSID=ABC123XYZ
```

The browser automatically sends the cookie with every request.

---

# Types of Cookies

## Session Cookie

- Temporary
- Deleted when browser closes

---

## Persistent Cookie

- Remains after browser closes
- Has expiration time

---

## Secure Cookie

- Sent only over HTTPS

---

## HttpOnly Cookie

- Cannot be accessed by JavaScript

Protects against XSS cookie theft.

---

## SameSite Cookie

Helps prevent CSRF attacks.

Values

- Strict
- Lax
- None

---

# JSON Web Token (JWT)

Modern applications often use JWT instead of traditional session IDs.

Structure

```
Header

Payload

Signature
```

Example

```
xxxxx.yyyyy.zzzzz
```

Advantages

- Stateless
- API Friendly
- Scalable

Disadvantages

- Difficult to revoke
- Must expire quickly

---

# Session Timeout

Session timeout automatically logs users out after inactivity.

Types

### Idle Timeout

User inactive.

Example

```
15 minutes
```

---

### Absolute Timeout

Session expires regardless of activity.

Example

```
8 hours
```

---

# Session Expiration

Sessions should expire:

- After logout
- After timeout
- Password reset
- Account lock
- Privilege change

---

# Session Regeneration

The server should generate a new Session ID:

- After login
- After privilege escalation
- After password reset

Purpose

Prevent Session Fixation attacks.

---

# Secure Session Management

## Recommended Practices

✔ Use HTTPS

✔ Enable HSTS

✔ Regenerate Session IDs

✔ Use Random Session IDs

✔ Secure Cookie Flag

✔ HttpOnly

✔ SameSite

✔ MFA

✔ Device Validation

✔ IP Monitoring

✔ Logout Invalidates Session

✔ Short Session Lifetime

✔ Continuous Monitoring

---

# Common Session Management Vulnerabilities

- Predictable Session IDs
- Session Fixation
- Session Hijacking
- Session Replay
- Long Session Timeout
- Session ID in URL
- Cookies without Secure Flag
- Missing HttpOnly
- Missing SameSite
- No Session Expiration

---

# Session Management in Different Technologies

| Technology | Default Session Cookie |
|------------|------------------------|
| PHP | PHPSESSID |
| Java | JSESSIONID |
| ASP.NET | ASP.NET_SessionId |
| Django | sessionid |
| Flask | session |
| Node.js | connect.sid |

---

# Session Management Testing

During a VAPT assessment, verify:

- Session ID randomness
- Cookie attributes
- HTTPS enforcement
- Session timeout
- Logout functionality
- Session regeneration
- Cookie security
- Token expiration
- JWT validation
- Concurrent session handling

---

# Tools Used

## Burp Suite

- Proxy
- Repeater
- Intruder

---

## Browser Developer Tools

- Application
- Storage
- Cookies
- Network

---

## OWASP ZAP

- Passive Scan
- Active Scan

---

## Wireshark

Inspect HTTP and HTTPS traffic.

---

# Best Practices Checklist

- HTTPS enabled
- Secure Cookies enabled
- HttpOnly enabled
- SameSite configured
- Session regenerated after login
- Session expires on logout
- Short timeout configured
- MFA enabled
- Device/IP monitoring enabled
- Logging enabled

---

# CEH Exam Tips

Remember:

- HTTP is stateless.
- Sessions maintain authentication.
- Cookies usually store Session IDs.
- JWT is widely used in modern web applications.
- Session IDs should never appear in URLs.
- Secure, HttpOnly, and SameSite are essential cookie attributes.
- Session regeneration prevents Session Fixation.
- Short session lifetimes reduce hijacking risk.

---

# Key Takeaways

- Session management is fundamental to web application security.
- Secure session handling prevents unauthorized access.
- Cookies and tokens must be protected throughout their lifecycle.
- Proper timeout, regeneration, encryption, and monitoring significantly reduce the risk of session hijacking.
