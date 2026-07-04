# System Hacking Tools

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Learn the most common tools used during the System Hacking phase of an authorized penetration test.

---

# System Hacking Lifecycle

```text
Enumeration
      │
      ▼
Password Attacks
      │
      ▼
Exploitation
      │
      ▼
Privilege Escalation
      │
      ▼
Persistence
      │
      ▼
Post Exploitation
```

---

# Popular System Hacking Tools

| Tool | Purpose |
|------|---------|
| Hydra | Online password attacks |
| John the Ripper | Offline password cracking |
| Hashcat | GPU password cracking |
| Metasploit | Exploitation Framework |
| Meterpreter | Post Exploitation |
| Mimikatz | Windows credential extraction |
| WinPEAS | Windows enumeration |
| LinPEAS | Linux enumeration |
| Seatbelt | Windows security enumeration |
| PowerUp | Windows privilege escalation |
| Nmap | Network & service scanning |
| GTFOBins | Linux privilege escalation reference |

---

# Hydra

**Purpose**

- Online password brute force
- Dictionary attacks
- Credential attacks

Example

```bash
hydra -l admin -P rockyou.txt ssh://TARGET
```

Supports

- SSH
- FTP
- HTTP
- RDP
- SMB
- MySQL
- PostgreSQL
- Telnet

---

# John the Ripper

**Purpose**

- Offline password cracking

Example

```bash
john hashes.txt
```

Show Cracked Passwords

```bash
john --show hashes.txt
```

---

# Hashcat

**Purpose**

- GPU-accelerated password cracking

Example

```bash
hashcat -m 0 hash.txt rockyou.txt
```

Common Modes

| Mode | Hash Type |
|------|-----------|
| 0 | MD5 |
| 1000 | NTLM |
| 1800 | SHA512crypt |
| 5600 | NetNTLMv2 |

---

# Metasploit Framework

**Purpose**

- Exploitation
- Payload generation
- Post exploitation

Start

```bash
msfconsole
```

Search Module

```bash
search smb
```

---

# Meterpreter

**Purpose**

- Advanced post-exploitation shell

Useful Commands

```bash
sysinfo

getuid

shell

hashdump

screenshot
```

---

# Mimikatz

**Purpose**

- Credential extraction
- Password hashes
- Kerberos tickets

Common Modules

- sekurlsa
- kerberos
- lsadump

> Use only in authorized lab or assessment environments.

---

# WinPEAS

**Purpose**

- Windows privilege escalation enumeration

Run

```cmd
winPEAS.exe
```

Finds

- Weak permissions
- Services
- Credentials
- Registry issues
- Privilege escalation paths

---

# LinPEAS

**Purpose**

- Linux privilege escalation enumeration

Run

```bash
./linpeas.sh
```

Finds

- SUID binaries
- Writable files
- Cron jobs
- Capabilities
- Misconfigurations

---

# Seatbelt

**Purpose**

- Windows security enumeration

Example

```cmd
Seatbelt.exe
```

---

# PowerUp

**Purpose**

- PowerShell privilege escalation checks

Example

```powershell
Invoke-AllChecks
```

---

# Nmap

**Purpose**

- Port scanning
- Service detection
- OS detection
- Enumeration

Example

```bash
nmap -A TARGET
```

---

# GTFOBins

**Purpose**

- Linux privilege escalation reference

Website

```
https://gtfobins.github.io
```

Useful Binaries

- nmap
- find
- vim
- bash
- tar
- less
- cp

---

# Tool Categories

| Category | Tools |
|----------|-------|
| Enumeration | Nmap, WinPEAS, LinPEAS, Seatbelt |
| Password Attacks | Hydra, John, Hashcat |
| Exploitation | Metasploit |
| Post Exploitation | Meterpreter |
| Credential Access | Mimikatz |
| Privilege Escalation | GTFOBins, PowerUp, WinPEAS, LinPEAS |

---

# Best Practices

✔ Choose the right tool for the task.

✔ Verify findings manually.

✔ Keep tools updated.

✔ Document commands and outputs.

✔ Use tools only with proper authorization.

---

# Interview Questions

### Which tool performs online password attacks?

**Hydra**

---

### Which tool cracks password hashes offline?

**John the Ripper**

---

### Which tool uses GPU acceleration?

**Hashcat**

---

### Which framework is used for exploitation?

**Metasploit Framework**

---

### Which tool is used for Linux privilege escalation enumeration?

**LinPEAS**

---

### Which tool is commonly used to dump Windows credentials?

**Mimikatz**

---

# CEH Exam Tips

- Understand the purpose of each tool rather than memorizing commands.
- Learn when to use online vs. offline password cracking tools.
- Be familiar with WinPEAS, LinPEAS, Metasploit, and Meterpreter.
- Practice these tools in TryHackMe, Hack The Box, and VulnHub labs.

---

# Key Takeaways

- System hacking requires different tools for each phase of an engagement.
- Enumeration tools identify weaknesses, exploitation tools gain access, and post-exploitation tools help assess impact.
- Selecting the appropriate tool improves efficiency and accuracy during penetration testing.
- Mastering these tools is essential for CEH practical labs and real-world assessments.

---

## Related Notes

- `05-Hydra-Cheat-Sheet.md`
- `06-John-the-Ripper.md`
- `07-Hashcat-Basics.md`
- `08-Metasploit-System-Hacking.md`
- `09-Meterpreter-Commands.md`
- `20-Cheat-Sheet.md`
