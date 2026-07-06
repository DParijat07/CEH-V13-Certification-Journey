# Session Hijacking Cheat Sheet

## Definition

Session Hijacking is the process of taking over a legitimate user's authenticated session by stealing or manipulating the session identifier (Session ID, Cookie, or Authentication Token).

---

# HTTP Session Flow

```
User Login
      │
      ▼
Server Authenticates User
      │
      ▼
Creates Session
      │
      ▼
Generates Session ID
      │
      ▼
Stores Session ID in Cookie
      │
      ▼
Browser Sends Cookie with Every Request
      │
      ▼
Server Verifies Session
      │
      ▼
Access Granted
```

---

# Why Sessions Exist

HTTP is a **stateless protocol**.

Without sessions:

- Login required on every request
- No user tracking
- Poor user experience

Sessions allow servers to remember authenticated users.

---

# Common Session Cookies

| Technology | Cookie Name |
|------------|-------------|
| PHP | PHPSESSID |
| Java | JSESSIONID |
| ASP.NET | ASP.NET_SessionId |
| Django | sessionid |
| Flask | session |
| Node.js | connect.sid |

---

# Types of Session Hijacking

## Session Sniffing

- Capture cookies over the network
- Requires insecure communication (HTTP)

---

## Session Sidejacking

- Intercept authentication cookies
- Common on public Wi-Fi

---

## Session Fixation

Attacker forces victim to use a known Session ID before login.

---

## Cookie Theft

Methods:

- XSS
- Malware
- Browser extensions
- Physical access

---

## Session Replay

Replay previously captured session tokens.

---

## Man-in-the-Middle (MITM)

Attacker intercepts communication between client and server.

---

# Common Attack Methods

- Cross-Site Scripting (XSS)
- Packet Sniffing
- ARP Spoofing
- Evil Twin Wi-Fi
- Session Replay
- Browser Malware
- Rogue Browser Extensions

---

# Session Token Locations

- Cookies
- URL Parameters (deprecated)
- Hidden Form Fields
- HTTP Headers
- JWT Tokens
- Bearer Tokens

---

# Cookie Security Attributes

## Secure

✔ Cookie only sent over HTTPS

---

## HttpOnly

✔ JavaScript cannot access cookie

Protects against:

- XSS Cookie Theft

---

## SameSite

Protects against:

- Cross-Site Request Forgery (CSRF)

Modes

- Strict
- Lax
- None

---

# Tools

## Burp Suite

- Proxy
- Repeater
- Intruder
- Decoder

---

## Browser Developer Tools

- Application
- Storage
- Cookies
- Network

---

## Wireshark

Capture

- HTTP
- HTTPS
- TCP
- DNS

---

## OWASP ZAP

- Proxy
- Active Scan
- Passive Scan

---

# Indicators of Session Hijacking

- Same Session ID from multiple IPs
- Same Session from different countries
- Impossible travel
- User-Agent changes
- Multiple devices using same session
- Session active after logout
- Excessively long session duration

---

# Detection Sources

- Web Server Logs
- Firewall Logs
- Proxy Logs
- SIEM
- IDS/IPS
- Authentication Logs

---

# MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Credential Access | Steal Web Session Cookie |
| Credential Access | Valid Accounts |
| Collection | Browser Session Data |
| Initial Access | Exploit Public-Facing Application |
| Credential Access | Adversary-in-the-Middle |

---

# Countermeasures

✅ HTTPS Everywhere

✅ HSTS

✅ Secure Cookies

✅ HttpOnly Cookies

✅ SameSite Cookies

✅ Multi-Factor Authentication (MFA)

✅ Short Session Timeout

✅ Regenerate Session IDs after Login

✅ Logout Invalidates Session

✅ IP & Device Validation

✅ Continuous Session Monitoring

---

# CEH Exam Quick Facts

✔ HTTP is stateless.

✔ Sessions maintain authentication.

✔ Cookies usually store Session IDs.

✔ Session IDs should be random and unpredictable.

✔ XSS can steal cookies.

✔ HTTPS encrypts session traffic.

✔ Secure attribute protects cookies during transmission.

✔ HttpOnly prevents JavaScript access.

✔ SameSite helps prevent CSRF.

✔ Session Fixation uses an attacker-controlled Session ID.

✔ Session Sidejacking captures cookies over insecure networks.

---

# Interview Questions

### What is Session Hijacking?

Taking control of a legitimate user's authenticated session by stealing or manipulating the session identifier.

---

### Difference between Authentication and Session?

Authentication verifies identity.

Session maintains that authenticated state.

---

### Difference between Session Fixation and Session Hijacking?

- **Session Hijacking:** Attacker steals an existing session.
- **Session Fixation:** Attacker forces the victim to use a session chosen by the attacker.

---

### Which cookie attribute prevents JavaScript from reading cookies?

**HttpOnly**

---

### Which cookie attribute forces cookies to be sent only over HTTPS?

**Secure**

---

### Which cookie attribute helps mitigate CSRF?

**SameSite**

---

# One-Line Revision

**Authenticate → Create Session → Generate Session ID → Store Cookie → Validate Session → Secure Cookie → Monitor Sessions**
