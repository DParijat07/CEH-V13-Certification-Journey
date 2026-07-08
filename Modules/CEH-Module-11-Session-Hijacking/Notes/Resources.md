# Resources

## Overview

This document contains official documentation, learning platforms, labs, cheat sheets, and books for mastering **CEH Module 11 – Session Hijacking**.

Use these resources to strengthen both theoretical knowledge and practical skills.

---

# Official References

## OWASP

Website:
https://owasp.org/

Useful Resources

- OWASP Top 10
- OWASP Web Security Testing Guide (WSTG)
- OWASP Cheat Sheet Series
- OWASP Session Management Cheat Sheet
- OWASP Authentication Cheat Sheet
- OWASP Transport Layer Security Cheat Sheet

---

## MITRE ATT&CK

Website

https://attack.mitre.org/

Useful Techniques

- T1539 – Steal Web Session Cookie
- T1557 – Adversary-in-the-Middle
- T1078 – Valid Accounts
- T1190 – Exploit Public-Facing Application

---

## PortSwigger Web Security Academy

Website

https://portswigger.net/web-security

Recommended Topics

- HTTP Basics
- Authentication
- Session Management
- Access Control
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- JWT
- OAuth
- Web Cache Poisoning

Recommended Labs

- Authentication Labs
- Session Management Labs
- XSS Labs
- CSRF Labs
- Access Control Labs

---

## Mozilla Developer Network (MDN)

Website

https://developer.mozilla.org/

Recommended Topics

- HTTP
- Cookies
- HTTP Headers
- Authentication
- SameSite Cookies
- Secure Cookies
- HttpOnly
- Web Storage API

---

## NIST

Website

https://www.nist.gov/

Useful Publications

- NIST Cybersecurity Framework (CSF)
- SP 800-61 Incident Response
- SP 800-53 Security Controls
- SP 800-63 Digital Identity Guidelines

---

# CEH Study Resources

EC-Council Official Courseware

Focus Topics

- Session Hijacking
- Web Application Security
- Authentication
- Cookies
- HTTP Protocol
- HTTPS
- MITM Attacks

---

# Practical Labs

## TryHackMe

Recommended Rooms

- HTTP in Detail
- OWASP Top 10
- Burp Suite: Repeater
- Burp Suite: Intruder
- Web Fundamentals
- Search Skills
- Blue
- Ice
- Mr Robot CTF
- Basic Pentesting

---

## PortSwigger Academy Labs

Recommended Order

1. Authentication
2. Session Management
3. Access Control
4. XSS
5. CSRF
6. JWT
7. OAuth

---

## DVWA (Damn Vulnerable Web Application)

Practice

- Authentication
- Session Management
- XSS
- CSRF
- File Inclusion

---

## OWASP Juice Shop

Practice

- Broken Authentication
- Session Handling
- JWT
- XSS
- CSRF

---

## Metasploitable 2

Useful for

- Enumeration
- Web Services
- Authentication
- Vulnerability Assessment

---

# Browser Tools

## Google Chrome DevTools

Useful Tabs

- Network
- Application
- Security
- Storage

---

## Firefox Developer Tools

Useful For

- Cookies
- HTTP Headers
- JavaScript
- Storage

---

# Security Tools

## Burp Suite

Modules

- Proxy
- Repeater
- Intruder
- Decoder
- Comparer

---

## OWASP ZAP

Features

- Proxy
- Spider
- Active Scan
- Passive Scan
- Fuzzer

---

## Wireshark

Useful Filters

```
http
```

```
tls
```

```
tcp
```

```
dns
```

---

## curl

Useful Commands

```bash
curl -I https://example.com
```

```bash
curl -v https://example.com
```

```bash
curl -c cookies.txt https://example.com
```

```bash
curl -b cookies.txt https://example.com
```

---

# Linux Commands

View Manual

```bash
man curl
```

Check OpenSSL Version

```bash
openssl version
```

Display HTTP Headers

```bash
curl -I https://example.com
```

---

# Books

## Web Application Hacker's Handbook

Authors

- Dafydd Stuttard
- Marcus Pinto

---

## The Tangled Web

Author

- Michal Zalewski

---

## Hacking: The Art of Exploitation

Author

- Jon Erickson

---

## Real-World Bug Hunting

Author

- Peter Yaworski

---

## Black Hat Python

Author

- Justin Seitz

---

# SOC Learning Resources

Microsoft Learn

Topics

- Microsoft Sentinel
- Defender XDR
- Incident Response

---

Splunk Education

Topics

- SIEM
- Log Analysis
- Threat Detection

---

Elastic Training

Topics

- Elastic Security
- Kibana
- Detection Rules

---

# Threat Intelligence

Useful Platforms

- VirusTotal
- AlienVault OTX
- AbuseIPDB
- Cisco Talos
- GreyNoise
- URLScan.io

---

# GitHub Repositories

Recommended Search Topics

- Burp Suite Extensions
- OWASP Cheat Sheets
- HTTP Security
- Session Management
- JWT Security
- Web Security Labs

---

# Blogs

Recommended Reading

- PortSwigger Blog
- Google Project Zero
- Microsoft Security Blog
- Cloudflare Blog
- OWASP Blog
- Krebs on Security

---

# YouTube Channels

- John Hammond
- The Cyber Mentor
- LiveOverflow
- IppSec
- NetworkChuck
- David Bombal

---

# Practice Checklist

Complete the following before the CEH exam:

- Understand HTTP and HTTPS.
- Learn how sessions work.
- Understand cookies and session IDs.
- Study Secure, HttpOnly, and SameSite attributes.
- Practice with Burp Suite.
- Complete PortSwigger Session Management labs.
- Complete relevant TryHackMe rooms.
- Practice Wireshark packet analysis.
- Learn MITRE ATT&CK mappings.
- Review OWASP Session Management Cheat Sheet.
- Revise interview questions.
- Build GitHub documentation.

---

# Career Mapping

This module builds practical knowledge for roles such as:

- SOC Analyst (L1/L2)
- Security Analyst
- Vulnerability Assessment Analyst
- Penetration Tester
- Application Security Analyst
- Web Security Tester
- Incident Response Analyst
- Security Consultant

---

# Key Takeaways

- Official documentation should always be the primary learning source.
- Hands-on practice is essential for understanding session management and web security.
- Combining CEH theory with practical labs (TryHackMe, PortSwigger, DVWA, Juice Shop) provides strong preparation for certifications, interviews, and real-world cybersecurity roles.
