# MITRE ATT&CK Mapping – System Hacking

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Understand how common system hacking techniques map to the MITRE ATT&CK Framework.

---

# What is MITRE ATT&CK?

The **MITRE ATT&CK Framework** is a globally recognized knowledge base that maps real-world adversary behaviors.

It helps security professionals:

- Understand attacker tactics
- Detect threats
- Improve defensive strategies
- Perform threat hunting
- Build detection rules

---

# ATT&CK Tactics Used in System Hacking

| Tactic | Description |
|----------|------------|
| Initial Access | Gain entry into a target |
| Execution | Execute malicious code |
| Persistence | Maintain access |
| Privilege Escalation | Gain higher privileges |
| Defense Evasion | Avoid detection |
| Credential Access | Steal credentials |
| Discovery | Gather system information |
| Lateral Movement | Move across systems |
| Collection | Gather sensitive data |
| Exfiltration | Transfer stolen data |
| Impact | Disrupt or damage systems |

---

# CEH Module 06 Technique Mapping

| CEH Topic | MITRE ATT&CK Technique |
|-----------|------------------------|
| Password Attacks | T1110 – Brute Force |
| Credential Dumping | T1003 – OS Credential Dumping |
| Account Discovery | T1087 – Account Discovery |
| System Information Discovery | T1082 |
| Process Discovery | T1057 |
| File & Directory Discovery | T1083 |
| Network Service Scanning | T1046 |
| Permission Groups Discovery | T1069 |
| Scheduled Tasks | T1053 |
| Registry Run Keys | T1547 |
| Windows Services | T1543 |
| SSH Authorized Keys | T1098 |
| Command Execution | T1059 |
| File Deletion | T1070 |
| Clear Event Logs | T1070.001 |
| Timestomping | T1070.006 |

---

# Common System Hacking Techniques

## Brute Force

**Technique**

```
T1110
```

Examples

- Hydra
- Medusa
- Ncrack

---

## Credential Dumping

**Technique**

```
T1003
```

Examples

- Mimikatz
- hashdump
- lsass memory dump

---

## Account Discovery

**Technique**

```
T1087
```

Commands

Windows

```cmd
net user
```

Linux

```bash
cat /etc/passwd
```

---

## Process Discovery

**Technique**

```
T1057
```

Commands

Windows

```cmd
tasklist
```

Linux

```bash
ps aux
```

---

## File Discovery

**Technique**

```
T1083
```

Commands

Windows

```cmd
dir
```

Linux

```bash
find /
```

---

## Network Discovery

**Technique**

```
T1046
```

Example

```bash
nmap -A TARGET
```

---

## Privilege Escalation

Examples

- SUID Binaries
- Weak Services
- Token Impersonation
- AlwaysInstallElevated

Common Techniques

```
T1548
```

---

## Persistence

Examples

- Scheduled Tasks
- Registry Run Keys
- Cron Jobs
- SSH Keys

---

## Defense Evasion

Examples

- Clear Event Logs
- Delete Bash History
- Rootkits
- Timestomping

---

# MITRE ATT&CK and CEH Tools

| Tool | ATT&CK Usage |
|------|--------------|
| Hydra | Brute Force |
| John the Ripper | Credential Access |
| Hashcat | Credential Access |
| Metasploit | Execution |
| Meterpreter | Post Exploitation |
| WinPEAS | Discovery |
| LinPEAS | Discovery |
| Mimikatz | Credential Dumping |
| Nmap | Discovery |
| GTFOBins | Privilege Escalation |

---

# Why Learn MITRE ATT&CK?

- Improves threat hunting
- Helps SOC analysts investigate attacks
- Maps attacker behavior
- Improves detection engineering
- Widely used in enterprise security

---

# Interview Questions

### What is MITRE ATT&CK?

A knowledge base that documents real-world adversary tactics, techniques, and procedures (TTPs).

---

### Which ATT&CK technique represents Brute Force?

```
T1110
```

---

### Which technique is used for Credential Dumping?

```
T1003
```

---

### Which ATT&CK tactic includes privilege escalation?

**Privilege Escalation**

---

### Why is MITRE ATT&CK important?

It helps security professionals understand, detect, and defend against attacker behavior.

---

# CEH Exam Tips

✔ Understand the relationship between CEH attack techniques and MITRE ATT&CK.

✔ Focus on commonly tested techniques such as:
- T1110 (Brute Force)
- T1003 (Credential Dumping)
- T1087 (Account Discovery)
- T1082 (System Discovery)

✔ MITRE knowledge is especially valuable for SOC, Blue Team, and Threat Hunting roles.

---

# Key Takeaways

- MITRE ATT&CK provides a standardized way to classify attacker behavior.
- Most techniques covered in CEH Module 06 map directly to ATT&CK techniques.
- Understanding ATT&CK improves both offensive and defensive cybersecurity skills.
- Knowledge of ATT&CK is highly valued in SOC, Threat Hunting, and Incident Response roles.

---

## Related Notes

- `01-System-Hacking-Workflow.md`
- `10-Privilege-Escalation-Windows.md`
- `11-Privilege-Escalation-Linux.md`
- `17-System-Hacking-Tools.md`
- `20-Cheat-Sheet.md`
