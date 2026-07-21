# MITRE ATT&CK Mapping – Cloud Computing

## Overview

The **MITRE ATT&CK® Enterprise Framework** is a globally recognized knowledge base that documents the tactics, techniques, and procedures (TTPs) used by adversaries.

It helps security teams:

- Understand attacker behavior
- Improve threat detection
- Perform threat hunting
- Build SIEM detection rules
- Strengthen incident response
- Validate defensive controls

Cloud attacks often target identities, APIs, workloads, storage, and management services rather than traditional operating systems.

---

# MITRE ATT&CK Tactics

The Enterprise ATT&CK framework groups attacker actions into tactics.

Common tactics relevant to cloud environments include:

- Initial Access
- Execution
- Persistence
- Privilege Escalation
- Defense Evasion
- Credential Access
- Discovery
- Lateral Movement
- Collection
- Command and Control
- Exfiltration
- Impact

---

# Cloud Attack Lifecycle

A simplified cloud attack lifecycle:

```
Reconnaissance
        ↓
Credential Theft
        ↓
Initial Access
        ↓
Privilege Escalation
        ↓
Persistence
        ↓
Discovery
        ↓
Lateral Movement
        ↓
Data Collection
        ↓
Exfiltration
        ↓
Impact
```

---

# Initial Access

## Objective

Gain unauthorized access to cloud resources.

### Common Techniques

- Phishing
- Stolen credentials
- Password spraying
- Credential stuffing
- Exploiting exposed services
- Insecure APIs

### Blue Team Detection

Monitor for:

- Failed login spikes
- Impossible travel logins
- New device logins
- Anonymous IP addresses
- Unusual authentication locations

---

# Execution

## Objective

Execute malicious code or workloads.

### Examples

- Malicious scripts
- Serverless function abuse
- Container execution
- Unauthorized virtual machine creation

### Detection

Monitor:

- New workload creation
- Script execution
- Unexpected container deployments
- Unauthorized automation jobs

---

# Persistence

## Objective

Maintain long-term access.

### Examples

- Creating new IAM users
- Adding API keys
- Persistent access tokens
- Scheduled cloud functions
- Startup scripts

### Detection

Monitor:

- New administrator accounts
- API key creation
- Role changes
- Long-lived credentials

---

# Privilege Escalation

## Objective

Obtain higher permissions.

### Examples

- IAM policy abuse
- Role assumption
- Misconfigured permissions
- Overprivileged accounts

### Detection

Monitor:

- IAM policy changes
- Privileged role assignments
- Permission escalation events
- Administrator group modifications

---

# Defense Evasion

## Objective

Avoid detection.

### Examples

- Disabling logging
- Deleting audit logs
- Removing monitoring agents
- Tampering with alerts

### Detection

Monitor:

- Logging disabled
- Audit trail modifications
- Security service failures
- Unexpected configuration changes

---

# Credential Access

## Objective

Steal authentication credentials.

### Common Targets

- API keys
- Access tokens
- Passwords
- Secrets
- Cloud credentials

### Detection

Monitor:

- Secret access
- Credential downloads
- Metadata service requests
- Password reset activity

---

# Discovery

## Objective

Gather information about the cloud environment.

### Examples

- Enumerating virtual machines
- Listing storage buckets
- Discovering IAM roles
- Querying APIs
- Network discovery

### Detection

Monitor:

- High-volume API enumeration
- Inventory requests
- Resource listing activities
- IAM discovery commands

---

# Lateral Movement

## Objective

Move between cloud resources.

### Examples

- Role assumption
- Accessing additional workloads
- Cross-account access
- Container movement

### Detection

Monitor:

- Cross-account authentication
- New trust relationships
- Unexpected resource access
- Internal network communication anomalies

---

# Collection

## Objective

Gather sensitive information.

### Examples

- Database exports
- Storage downloads
- Backup access
- Log collection

### Detection

Monitor:

- Large downloads
- Database exports
- Storage access spikes
- Backup retrieval

---

# Exfiltration

## Objective

Transfer stolen data outside the environment.

### Examples

- Cloud storage synchronization
- External file transfers
- API uploads
- Data compression

### Detection

Monitor:

- Large outbound transfers
- Unknown destinations
- Unusual storage activity
- Data export operations

---

# Impact

## Objective

Disrupt operations or destroy data.

### Examples

- Resource deletion
- Ransomware
- Cryptojacking
- Service disruption

### Detection

Monitor:

- Resource termination
- Encryption activity
- CPU spikes
- Unexpected billing increases

---

# Common Cloud Attack Techniques

Frequently observed attack techniques include:

- Credential theft
- IAM abuse
- Public storage exposure
- Misconfigured security groups
- API abuse
- Container compromise
- Serverless abuse
- Supply chain compromise
- Cryptojacking
- Shadow IT

---

# Blue Team Detection Opportunities

Security teams should continuously monitor for:

### Authentication

- Impossible travel
- Failed logins
- New MFA enrollment
- Password resets

---

### Identity

- New administrator accounts
- Role changes
- Policy modifications
- Privilege escalation

---

### Compute

- New virtual machines
- Unauthorized containers
- Suspicious serverless functions

---

### Storage

- Public bucket creation
- Sensitive file downloads
- Permission changes

---

### Networking

- Firewall modifications
- Security group changes
- Unexpected public IP assignments

---

### APIs

- Excessive API requests
- Unauthorized API calls
- Enumeration behavior

---

### Billing

- Sudden cost increases
- Unexpected compute usage
- Cryptocurrency mining indicators

---

# Threat Hunting Ideas

Cloud threat hunters should investigate:

- Privileged account creation
- Disabled logging
- Newly exposed storage
- High-volume downloads
- Long-lived access tokens
- Cross-region logins
- Rare API usage
- Unusual administrative activity

---

# SIEM Use Cases

Common SIEM detection rules include:

- Multiple failed logins
- Impossible travel
- New administrator account
- Privilege escalation
- Public storage exposure
- API abuse
- Disabled logging
- High outbound data transfer
- Cryptojacking indicators
- Unexpected workload deployment

---

# Cloud Security Monitoring Checklist

Review regularly:

- IAM users
- MFA coverage
- API activity
- Storage permissions
- Security groups
- Firewall rules
- CloudTrail / Activity Logs
- Billing reports
- Resource inventory
- Vulnerability reports

---

# CEH Exam Tips

Remember:

- ATT&CK describes attacker behavior using tactics and techniques.
- Credential theft is one of the most common cloud attack methods.
- IAM abuse frequently leads to privilege escalation.
- Misconfigured storage is a common cause of data breaches.
- SIEM platforms detect suspicious cloud activities.
- Threat hunting relies on log analysis and behavioral monitoring.
- Blue Teams should monitor identities, workloads, APIs, storage, and networking continuously.

---

# Interview Tips

Be prepared to explain:

- The purpose of the MITRE ATT&CK Framework.
- How cloud attacks differ from traditional network attacks.
- Why IAM is critical in cloud security.
- How SIEM detects cloud threats.
- Examples of cloud threat hunting activities.
- Common indicators of cloud compromise.

---

# Key Takeaways

- The MITRE ATT&CK Enterprise Framework helps defenders understand, detect, and respond to cloud attacks.
- Cloud attackers commonly target identities, APIs, storage, workloads, and management services.
- Effective cloud defense combines continuous monitoring, threat hunting, SIEM correlation, and least-privilege access control aligned with ATT&CK tactics.
