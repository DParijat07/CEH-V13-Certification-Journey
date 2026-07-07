# MITRE ATT&CK Mapping – CEH Module 11: Session Hijacking

## Overview

The MITRE ATT&CK Framework is a globally recognized knowledge base of adversary tactics and techniques based on real-world observations. Session hijacking activities span multiple ATT&CK tactics because attackers may steal, reuse, or abuse authenticated sessions after gaining initial access.

This document maps CEH Module 11 concepts to the relevant MITRE ATT&CK tactics and techniques.

---

# ATT&CK Tactics Covered

| Tactic | ATT&CK ID | Purpose |
|---------|-----------|---------|
| Initial Access | TA0001 | Gain initial foothold |
| Credential Access | TA0006 | Steal authentication material |
| Collection | TA0009 | Collect sensitive information |
| Defense Evasion | TA0005 | Avoid detection |
| Persistence | TA0003 | Maintain access |
| Lateral Movement | TA0008 | Move between systems |

---

# Technique Mapping

## 1. Steal Web Session Cookie

**Technique ID:** T1539

### Description

Adversaries steal web session cookies from browsers or memory to impersonate authenticated users without needing their passwords.

### CEH Topics

- Session Hijacking
- Cookie Theft
- Session Sidejacking

### Common Methods

- XSS
- Malware
- Browser Memory
- Packet Sniffing
- Browser Extensions

### Detection

- Same cookie used from multiple IPs
- Session reuse after logout
- Impossible travel
- Device fingerprint mismatch

### Mitigation

- Secure Cookies
- HttpOnly
- HTTPS
- MFA
- Short session lifetime

---

# 2. Adversary-in-the-Middle

**Technique ID:** T1557

### Description

The attacker positions themselves between the victim and server to intercept or modify traffic.

### CEH Topics

- Session Sidejacking
- MITM
- Packet Sniffing

### Examples

- ARP Spoofing
- Evil Twin Wi-Fi
- DNS Spoofing
- Rogue Access Point

### Detection

- Certificate warnings
- Unexpected ARP changes
- Duplicate MAC addresses
- TLS anomalies

### Mitigation

- HTTPS
- VPN
- Certificate validation
- HSTS

---

# 3. Valid Accounts

**Technique ID:** T1078

### Description

Attackers abuse valid authenticated sessions or legitimate credentials to access systems.

### CEH Topics

- Session Hijacking
- Authentication
- Session Replay

### Detection

- Concurrent logins
- Impossible travel
- New device logins
- Privilege misuse

### Mitigation

- MFA
- Conditional Access
- Device trust
- Continuous authentication

---

# 4. Browser Session Abuse

### Description

Attackers exploit browser-stored authentication tokens or cookies to impersonate users.

### CEH Topics

- Browser Cookies
- Session Tokens
- JWT
- Browser Storage

### Common Sources

- Chrome
- Firefox
- Edge

### Mitigation

- Browser hardening
- Endpoint protection
- Secure cookie attributes

---

# 5. Exploit Public-Facing Application

**Technique ID:** T1190

### Description

Attackers exploit web application vulnerabilities that may ultimately lead to session compromise.

### Related Vulnerabilities

- Cross-Site Scripting (XSS)
- Authentication flaws
- Session fixation
- Insecure cookies

### Mitigation

- Secure coding
- Input validation
- Output encoding
- WAF

---

# 6. Input Capture

**Technique ID:** T1056

### Description

Malware captures user input before it reaches the application.

### Examples

- Keyloggers
- Browser malware

### Relationship to Session Hijacking

Captured credentials may be used to create new authenticated sessions or steal active ones.

---

# Attack Chain Example

```
Initial Access

↓

Exploit Web Application

↓

Victim Logs In

↓

Attacker Steals Session Cookie

↓

Cookie Imported

↓

Account Hijacked

↓

Privilege Abuse

↓

Data Exfiltration
```

---

# Detection Opportunities

SOC analysts should monitor for:

- Multiple IP addresses using the same Session ID
- Impossible travel events
- Concurrent logins
- User-Agent changes during an active session
- Long-lived sessions
- Session reuse after logout
- Repeated failed authentication followed by success
- Unexpected geographic locations

---

# Log Sources

Useful logs include:

- Web Server Logs (Apache, Nginx, IIS)
- Authentication Logs
- Identity Provider Logs
- Firewall Logs
- Proxy Logs
- VPN Logs
- Endpoint Detection and Response (EDR)
- SIEM Platforms (Splunk, Elastic, Microsoft Sentinel)

---

# Defensive Controls

| Control | Purpose |
|----------|---------|
| HTTPS | Encrypt session traffic |
| HSTS | Force HTTPS |
| Secure Cookies | Protect cookies in transit |
| HttpOnly | Prevent JavaScript cookie access |
| SameSite | Reduce CSRF risk |
| Session Regeneration | Prevent session fixation |
| Session Timeout | Limit exposure |
| MFA | Strengthen authentication |
| Device Validation | Detect anomalous access |
| Continuous Monitoring | Identify session abuse |

---

# CEH Module Mapping

| CEH Topic | MITRE ATT&CK Technique |
|-----------|------------------------|
| Session Hijacking | T1539 – Steal Web Session Cookie |
| Session Sidejacking | T1557 – Adversary-in-the-Middle |
| Cookie Theft | T1539 – Steal Web Session Cookie |
| Session Replay | T1078 – Valid Accounts |
| XSS-based Cookie Theft | T1190 + T1539 |
| Browser Session Abuse | T1539 |
| Authentication Abuse | T1078 |

---

# Blue Team Perspective

During investigations, analysts should ask:

- Was the session cookie stolen?
- Is the session being reused from another location?
- Has the User-Agent changed?
- Was MFA bypassed?
- Was the session regenerated after login?
- Did the user log out before the suspicious activity?
- Are multiple devices using the same session?

---

# Key Takeaways

- Session hijacking aligns closely with **Credential Access** in the MITRE ATT&CK Framework.
- **T1539 (Steal Web Session Cookie)** is the primary technique associated with this module.
- Defenders should monitor authentication logs, session activity, IP addresses, and device characteristics to detect suspicious behavior.
- Mapping CEH concepts to MITRE ATT&CK helps standardize communication between penetration testers, SOC analysts, and incident responders.
