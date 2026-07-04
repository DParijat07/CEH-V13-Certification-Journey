# System Hacking Interview Questions

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Frequently asked interview questions for CEH, SOC, VAPT, and Entry-Level Cybersecurity roles.

---

# Basic Questions

## 1. What is System Hacking?

System Hacking is the process of gaining access to a target system, escalating privileges, maintaining access, and assessing security weaknesses during an authorized penetration test.

---

## 2. What are the phases of System Hacking?

- Password Attacks
- Privilege Escalation
- Maintaining Access
- Covering Tracks

---

## 3. What is Privilege Escalation?

The process of gaining higher privileges after obtaining initial access to a system.

---

## 4. Difference between Vertical and Horizontal Privilege Escalation?

**Vertical**
- User → Administrator/Root

**Horizontal**
- One normal user → Another normal user

---

## 5. What is Password Cracking?

Recovering plaintext passwords from password hashes using authorized methods.

---

# Tool-Based Questions

## 6. What is Hydra used for?

Hydra performs **online password brute-force attacks** against network services.

---

## 7. What is John the Ripper?

A tool used for **offline password cracking**.

---

## 8. What is Hashcat?

A **GPU-accelerated password cracking** tool.

---

## 9. What is Metasploit?

An exploitation framework used for vulnerability exploitation and post-exploitation.

---

## 10. What is Meterpreter?

An advanced in-memory shell used for post-exploitation.

---

## 11. What is WinPEAS?

A Windows privilege escalation enumeration tool.

---

## 12. What is LinPEAS?

A Linux privilege escalation enumeration tool.

---

# Windows Questions

## 13. Which command displays current user information?

```cmd
whoami
```

---

## 14. Which command displays Windows privileges?

```cmd
whoami /priv
```

---

## 15. Which command lists local users?

```cmd
net user
```

---

## 16. Which command displays system information?

```cmd
systeminfo
```

---

## 17. Which command lists running processes?

```cmd
tasklist
```

---

# Linux Questions

## 18. Which command displays the current user?

```bash
whoami
```

---

## 19. Which command displays user information?

```bash
id
```

---

## 20. Which command checks sudo permissions?

```bash
sudo -l
```

---

## 21. Which command finds SUID binaries?

```bash
find / -perm -4000 -type f 2>/dev/null
```

---

## 22. Which command displays running processes?

```bash
ps aux
```

---

# Privilege Escalation Questions

## 23. Name common Windows privilege escalation techniques.

- Weak Service Permissions
- Unquoted Service Paths
- AlwaysInstallElevated
- DLL Hijacking
- Token Impersonation

---

## 24. Name common Linux privilege escalation techniques.

- SUID Binaries
- Weak sudo permissions
- Cron Jobs
- Capabilities
- Kernel Exploits

---

## 25. What is GTFOBins?

A collection of Unix binaries that can be abused for privilege escalation and command execution.

---

# Persistence Questions

## 26. What is Persistence?

A technique used to maintain access after the initial compromise.

---

## 27. Name Windows persistence techniques.

- Startup Folder
- Registry Run Keys
- Scheduled Tasks
- Windows Services

---

## 28. Name Linux persistence techniques.

- Cron Jobs
- SSH Authorized Keys
- Startup Scripts

---

# Covering Tracks Questions

## 29. What is Covering Tracks?

Techniques used to hide attacker activities and avoid detection.

---

## 30. Name two anti-forensic techniques.

- Clearing Logs
- Timestamp Manipulation

---

# MITRE ATT&CK Questions

## 31. What is MITRE ATT&CK?

A framework that maps attacker tactics and techniques.

---

## 32. Which ATT&CK technique represents Brute Force?

```
T1110
```

---

## 33. Which ATT&CK technique represents Credential Dumping?

```
T1003
```

---

# Scenario-Based Questions

## 34. What would you do after gaining a shell?

- Verify access
- Enumerate the system
- Identify privilege escalation paths
- Document findings
- Recommend remediation

---

## 35. What should you do before attempting privilege escalation?

Perform thorough system enumeration.

---

## 36. Why is documentation important during penetration testing?

It provides evidence, supports findings, and helps clients remediate vulnerabilities.

---

# Quick Revision

| Question | Answer |
|-----------|--------|
| Online Password Attack Tool | Hydra |
| Offline Password Cracker | John the Ripper |
| GPU Password Cracker | Hashcat |
| Exploitation Framework | Metasploit |
| Post Exploitation Shell | Meterpreter |
| Windows Enumeration Tool | WinPEAS |
| Linux Enumeration Tool | LinPEAS |
| Linux PrivEsc Reference | GTFOBins |
| Windows Current User | `whoami` |
| Linux Current User | `whoami` |

---

# CEH Interview Tips

✔ Understand concepts instead of memorizing commands.

✔ Be able to explain your methodology.

✔ Practice on TryHackMe, VulnHub, and Hack The Box.

✔ Maintain proper documentation for every lab.

✔ Focus on both offensive techniques and defensive mitigations.

---

## Related Notes

- `10-Privilege-Escalation-Windows.md`
- `11-Privilege-Escalation-Linux.md`
- `17-System-Hacking-Tools.md`
- `18-MITRE-Mapping.md`
- `20-Cheat-Sheet.md`
