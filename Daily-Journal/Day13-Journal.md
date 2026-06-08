# Day 13 Journal

**Date:** 08/06/2026

## Summary

Today was one of the most practical and hands-on cybersecurity learning days so far. I attended my 4th CEH training class at IEMLabs and completed the ICE room on TryHackMe. The room covered the complete attack lifecycle from reconnaissance to post-exploitation on a Windows target. I used Kali Linux as the attacking machine and connected to the TryHackMe VPN to place my machine in the same virtual network as the target.

---

## Activities Completed

### 1. IEMLabs CEH Class 04

Attended the fourth CEH training session and continued learning practical ethical hacking concepts aligned with CEHv13.

#### Topics Reinforced

* Vulnerability Assessment
* Service Enumeration
* Metasploit Framework
* Privilege Escalation Concepts
* Windows Internals
* Post Exploitation

---

### 2. TryHackMe - ICE Room

Successfully solved the ICE room and completed all tasks.

#### Initial Access

* Downloaded TryHackMe VPN configuration file.
* Connected Kali Linux to the TryHackMe network.
* Verified connectivity using ping.
* Performed Nmap scanning.

#### Nmap Activities

* SYN Scan
* Aggressive Scan

Identified:

* Open Ports
* Running Services
* Hostname
* Operating System Information

---

### 3. Vulnerability Assessment

Discovered:

```text
Icecast Media Server
Port 8000
```

Performed vulnerability research.

#### Activities

* Reviewed CVE information.
* Studied CVSS score.
* Analyzed impact rating.
* Researched exploit availability.

#### Outcome

Identified a publicly available Metasploit module for exploitation.

---

### 4. Exploitation

Used Metasploit Framework.

#### Activities

* Started msfconsole.
* Searched exploit module.
* Configured RHOSTS.
* Configured LHOST.
* Executed exploit.

#### Result

Successfully obtained a Meterpreter session.

---

### 5. Post Exploitation Enumeration

Executed:

```text
getuid
getpid
sysinfo
```

Collected:

* Username
* Hostname
* Windows Build Information
* Architecture Information

---

### 6. Privilege Escalation

Executed:

```text
run post/multi/recon/local_exploit_suggester
```

Identified potential privilege escalation vectors.

Selected:

```text
exploit/windows/local/bypassuac_eventvwr
```

Backgrounded current session and executed privilege escalation module.

Successfully obtained elevated privileges.

---

### 7. Process Migration

Investigated running processes.

Used:

```text
ps
```

Migrated to:

```text
spoolsv.exe
```

Verified privileges:

```text
getuid
```

Result:

```text
NT AUTHORITY\SYSTEM
```

---

### 8. Credential Access

Loaded Kiwi (Mimikatz).

```text
load kiwi
```

Used:

```text
creds_all
```

Successfully recovered stored credentials.

---

### 9. Post Exploitation Techniques

Explored:

* Hash Dumping
* Screen Sharing
* Microphone Recording
* Timestamp Manipulation
* Golden Ticket Creation
* Remote Desktop Enablement

Commands studied:

```text
hashdump
screenshare
record_mic
timestomp
golden_ticket_create
```

---

## Key Learnings

* Vulnerability research is a critical step before exploitation.
* Meterpreter provides powerful post-exploitation capabilities.
* Privilege escalation often requires understanding Windows internals.
* Process migration is important for stability and privilege access.
* Credential access techniques demonstrate the importance of endpoint protection.

---

## Future Research Topics

* spoolsv.exe
* lsass.exe
* UAC Bypass Concepts
* EventVwr UAC Bypass
* Token Impersonation
* Windows Authentication Architecture

---

## Achievements

* Completed ICE Room.
* Performed full exploitation lifecycle.
* Practiced Metasploit Framework.
* Practiced Privilege Escalation.
* Practiced Credential Access.
* Continued CEHv13 practical learning journey.

---

## Next Session Plan

### Module 05

* Vulnerability Assessment Lifecycle
* CVSS Scoring
* Vulnerability Classification
* Vulnerability Management

### Research

* Windows Authentication Architecture
* LSASS Process
* Print Spooler Service
* UAC Bypass Mechanisms

### Documentation

* Complete ICE VAPT Report
* Update GitHub Repository
* Create Module 05 Notes
