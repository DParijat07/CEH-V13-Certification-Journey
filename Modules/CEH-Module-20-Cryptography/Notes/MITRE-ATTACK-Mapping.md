# MITRE ATT&CK Mapping – Cryptography

## Overview

Cryptography itself is a defensive technology, but attackers frequently abuse cryptographic techniques or exploit weaknesses in cryptographic implementations during different phases of the MITRE ATT&CK framework.

Security analysts should understand how encryption, certificates, keys, TLS, and cryptographic protocols are abused so they can detect and investigate malicious activity.

---

# MITRE ATT&CK Mapping

| ATT&CK Tactic | Example Cryptographic Abuse |
|---------------|-----------------------------|
| Initial Access | Fake HTTPS websites, forged certificates |
| Credential Access | Password hash theft, offline password cracking |
| Persistence | Malicious certificates, signed malware |
| Defense Evasion | Encrypted malware, encrypted C2, packed binaries |
| Discovery | TLS certificate enumeration |
| Credential Access | Kerberos ticket attacks |
| Collection | Encrypting stolen data before exfiltration |
| Command and Control | HTTPS, TLS, DNS over HTTPS (DoH) |
| Exfiltration | Encrypted data transfer |
| Impact | Ransomware encrypting files |

---

# Initial Access

## Fake HTTPS Websites

Attackers create phishing websites protected with valid TLS certificates to increase user trust.

### Examples

- Fake banking portals
- Fake Microsoft login pages
- Fake Google authentication pages

---

## Detection

Monitor for:

- Newly registered domains
- Suspicious TLS certificates
- Brand impersonation
- Unexpected certificate issuers

---

# Credential Access

## Password Hash Theft

Attackers steal password hashes from:

- Windows SAM
- Active Directory (NTDS.dit)
- Linux shadow files

Hashes are cracked offline.

---

## MITRE Mapping

Technique:

- OS Credential Dumping

---

## Detection

Monitor:

- SAM access
- LSASS access
- NTDS extraction
- Shadow file access

---

# Credential Access

## Kerberos Ticket Attacks

Examples:

- Kerberoasting
- AS-REP Roasting
- Golden Ticket
- Silver Ticket

Attackers abuse Kerberos encryption and ticketing.

---

## Detection

Monitor:

- Unusual Kerberos requests
- Excessive TGS requests
- Abnormal ticket lifetimes
- Domain Controller logs

---

# Persistence

## Signed Malware

Attackers digitally sign malware using:

- Stolen certificates
- Fraudulent certificates
- Compromised Certificate Authorities

Digitally signed malware appears more trustworthy.

---

## Detection

Monitor:

- Unexpected publishers
- Invalid signatures
- Expired certificates
- Certificate revocation status

---

# Defense Evasion

## Encrypted Malware

Modern malware encrypts:

- Configuration files
- Payloads
- Strings
- Communications

Purpose:

Prevent detection by antivirus and EDR products.

---

## Detection

Monitor:

- Packed executables
- High entropy files
- Obfuscated binaries
- Memory-only payloads

---

# Defense Evasion

## Encrypted Command and Control

Malware often communicates over:

- HTTPS
- TLS
- DNS over HTTPS (DoH)
- Encrypted WebSockets

Encryption hides malicious traffic.

---

## Detection

Monitor:

- Unusual TLS destinations
- Self-signed certificates
- JA3/JA4 TLS fingerprints
- Beaconing behavior
- Rare domains

---

# Discovery

## Certificate Enumeration

Attackers enumerate certificates to identify:

- VPN services
- Internal PKI
- Enterprise applications
- Authentication systems

---

## Detection

Monitor:

- Certificate store access
- Certificate export attempts
- Enumeration tools

---

# Collection

## Data Encryption Before Exfiltration

Attackers encrypt stolen data before uploading it.

Purpose:

Avoid detection by DLP solutions.

---

## Detection

Monitor:

- Archive creation
- Encryption utilities
- Large encrypted files
- Sudden file compression

---

# Command and Control

## HTTPS-Based C2

Common attacker channels:

- HTTPS
- TLS
- HTTP/2
- WebSockets

These blend malicious traffic with legitimate web traffic.

---

## Detection

Monitor:

- Rare destinations
- Long-lived TLS sessions
- Beacon intervals
- Abnormal User-Agent strings

---

# Exfiltration

## Encrypted Exfiltration

Attackers transfer stolen data through:

- HTTPS
- SFTP
- FTPS
- VPN tunnels
- Cloud storage APIs

---

## Detection

Monitor:

- Large outbound transfers
- Cloud uploads
- Unusual encrypted sessions
- Geographic anomalies

---

# Impact

## Ransomware

Ransomware encrypts:

- Documents
- Databases
- Backups
- Network shares

Purpose:

Prevent access until a ransom is paid.

---

## Detection

Monitor:

- Mass file modifications
- File extension changes
- Shadow copy deletion
- High-volume file encryption
- Ransom notes

---

# Certificate Abuse

Attackers may abuse:

- Stolen certificates
- Expired certificates
- Rogue Certificate Authorities
- Self-signed certificates

---

## Detection

Monitor:

- Unexpected certificate changes
- Invalid certificate chains
- Certificate pinning failures
- Certificate transparency logs

---

# SOC Monitoring Opportunities

Security teams should monitor:

- TLS version usage
- Weak cipher suites
- Certificate expiration
- Certificate revocation failures
- Certificate issuance logs
- HSM events
- Key rotation events
- Cryptographic library errors
- Unauthorized key access

---

# SIEM Use Cases

Generate alerts for:

- Expired certificates
- Self-signed certificates
- TLS downgrade attempts
- Deprecated protocols (SSL, TLS 1.0)
- Weak encryption algorithms
- Repeated authentication failures
- Suspicious certificate installations
- High-volume encryption activity
- Ransomware indicators

---

# Threat Hunting Ideas

Threat hunters should investigate:

- Rare TLS destinations
- New outbound encrypted connections
- High entropy executables
- Certificate modifications
- Unexpected certificate exports
- Long-running HTTPS sessions
- Abnormal VPN usage
- Password hash dumping activity
- Kerberos anomalies

---

# Blue Team Best Practices

- Disable SSL and legacy TLS versions.
- Enforce TLS 1.2 or TLS 1.3.
- Monitor certificate lifecycles.
- Rotate cryptographic keys regularly.
- Secure private keys with HSMs.
- Audit PKI infrastructure.
- Monitor certificate transparency logs.
- Detect weak cipher suites.
- Investigate unusual encrypted traffic.
- Deploy network traffic analysis and EDR solutions.

---

# CEH Exam Tips

Remember:

- Attackers frequently abuse HTTPS and TLS for stealth.
- Password hashes are commonly cracked offline.
- Kerberos attacks target encrypted authentication tickets.
- Ransomware uses encryption to deny access.
- Digitally signed malware can bypass trust mechanisms.
- Self-signed or rogue certificates are common indicators of malicious activity.
- Monitoring certificates and TLS configurations is an important Blue Team responsibility.

---

# Key Takeaways

- Cryptography protects modern systems, but attackers also leverage encryption to hide malicious activities.
- Effective defense requires monitoring certificates, TLS usage, encrypted traffic, key management events, and ransomware behavior while aligning detections with the MITRE ATT&CK framework.
