

# System Hacking Workflow

> **Module:** CEH v13 - Module 06 (System Hacking)
>
> **Difficulty:** Beginner → Intermediate
>
> **Objective:** Understand the complete ethical hacking workflow after discovering a target.

---

# What is System Hacking?

System Hacking is the process of gaining authorized access to a target system during a penetration test, identifying security weaknesses, assessing the impact of vulnerabilities, and documenting findings. In an ethical hacking engagement, all activities are performed with explicit authorization to evaluate and improve an organization's security posture.

System hacking is one of the most practical modules in CEH because it combines reconnaissance, exploitation, privilege escalation, post-exploitation, and reporting into a structured methodology.

---

# System Hacking Lifecycle

```text
Reconnaissance
      │
      ▼
Scanning
      │
      ▼
Enumeration
      │
      ▼
Vulnerability Identification
      │
      ▼
Gain Initial Access
      │
      ▼
Privilege Escalation
      │
      ▼
Credential Access
      │
      ▼
Post Exploitation
      │
      ▼
Persistence
      │
      ▼
Covering Tracks
      │
      ▼
Documentation & Reporting
```

---

# Phase 1 – Reconnaissance

## Objective

Collect information about the target before attacking it.

Reconnaissance is divided into:

- Passive Reconnaissance
- Active Reconnaissance

### Passive Reconnaissance

No direct interaction with the target.

Examples:

- Google Dorking
- WHOIS
- DNS Records
- LinkedIn
- Company Website
- GitHub
- Shodan
- Social Media

### Active Reconnaissance

Direct interaction with the target.

Examples:

- Ping
- Nmap
- Traceroute
- Banner Grabbing

---

## Typical Tools

| Tool | Purpose |
|------|----------|
| Google | OSINT |
| WHOIS | Domain Information |
| nslookup | DNS |
| dig | DNS |
| Shodan | Internet Devices |
| Maltego | Relationship Mapping |
| theHarvester | Email Collection |

---

# Phase 2 – Scanning

## Objective

Identify:

- Live Hosts
- Open Ports
- Running Services
- Service Versions
- Operating System

---

### Common Nmap Commands

Basic Scan

```bash
nmap TARGET_IP
```

SYN Scan

```bash
nmap -sS TARGET_IP
```

Version Detection

```bash
nmap -sV TARGET_IP
```

Default Scripts

```bash
nmap -sC TARGET_IP
```

Aggressive Scan

```bash
nmap -A TARGET_IP
```

OS Detection

```bash
nmap -O TARGET_IP
```

---

### Expected Output

- Open Ports
- Service Version
- Hostname
- OS Guess
- SSL Certificates
- HTTP Headers

---

# Phase 3 – Enumeration

Enumeration goes beyond scanning.

It aims to extract useful information from discovered services.

---

## Examples

SSH

- Users
- Authentication

HTTP

- Directories
- CMS
- Login Pages
- Robots.txt

SMB

- Shares
- Anonymous Login

FTP

- Anonymous Access

DNS

- Zone Transfer

SNMP

- Device Information

LDAP

- User Enumeration

---

## Common Enumeration Tools

| Tool | Purpose |
|------|----------|
| Gobuster | Directory Enumeration |
| Nikto | Web Scanner |
| enum4linux | SMB Enumeration |
| smbclient | SMB |
| rpcclient | SMB |
| curl | HTTP Requests |
| wget | Download Files |
| ldapsearch | LDAP |

---

# Phase 4 – Vulnerability Identification

Now determine whether the discovered services contain vulnerabilities.

Examples

- Outdated Software
- Weak Passwords
- Default Credentials
- Misconfiguration
- Public CVEs

---

## Useful Resources

- CVE Details
- NVD
- Exploit Database
- GTFOBins
- LOLBAS

---

## Example

```
Icecast 2.0.1

↓

CVE Search

↓

Known RCE

↓

Metasploit Module Available
```

---

# Phase 5 – Gain Initial Access

Objective

Obtain the first shell.

Methods

- Password Attack
- Exploit
- Web Shell
- Reverse Shell
- SQL Injection
- File Upload
- Authentication Bypass

---

## Common Tools

| Tool | Purpose |
|------|----------|
| Hydra | Password Attack |
| Medusa | Password Attack |
| Burp Suite | Web Testing |
| Metasploit | Exploitation |
| Netcat | Listener |
| PHP Reverse Shell | Web Shell |

---

## Initial Shell Types

- Bash Shell
- Reverse Shell
- Bind Shell
- Meterpreter
- Web Shell

---

# Phase 6 – Privilege Escalation

Getting a shell does NOT mean you own the machine.

Usually you'll start as:

- www-data
- apache
- nginx
- robot
- guest

Goal:

Become:

- root
- Administrator
- SYSTEM

---

## Linux

Common Checks

```bash
sudo -l

find / -perm -4000 -type f

id

uname -a

cat /etc/passwd
```

---

## Windows

Common Checks

```text
whoami

systeminfo

net user

net localgroup administrators

tasklist

wmic
```

---

# Phase 7 – Credential Access

Attackers often attempt to obtain credentials for further access.

Examples

Linux

- Shadow File
- SSH Keys
- Browser Passwords

Windows

- SAM Database
- LSASS Memory
- Cached Credentials
- NTLM Hashes

---

## Common Tools

- Mimikatz
- Kiwi
- secretsdump
- hashdump
- John the Ripper
- Hashcat

---

# Phase 8 – Post Exploitation

After gaining privileged access, collect useful information.

Examples

- Users
- Running Processes
- Installed Software
- Scheduled Tasks
- Network Configuration
- Shares
- Passwords
- Sensitive Files

---

## Typical Commands

Linux

```bash
hostname

whoami

id

ps aux

netstat -tulpn
```

Windows

```text
hostname

whoami

systeminfo

tasklist

netstat -ano
```

---

# Phase 9 – Persistence

Persistence allows future access.

Examples

Linux

- SSH Keys
- Cron Jobs
- Systemd Services

Windows

- Registry Run Keys
- Scheduled Tasks
- Startup Folder
- Services

> **Note:** In professional penetration tests, persistence techniques should only be demonstrated if they are within the agreed scope and authorized by the client.

---

# Phase 10 – Covering Tracks

Attackers often attempt to hide evidence.

Examples

- Clear Logs
- Delete Temporary Files
- Remove Shells
- Modify Timestamps

> **Note:** In authorized penetration testing, modifying or deleting logs is generally avoided unless it is an explicitly approved objective, because it can interfere with incident response and forensic analysis.

---

# Phase 11 – Documentation

The final phase.

No penetration test is complete without proper reporting.

Professional reports include:

- Executive Summary
- Scope
- Methodology
- Findings
- Risk Ratings
- Screenshots
- Proof of Concept
- Recommendations
- Conclusion

---

# Tools Used During System Hacking

| Phase | Tools |
|---------|-------|
| Recon | Google, WHOIS, Shodan |
| Scanning | Nmap |
| Enumeration | Gobuster, Nikto |
| Exploitation | Metasploit |
| Password Attack | Hydra |
| Hash Cracking | John, Hashcat |
| Post Exploitation | Meterpreter |
| Privilege Escalation | GTFOBins, LinPEAS, WinPEAS |
| Reporting | Markdown, Word, Screenshots |

---

# CEH Module Mapping

| Activity | CEH Module |
|-----------|------------|
| Scanning | Module 03 |
| Enumeration | Module 04 |
| Vulnerability Assessment | Module 05 |
| System Hacking | Module 06 |
| Malware | Module 07 |
| Sniffing | Module 08 |
| Social Engineering | Module 09 |

---

# Real-World Practice

The following labs reinforce the concepts covered in this workflow:

- TryHackMe – Blue
- TryHackMe – Ice
- TryHackMe – Mr. Robot
- VulnHub – Basic Pentesting 1
- Metasploitable 2
- OWASP Broken Web Applications

---

# Interview Questions

### What is System Hacking?

System Hacking is the process of gaining authorized access to a target system, assessing its security posture through activities such as enumeration, exploitation, privilege escalation, and post-exploitation, and documenting findings to improve the organization's defenses.

---

### Why is Enumeration important?

Enumeration reveals detailed information about users, services, shares, configurations, and other resources that helps identify potential attack paths.

---

### What is the difference between Initial Access and Privilege Escalation?

- Initial Access obtains the first foothold on a target.
- Privilege Escalation increases permissions to gain administrative or root-level access.

---

# Key Takeaways

- Follow a structured methodology instead of attacking randomly.
- Enumeration often provides the most valuable information.
- Least-privileged shells usually require privilege escalation.
- Documentation is as important as technical exploitation.
- Always perform activities within the authorized scope and maintain evidence for reporting.

---

**Author:** Parijat Das  
**Certification Track:** CEH v13  
**Last Updated:** July 2026
