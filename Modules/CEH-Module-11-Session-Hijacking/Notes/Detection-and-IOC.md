# Detection and IOC (Indicators of Compromise)

## Overview

Session Hijacking attacks often leave detectable traces in authentication logs, web server logs, network traffic, and endpoint telemetry. Security analysts monitor these Indicators of Compromise (IOCs) to identify unauthorized session usage and respond before significant damage occurs.

Unlike password attacks, session hijacking usually involves the abuse of an already authenticated session, making behavioral monitoring essential.

---

# What is an IOC?

An **Indicator of Compromise (IOC)** is evidence that suggests a system, user account, or network may have been compromised.

Examples include:

- Suspicious IP addresses
- Malicious domains
- Stolen session cookies
- Unusual login behavior
- Unexpected User-Agent changes
- Authentication anomalies

---

# Common Indicators of Session Hijacking

## 1. Multiple IP Addresses Using the Same Session

### Description

The same Session ID appears from different IP addresses.

Example

```
Session ID: A8F12B

10:05 AM → India

10:08 AM → Germany
```

### Risk

High

### Detection

- Authentication Logs
- SIEM
- Web Server Logs

---

## 2. Impossible Travel

### Description

A user appears to log in from two geographically distant locations within an impossible timeframe.

Example

```
09:00 → Kolkata

09:20 → New York
```

### Risk

Very High

### Detection

- Identity Provider
- Microsoft Sentinel
- Splunk
- SIEM Correlation Rules

---

## 3. User-Agent Change

### Description

The browser fingerprint changes during the same authenticated session.

Example

```
Chrome

↓

Firefox
```

or

```
Windows

↓

Linux
```

### Possible Cause

- Session Hijacking
- Browser Emulation
- Automated Tools

---

## 4. Concurrent Sessions

### Description

Multiple active sessions use the same account simultaneously.

Example

```
Laptop

Desktop

Mobile

Unknown Device
```

### Detection

Authentication Logs

---

## 5. Session Reuse After Logout

### Description

A session continues to be used after the legitimate user has logged out.

### Risk

Critical

### Possible Cause

- Server failed to destroy session
- Session cookie stolen

---

## 6. Long-Lived Sessions

### Description

Sessions remain active for an unusually long period.

Example

```
Session Duration

12 Hours

24 Hours

3 Days
```

### Risk

High

---

## 7. Multiple Failed Requests Followed by Success

Possible indicator of

- Authentication abuse
- Session replay
- Automated attack

---

## 8. New Device Access

Example

```
Previous Device

Windows Laptop

↓

Current Device

Unknown Linux VM
```

May indicate

- Session Theft
- Account Takeover

---

## 9. Authentication Without Login Event

The server receives authenticated requests even though no successful login occurred recently.

Possible Causes

- Cookie Replay
- Session Replay
- Token Theft

---

## 10. Access Outside Normal Hours

Example

```
Normal Login

09:00–18:00

Observed Login

03:15 AM
```

May indicate

- Compromised Session
- Insider Threat
- Malware

---

# Network Indicators

Monitor

- New external IP
- Suspicious VPN
- Proxy usage
- TOR exit nodes
- Repeated HTTP requests
- Abnormal TLS behavior

---

# Browser Indicators

- Unexpected cookies
- Missing Secure flag
- Missing HttpOnly
- Unexpected Local Storage
- Unknown browser extensions

---

# Web Server Indicators

Review

- Apache Logs
- Nginx Logs
- IIS Logs

Look for

- Repeated Session IDs
- Same Session from different IPs
- Frequent 302 redirects
- Authentication anomalies

---

# Endpoint Indicators

Monitor

- Browser malware
- Infostealers
- Suspicious extensions
- Credential dumping
- Memory scraping

Useful Tools

- Microsoft Defender
- CrowdStrike
- SentinelOne
- Elastic Agent

---

# Log Sources

| Log Source | Purpose |
|------------|---------|
| Authentication Logs | Login events |
| Web Server Logs | Session activity |
| Firewall Logs | Network connections |
| VPN Logs | Remote access |
| Proxy Logs | Web requests |
| DNS Logs | Domain lookups |
| EDR Logs | Endpoint activity |
| SIEM | Correlation and alerting |

---

# Detection Logic Examples

Example 1

```
IF

Same Session ID

AND

Different Country

THEN

Generate High Severity Alert
```

---

Example 2

```
IF

User-Agent Changes

AND

IP Changes

THEN

Possible Session Hijacking
```

---

Example 3

```
IF

Session Used

AFTER Logout

THEN

Critical Alert
```

---

# IOC Summary Table

| IOC | Severity |
|------|----------|
| Same Session ID from Multiple IPs | High |
| Impossible Travel | Critical |
| Session Reuse After Logout | Critical |
| User-Agent Change | Medium |
| Long Session Duration | Medium |
| Concurrent Sessions | High |
| New Device Login | Medium |
| Authentication Without Login | High |
| Access Outside Working Hours | Medium |
| Browser Cookie Theft | Critical |

---

# Incident Response Steps

1. Identify suspicious session.
2. Verify user activity.
3. Terminate affected sessions.
4. Force password reset.
5. Revoke authentication tokens.
6. Investigate logs.
7. Block malicious IP addresses.
8. Notify the user.
9. Enable MFA (if not already enabled).
10. Document the incident.

---

# CEH Exam Tips

Remember:

- Session Hijacking is often detected through behavioral anomalies rather than malware signatures.
- Impossible travel is a common indicator of account compromise.
- Concurrent sessions may indicate unauthorized access.
- Authentication logs are one of the most valuable sources during investigations.
- SIEM solutions help correlate multiple indicators into a single high-confidence alert.

---

# Key Takeaways

- Session hijacking detection relies on monitoring user behavior, session activity, and authentication events.
- A single IOC may not confirm an attack, but multiple correlated indicators significantly increase confidence.
- SOC analysts use SIEM, EDR, web server logs, and network telemetry to detect and investigate session hijacking attempts.
