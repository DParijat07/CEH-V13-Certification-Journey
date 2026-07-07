# Tools and Commands

## Overview

Session Hijacking assessments primarily focus on analyzing HTTP requests, cookies, authentication tokens, and web sessions. Security professionals use a combination of interception proxies, browser developer tools, packet analyzers, and command-line utilities to identify insecure session management.

> **Note:** All tools and techniques described below should only be used in authorized environments such as labs, CTFs, or approved penetration testing engagements.

---

# Burp Suite

Burp Suite is one of the most widely used web application security testing tools.

## Common Modules

| Module | Purpose |
|---------|---------|
| Proxy | Intercept HTTP/HTTPS requests |
| Repeater | Modify and resend requests |
| Intruder | Automated request testing |
| Decoder | Encode and decode data |
| Comparer | Compare responses |
| Logger | View captured traffic |

---

## Intercept Requests

Intercept requests between browser and server.

Example:

```
Browser
      ↓
Burp Proxy
      ↓
Target Server
```

Useful for:

- Viewing cookies
- Viewing headers
- Session analysis
- Authentication testing

---

## Repeater

Allows manual modification of requests.

Common Uses

- Replay authenticated requests
- Modify cookies
- Change HTTP methods
- Test authorization

---

## Intruder

Used for automated testing.

Examples

- Username enumeration
- Password testing (authorized labs only)
- Session token analysis
- Fuzzing parameters

---

# Browser Developer Tools

Modern browsers provide built-in tools for inspecting web applications.

Open:

```
F12
```

or

```
Ctrl + Shift + I
```

---

## Network Tab

Displays

- HTTP Requests
- HTTP Responses
- Headers
- Cookies
- Status Codes
- Response Time

---

## Application Tab

Useful for viewing

- Cookies
- Local Storage
- Session Storage
- IndexedDB

---

## Security Tab

Displays

- TLS version
- HTTPS status
- Certificate information

---

## Console

Useful for testing JavaScript.

Example

```
document.cookie
```

> Modern browsers will not display cookies marked with the **HttpOnly** attribute.

---

# Wireshark

Wireshark is a packet analysis tool used to inspect network traffic.

Common Filters

HTTP Traffic

```
http
```

HTTPS Traffic

```
tls
```

DNS

```
dns
```

TCP

```
tcp
```

ICMP

```
icmp
```

Follow HTTP Stream

```
Right Click
↓

Follow

↓

HTTP Stream
```

---

# OWASP ZAP

Open-source web application security testing tool.

Useful Features

- Intercept Proxy
- Passive Scanner
- Active Scanner
- Spider
- Fuzzer
- Automation

---

# cURL

Command-line tool for interacting with web servers.

## View HTTP Headers

```bash
curl -I https://example.com
```

---

## View Full Response

```bash
curl -v https://example.com
```

---

## Follow Redirects

```bash
curl -L https://example.com
```

---

## Send Custom Header

```bash
curl -H "User-Agent: Mozilla/5.0" https://example.com
```

---

## Send Cookie

```bash
curl --cookie "SESSIONID=ABC123" https://example.com
```

---

## Save Cookies

```bash
curl -c cookies.txt https://example.com
```

---

## Use Saved Cookies

```bash
curl -b cookies.txt https://example.com
```

---

# Browser Cookie Manager

Browsers allow inspection of stored cookies.

Information Available

- Cookie Name
- Value
- Domain
- Path
- Expiration
- Secure Flag
- HttpOnly
- SameSite

---

# OpenSSL

Inspect HTTPS certificates.

```bash
openssl s_client -connect example.com:443
```

Useful for

- TLS validation
- Certificate inspection
- Cipher information

---

# Nmap

Although Nmap is not a session hijacking tool, it helps identify web services before testing.

Basic Scan

```bash
nmap <target-ip>
```

Service Detection

```bash
nmap -sV <target-ip>
```

HTTP Scripts

```bash
nmap --script http* <target-ip>
```

---

# Useful HTTP Response Headers

```
Set-Cookie

Cookie

Authorization

Location

Server

Content-Type

Cache-Control

Strict-Transport-Security
```

---

# Important Cookie Attributes

```
Secure
```

Cookie only sent over HTTPS.

---

```
HttpOnly
```

Prevents JavaScript from accessing cookies.

---

```
SameSite
```

Helps mitigate CSRF attacks.

Values

- Strict
- Lax
- None

---

# Useful HTTP Status Codes

| Code | Meaning |
|------|---------|
| 200 | OK |
| 201 | Created |
| 301 | Permanent Redirect |
| 302 | Temporary Redirect |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Internal Server Error |

---

# Common Testing Checklist

- Inspect cookies after login.
- Verify Secure flag.
- Verify HttpOnly flag.
- Verify SameSite attribute.
- Check if Session ID changes after login.
- Test logout behavior.
- Review HTTP response headers.
- Confirm HTTPS enforcement.
- Observe session timeout.

---

# CEH Exam Tips

Remember:

- **Burp Suite** is the primary web application testing tool.
- **Browser Developer Tools** are useful for inspecting cookies and storage.
- **Wireshark** captures network traffic.
- **OWASP ZAP** is an open-source alternative to Burp Suite.
- **curl** is useful for interacting with web servers and testing cookies.
- Cookies marked **HttpOnly** cannot be accessed via JavaScript.
- Cookies marked **Secure** are transmitted only over HTTPS.

---

# Key Takeaways

- Burp Suite is the most important tool for session management testing.
- Browser Developer Tools help inspect cookies and client-side storage.
- Wireshark enables network-level traffic analysis.
- curl is useful for testing HTTP requests and cookie behavior.
- Understanding these tools is essential for both CEH practicals and real-world web application assessments.
