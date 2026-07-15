# MITRE ATT&CK Mapping – Wireless Network Security

## Overview

The MITRE ATT&CK Framework is a globally recognized knowledge base that documents adversary tactics and techniques observed during real-world cyber attacks.

While wireless technologies (Wi-Fi, IEEE 802.11, WPA3, etc.) are not individual ATT&CK techniques, attacks against wireless environments often align with multiple ATT&CK tactics.

This document maps common wireless security concepts to relevant ATT&CK tactics and highlights detection and defensive opportunities for Blue Teams.

---

# MITRE ATT&CK Tactics

| ATT&CK Tactic | Relevance to Wireless Security |
|---------------|--------------------------------|
| Initial Access | Gaining unauthorized access to wireless networks or connected systems |
| Discovery | Identifying wireless devices, access points, SSIDs, and network information |
| Credential Access | Obtaining wireless authentication credentials |
| Collection | Capturing network traffic or sensitive information after access |
| Defense Evasion | Attempting to avoid wireless monitoring or security controls |
| Impact | Disrupting wireless availability or communication |

---

# Relevant ATT&CK Techniques

| Technique | ATT&CK ID | Example Relevance |
|-----------|-----------|------------------|
| Valid Accounts | T1078 | Use of compromised wireless or enterprise credentials |
| Network Sniffing | T1040 | Capturing network traffic where protections are inadequate |
| Exploit Public-Facing Application | T1190 | Exploitation of exposed wireless management interfaces |
| Data from Information Repositories | T1213 | Accessing sensitive information after network access |
| Endpoint Denial of Service | T1499 | Disrupting wireless services or client connectivity |

> **Note:** MITRE ATT&CK focuses on adversary behavior. Wireless protocols such as WPA3, IEEE 802.11, and RADIUS are security technologies, not ATT&CK techniques.

---

# Defensive Security Controls

Organizations should implement:

- WPA3 authentication
- IEEE 802.1X
- RADIUS authentication
- Protected Management Frames (PMF)
- Network Access Control (NAC)
- Network segmentation
- Wireless IDS/IPS (WIDS/WIPS)
- Continuous monitoring
- Firmware updates
- Security awareness training

---

# Blue Team Detection Opportunities

Security teams should monitor for:

- Rogue Access Points
- Unknown SSIDs
- Unauthorized wireless devices
- Authentication failures
- Unexpected client associations
- Excessive client disconnects
- Wireless controller configuration changes
- RF interference
- Abnormal wireless traffic
- Failed RADIUS authentications

---

# SIEM Use Cases

Security Information and Event Management (SIEM) platforms can generate alerts for:

- Rogue AP detection
- Authentication anomalies
- Excessive failed logins
- RADIUS failures
- Configuration changes
- New wireless devices
- Client association anomalies
- Unexpected administrator activity
- Wireless infrastructure health alerts

Common SIEM platforms include:

- Splunk
- Microsoft Sentinel
- IBM QRadar
- Elastic Security
- Wazuh

---

# Threat Hunting Opportunities

Threat hunters should investigate:

- Unknown Access Points
- Unexpected SSIDs
- Unauthorized MAC addresses
- Authentication spikes
- Client roaming anomalies
- RF interference
- Firmware changes
- Rogue wireless controllers
- Wireless configuration drift

---

# Incident Response Considerations

If suspicious wireless activity is detected:

1. Identify affected devices and infrastructure.
2. Preserve logs and evidence.
3. Contain unauthorized access.
4. Investigate authentication records.
5. Remove rogue devices if confirmed.
6. Update configurations or credentials.
7. Monitor for recurring activity.
8. Document lessons learned.

---

# Wireless Security Monitoring Checklist

Regularly review:

- Access Point status
- Wireless controller logs
- RADIUS authentication logs
- NAC events
- WIDS/WIPS alerts
- SIEM dashboards
- Firmware versions
- Client inventories
- Wireless policy compliance

---

# CEH Exam Tips

Remember:

- MITRE ATT&CK describes attacker behavior, not security products.
- Wireless attacks commonly relate to Initial Access, Discovery, Credential Access, Collection, Defense Evasion, and Impact.
- SIEM platforms improve centralized visibility into wireless events.
- WIDS detects suspicious activity, while WIPS helps prevent or contain threats.
- Continuous monitoring and threat hunting improve wireless security.

---

# Key Takeaways

- Wireless attacks can be mapped to multiple MITRE ATT&CK tactics even though Wi-Fi technologies themselves are not ATT&CK techniques.
- Effective wireless defense combines strong authentication, modern encryption, centralized monitoring, and proactive threat hunting.
- Organizations should continuously monitor wireless infrastructure, integrate logs with SIEM platforms, and investigate anomalies to strengthen their security posture.
