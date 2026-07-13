# MITRE ATT&CK Mapping – SQL Injection

## Overview

SQL Injection (SQLi) is one of the most common web application vulnerabilities. While SQL Injection itself is **not a MITRE ATT&CK technique**, attackers may use it as an **initial access vector** or as a method to achieve objectives that map to multiple ATT&CK tactics and techniques.

Understanding this mapping helps security teams improve detection, monitoring, threat hunting, and incident response.

---

# ATT&CK Tactics Related to SQL Injection

| ATT&CK Tactic | Description |
|--------------|-------------|
| Initial Access | Exploiting vulnerable web applications to gain unauthorized access. |
| Discovery | Gathering information about databases, schemas, users, or application structure. |
| Credential Access | Accessing authentication data stored in databases. |
| Collection | Retrieving sensitive business or customer information. |
| Exfiltration | Transferring stolen data outside the organization. |
| Defense Evasion | Attempting to bypass logging, monitoring, or security controls. |

---

# Common ATT&CK Techniques

| Technique | ATT&CK ID | Relevance |
|-----------|-----------|-----------|
| Exploit Public-Facing Application | T1190 | Exploiting vulnerable web applications exposed to the Internet. |
| Data from Information Repositories | T1213 | Accessing sensitive information stored in databases or repositories. |
| Data from Local System | T1005 | Collecting locally stored application or database data after access is obtained. |
| Exfiltration Over Web Service | T1567 | Exfiltrating stolen information through web-based services or applications. |
| Valid Accounts | T1078 | Misusing compromised database or application credentials. |

> **Note:** SQL Injection is a vulnerability, while the ATT&CK framework documents adversary behaviors after or during exploitation.

---

# Blue Team Detection Opportunities

Monitor for:

- Repeated database query failures
- Unusual SQL query patterns
- Unexpected database errors
- Authentication anomalies
- Excessive failed login attempts
- Large database exports
- Sudden increases in database activity
- Unexpected privilege changes
- Suspicious outbound network traffic
- High-frequency requests to web application endpoints

---

# SIEM Use Cases

Security Information and Event Management (SIEM) solutions can generate alerts for:

- Multiple failed login attempts
- Repeated database errors
- Abnormal database query volumes
- Privilege escalation events
- Unauthorized database access
- Large data transfers
- Unexpected administrator activity
- Database configuration changes

Common SIEM platforms include:

- Splunk
- Microsoft Sentinel
- IBM QRadar
- Elastic Security
- Wazuh

---

# Defensive Security Controls

Recommended controls include:

- Parameterized queries
- Prepared statements
- Input validation
- Principle of Least Privilege (PoLP)
- Secure error handling
- Database hardening
- Database Activity Monitoring (DAM)
- Web Application Firewall (WAF)
- Patch management
- Centralized logging
- Continuous security testing

---

# Threat Hunting Indicators

Threat hunters should investigate:

- Unusual application behavior
- Unexpected SQL errors
- Large data retrieval operations
- Database performance anomalies
- Excessive authentication failures
- Unusual administrator actions
- Unexpected outbound connections from database servers
- Repeated requests targeting login or search functionality

---

# Incident Response Recommendations

If SQL Injection activity is suspected:

1. Identify affected applications.
2. Preserve application and database logs.
3. Contain unauthorized access.
4. Review database permissions.
5. Patch the vulnerable application.
6. Reset exposed credentials if necessary.
7. Validate data integrity.
8. Monitor for continued suspicious activity.
9. Conduct a post-incident review.

---

# CEH Exam Tips

Remember:

- SQL Injection is **not itself** an ATT&CK technique.
- SQL Injection commonly maps to **Initial Access** activities.
- T1190 (Exploit Public-Facing Application) is the most relevant ATT&CK technique.
- Blue Teams should focus on logging, monitoring, and anomaly detection.
- SIEM, WAF, and Database Activity Monitoring improve visibility and response.

---

# Key Takeaways

- SQL Injection is a web application vulnerability that can enable multiple stages of an attack.
- MITRE ATT&CK helps defenders understand the behaviors that may follow exploitation.
- Layered security controls, continuous monitoring, and proactive threat hunting are essential for detecting and mitigating SQL Injection-related activity.
