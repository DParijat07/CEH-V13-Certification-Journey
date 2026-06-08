# IEMLabs CEH Class 04 Notes

## Overview

This class focused on practical vulnerability assessment, exploitation methodology, privilege escalation, and post-exploitation concepts using Windows targets.

---

# Vulnerability Assessment Workflow

## Step 1 - Discovery

Identify:

* Hosts
* Services
* Operating Systems
* Open Ports

Tools:

* Nmap
* Netcat
* Metasploit Auxiliary Modules

---

## Step 2 - Enumeration

Gather:

* Usernames
* Shares
* Services
* Software Versions

Goal:

Identify attack surface.

---

## Step 3 - Vulnerability Identification

Research:

* CVEs
* CVSS Scores
* Exploit Availability

Resources:

* CVE Details
* NVD
* Searchsploit

---

## Step 4 - Exploitation

Metasploit Workflow:

```text
search
use
show options
set
exploit
```

Important Concepts:

* Exploit
* Payload
* Session
* Meterpreter

---

# Meterpreter Basics

Useful Commands:

```text
sysinfo
getuid
getpid
pwd
ls
ps
migrate
background
```

---

# Local Exploit Suggester

Purpose:

Identify privilege escalation opportunities.

Command:

```text
run post/multi/recon/local_exploit_suggester
```

Output:

Potential local privilege escalation modules.

---

# UAC Bypass

Purpose:

Gain elevated privileges without direct administrator login.

Example Module:

```text
exploit/windows/local/bypassuac_eventvwr
```

---

# Windows Processes

## spoolsv.exe

Print Spooler Service.

Used for:

* Printer management
* Stable process migration

---

## lsass.exe

Local Security Authority Subsystem Service.

Responsible for:

* Authentication
* Credential Storage
* Security Policies

---

# Process Migration

Purpose:

Move Meterpreter into a stable process.

Benefits:

* Better stability
* Access to resources
* Reduced crash risk

Commands:

```text
ps
migrate <PID>
```

---

# Credential Access

Kiwi (Mimikatz)

Load:

```text
load kiwi
```

Common Commands:

```text
creds_all
hashdump
```

---

# Post Exploitation

Capabilities:

* Credential Access
* Screen Monitoring
* Persistence
* Remote Access
* Timestamp Manipulation

Examples:

```text
screenshare
record_mic
timestomp
golden_ticket_create
```

---

# Key Takeaways

* Enumeration precedes vulnerability assessment.
* Vulnerability assessment precedes exploitation.
* Exploitation does not guarantee administrative privileges.
* Privilege escalation is often a separate phase.
* Post-exploitation activities depend heavily on access level.
* Understanding Windows internals improves exploitation success.

---

# CEHv13 Mapping

Module 03 → Network Scanning

Module 04 → Enumeration

Module 05 → Vulnerability Assessment

Module 06 → System Hacking
