# CEH Class 3 Notes

## Topic: Exploiting EternalBlue (MS17-010)

---

# 1. Lab Objective

Understand the complete penetration testing workflow against a vulnerable Windows machine.

Workflow:

Reconnaissance → Enumeration → Vulnerability Discovery → Exploitation → Post Exploitation → Flag Collection

---

# 2. VPN Connection

Purpose:

* Access TryHackMe private lab network.
* Communicate with target machines securely.

Steps:

1. Download VPN configuration file.
2. Import configuration into Kali Linux.
3. Establish VPN connection.
4. Verify connectivity.

---

# 3. Reconnaissance

Goal:

Identify:

* Live host
* Open ports
* Running services
* Operating system

Information Gathered:

* Target Operating System: Windows 7
* SMB Service Exposed

---

# 4. Vulnerability Scanning

Tool:

* Nmap

Purpose:

* Detect vulnerabilities.
* Identify known SMB weaknesses.

Finding:

* SMB service vulnerable to EternalBlue (MS17-010).

Risk Level:

Critical

Impact:

Remote code execution without authentication.

---

# 5. EternalBlue Overview

Vulnerability ID:

MS17-010

Affected Service:

SMBv1

Affected Systems:

* Windows 7
* Windows Server 2008
* Older Microsoft systems

Impact:

* Remote code execution
* System compromise
* Malware propagation

Historical Example:

WannaCry Ransomware

---

# 6. Exploitation Phase

Tool:

Metasploit Framework

Process:

1. Select EternalBlue exploit module.
2. Configure target information.
3. Configure payload.
4. Launch exploit.
5. Gain shell access.

Result:

Successful compromise of target machine.

---

# 7. Shell Upgrade

Initial Access:

Regular command shell

Issue:

Limited functionality

Solution:

Upgrade shell to Meterpreter.

Benefits:

* Better post-exploitation capabilities
* File operations
* Process migration
* Credential access
* Privilege management

---

# 8. Process Migration

Purpose:

Improve session stability.

Concept:

Move Meterpreter session into a stable Windows process.

Benefits:

* Reduced chance of session termination
* Improved persistence during engagement

---

# 9. Credential Access

Objective:

Extract local account password hashes.

Technique:

Hash dumping via Meterpreter.

Result:

Obtained user account hashes.

---

# 10. Password Cracking

Method:

Online hash lookup/cracking services.

Purpose:

Recover plaintext passwords from hashes when possible.

Learning Point:

Weak passwords can often be recovered quickly.

---

# 11. Flag Collection

Post-exploitation activities included:

* User flag discovery
* System flag discovery
* Additional room objectives

Result:

Room completed successfully.

---

# Key CEH Domains Covered

* Footprinting
* Scanning Networks
* Vulnerability Analysis
* System Hacking
* Password Attacks
* Enumeration
* Post Exploitation

---

# Important Takeaway

A single unpatched SMB vulnerability can lead to complete system compromise, demonstrating the importance of patch management and vulnerability remediation.
