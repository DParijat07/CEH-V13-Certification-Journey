# CEH v13 – Module 11: Session Hijacking

## Overview

Session Hijacking is an attack where an attacker gains unauthorized access to a user's active session by stealing or manipulating session identifiers (cookies or tokens). Instead of stealing credentials, the attacker abuses an already authenticated session.

This module covers the concepts, techniques, tools, defenses, and practical labs related to session hijacking in modern web applications.

---

# Learning Objectives

After completing this module, I can:

- Understand HTTP session management.
- Explain session cookies and authentication tokens.
- Perform session enumeration in a controlled lab.
- Identify common session hijacking techniques.
- Analyze cookies using browser developer tools.
- Use Burp Suite for session analysis.
- Understand Session Fixation attacks.
- Understand Session Sidejacking.
- Recommend secure session management practices.
- Map attacks to MITRE ATT&CK.
- Write professional VAPT reports.

---

# Module Contents

| File | Description |
|------|-------------|
| Module-11-Complete-Notes.md | Complete CEH study notes |
| Session-Hijacking-CheatSheet.md | Quick revision sheet |
| Attack-Techniques.md | Session hijacking attack methods |
| Session-Management.md | Cookies, Tokens, Sessions |
| Tools-and-Commands.md | Burp Suite, Browser DevTools, OWASP ZAP |
| Countermeasures.md | Defensive techniques |
| MITRE-ATTACK-Mapping.md | MITRE ATT&CK mapping |
| Detection-and-IOC.md | Indicators of Compromise |
| SOC-Analyst-Notes.md | Detection from SOC perspective |
| Interview-Questions.md | Interview preparation |
| Resources.md | References |

---

# Practical Labs

## TryHackMe

- Burp Suite: The Basics
- Walking An Application
- OWASP Top 10
- Juice Shop (Recommended)

---

## Home Lab

- DVWA
- OWASP Juice Shop
- Burp Suite Community
- Firefox Developer Tools
- Kali Linux

---

# Tools Covered

- Burp Suite
- Browser Developer Tools
- Firefox
- Chrome DevTools
- Wireshark
- OWASP ZAP
- cURL

---

# CEH Topics Covered

- Session Management
- Session Hijacking
- Session Fixation
- Session Sidejacking
- Cookie Poisoning
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- Token-based Authentication
- Secure Cookies

---

# MITRE ATT&CK

Primary Tactics:

- Credential Access
- Collection

Related Techniques:

- Session Cookie Theft
- Web Session Abuse
- Browser Session Hijacking

---

# Skills Gained

- Cookie analysis
- HTTP request analysis
- Burp Suite interception
- Session token inspection
- Browser security testing
- Session vulnerability assessment
- Professional reporting

---

# Deliverables

- Complete Notes
- Cheat Sheets
- Lab Notes
- TryHackMe Write-ups
- Professional VAPT Report
- IOC Documentation
- MITRE Mapping
- Screenshots

---

# Status

- [ ] Theory Complete
- [ ] Practical Labs Complete
- [ ] TryHackMe Rooms Complete
- [ ] GitHub Documentation Complete
- [ ] VAPT Report Complete
