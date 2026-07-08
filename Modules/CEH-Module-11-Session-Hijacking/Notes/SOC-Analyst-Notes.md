# SOC Analyst Notes

## CEH Module 11 – Session Hijacking

---

# Overview

A Security Operations Center (SOC) Analyst is responsible for continuously monitoring, detecting, investigating, and responding to cyber threats. Session hijacking is a common web application attack that SOC analysts must identify through authentication logs, user behavior, and network activity.

Unlike password attacks, session hijacking often uses a **valid authenticated session**, making behavioral analysis more important than signature-based detection.

---

# SOC Objectives

When investigating session hijacking, the SOC analyst should:

- Detect suspicious authentication activity.
- Monitor session usage.
- Investigate abnormal user behavior.
- Identify compromised accounts.
- Contain the incident.
- Preserve forensic evidence.
- Coordinate incident response.

---

# Attack Lifecycle

```
User Authentication
        │
        ▼
Session Created
        │
        ▼
Attacker Obtains Session Cookie
        │
        ▼
Cookie Reused
        │
        ▼
Unauthorized Access
        │
        ▼
Privilege Abuse
        │
        ▼
Data Theft
```

---

# Detection Sources

A SOC analyst should monitor data from multiple sources.

## Authentication Logs

Monitor:

- Successful logins
- Failed logins
- Login time
- Login location
- Login device

Examples

- Windows Event Logs
- Linux Authentication Logs
- Active Directory
- Azure AD
- Okta

---

## Web Server Logs

Useful servers

- Apache
- Nginx
- IIS

Look for

- Repeated Session IDs
- Unauthorized requests
- HTTP status codes
- Session duration
- Cookie usage

---

## Firewall Logs

Monitor

- External IP addresses
- Blocked traffic
- Allowed traffic
- Geographic locations

---

## VPN Logs

Review

- Login country
- Public IP address
- VPN connection time
- Device information

---

## Proxy Logs

Useful for

- Website access
- User activity
- File downloads
- Suspicious browsing

---

## EDR Logs

Examples

- Microsoft Defender
- CrowdStrike
- SentinelOne
- Elastic Agent

Monitor

- Browser malware
- Suspicious processes
- Browser extensions
- Credential theft

---

# Indicators of Suspicious Activity

## Impossible Travel

Example

```
09:00

India

↓

09:15

United Kingdom
```

---

## Concurrent Sessions

Example

```
Laptop

Mobile

Unknown Device
```

---

## Session Reuse

Session remains active after logout.

---

## User-Agent Changes

```
Chrome

↓

Firefox
```

during the same session.

---

## New Device

Known Device

↓

Unknown Device

---

## Long Session Duration

Example

```
36 Hours
```

Active session without expiration.

---

## Authentication Without Login

Authenticated requests appear without a recent login event.

---

# Investigation Workflow

```
Alert Generated
        │
        ▼
Validate Alert
        │
        ▼
Identify User
        │
        ▼
Review Authentication Logs
        │
        ▼
Review Session Activity
        │
        ▼
Review IP Address
        │
        ▼
Review Device
        │
        ▼
Determine Impact
        │
        ▼
Contain Incident
        │
        ▼
Document Findings
```

---

# Containment Actions

If session hijacking is confirmed:

- Terminate active sessions
- Invalidate session cookies
- Revoke authentication tokens
- Reset user password
- Require MFA
- Block malicious IP addresses
- Isolate infected endpoint (if necessary)

---

# SIEM Use Cases

Examples

## Rule 1

```
Same Session ID

AND

Different Country
```

Generate

High Severity Alert

---

## Rule 2

```
Session Active

AFTER Logout
```

Generate

Critical Alert

---

## Rule 3

```
Same Account

Multiple Public IPs

Within 10 Minutes
```

Generate

Medium/High Alert

---

## Rule 4

```
User-Agent Changes

During Active Session
```

Generate

Investigation Alert

---

# MITRE ATT&CK Mapping

| ATT&CK Technique | Description |
|------------------|-------------|
| T1539 | Steal Web Session Cookie |
| T1557 | Adversary-in-the-Middle |
| T1078 | Valid Accounts |
| T1190 | Exploit Public-Facing Application |

---

# Common SOC Tools

## SIEM

- Splunk
- Microsoft Sentinel
- Elastic Security
- QRadar

---

## Packet Analysis

- Wireshark
- tcpdump

---

## Endpoint Security

- Microsoft Defender
- CrowdStrike
- SentinelOne

---

## Web Security

- Burp Suite
- OWASP ZAP

---

## Threat Intelligence

- VirusTotal
- AlienVault OTX
- AbuseIPDB
- Cisco Talos

---

# Incident Response Process

```
Preparation

↓

Detection

↓

Analysis

↓

Containment

↓

Eradication

↓

Recovery

↓

Lessons Learned
```

---

# Best Practices

- Enforce HTTPS
- Enable HSTS
- Configure Secure cookies
- Enable HttpOnly
- Configure SameSite
- Regenerate Session IDs after login
- Implement MFA
- Monitor authentication logs
- Detect impossible travel
- Limit session lifetime
- Enable centralized logging

---

# Interview Questions

### What is Session Hijacking?

Taking over an authenticated user's active session by stealing or manipulating the session identifier.

---

### How would a SOC analyst detect Session Hijacking?

By analyzing authentication logs, session activity, IP addresses, User-Agent strings, device information, and behavioral anomalies.

---

### Which logs are most useful?

- Authentication Logs
- Web Server Logs
- Firewall Logs
- VPN Logs
- SIEM Alerts
- EDR Logs

---

### Which MITRE ATT&CK technique is most closely related?

**T1539 – Steal Web Session Cookie**

---

# CEH Exam Notes

Remember:

- HTTP is stateless.
- Sessions maintain authentication.
- Secure cookies protect data in transit.
- HttpOnly helps prevent JavaScript cookie theft.
- SameSite reduces CSRF attacks.
- Session regeneration prevents Session Fixation.
- SOC analysts detect session hijacking through behavioral anomalies rather than passwords alone.

---

# Key Takeaways

- Session hijacking is both a web application security issue and a SOC monitoring challenge.
- Effective detection requires correlating authentication logs, session behavior, IP addresses, devices, and network activity.
- SOC analysts should combine SIEM alerts, endpoint telemetry, and web server logs to identify and respond to unauthorized session usage quickly.
