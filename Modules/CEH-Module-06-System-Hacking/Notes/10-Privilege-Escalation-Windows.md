# Windows Privilege Escalation

> **Module:** CEH v13 – Module 06 (System Hacking)
>
> **Objective:** Learn common Windows privilege escalation techniques used during authorized penetration tests.

---

# What is Privilege Escalation?

Privilege Escalation is the process of gaining higher privileges after obtaining an initial foothold on a target system.

Example:

```
Low Privileged User

↓

Administrator

↓

SYSTEM
```

---

# Privilege Escalation Workflow

```text
Gain Initial Access
        │
        ▼
System Enumeration
        │
        ▼
Identify Misconfigurations
        │
        ▼
Exploit Weakness
        │
        ▼
Gain Administrator/SYSTEM
        │
        ▼
Post Exploitation
```

---

# Enumeration

Always enumerate before exploiting.

Useful Commands

```cmd
whoami
```

```cmd
hostname
```

```cmd
systeminfo
```

```cmd
ipconfig /all
```

```cmd
net user
```

```cmd
net localgroup administrators
```

```cmd
whoami /priv
```

```cmd
whoami /groups
```

---

# Automated Enumeration Tools

- WinPEAS
- Seatbelt
- PowerUp
- PrivescCheck
- Metasploit Local Exploit Suggester

Example

```cmd
winPEAS.exe
```

---

# Common Privilege Escalation Techniques

- Weak Service Permissions
- Unquoted Service Paths
- DLL Hijacking
- Weak Registry Permissions
- AlwaysInstallElevated
- Scheduled Tasks
- Stored Credentials
- Token Impersonation
- Vulnerable Software
- Misconfigured Services

---

# Weak Service Permissions

If a service executable is writable by a low-privileged user, replace it with a malicious executable and restart the service.

Enumeration

```cmd
sc query
```

```cmd
sc qc ServiceName
```

---

# Unquoted Service Paths

Example

```
C:\Program Files\My App\Service.exe
```

Without quotes, Windows may execute:

```
C:\Program.exe
```

if present.

Check Services

```cmd
wmic service get name,displayname,pathname,startmode
```

---

# AlwaysInstallElevated

Check

```cmd
reg query HKCU\Software\Policies\Microsoft\Windows\Installer
```

```cmd
reg query HKLM\Software\Policies\Microsoft\Windows\Installer
```

If enabled, MSI packages may execute with elevated privileges.

---

# Stored Credentials

View Saved Credentials

```cmd
cmdkey /list
```

---

# Scheduled Tasks

List Scheduled Tasks

```cmd
schtasks /query /fo LIST /v
```

Look for writable scripts or executables.

---

# Token Privileges

View Current Privileges

```cmd
whoami /priv
```

Interesting Privileges

- SeImpersonatePrivilege
- SeAssignPrimaryTokenPrivilege
- SeBackupPrivilege
- SeRestorePrivilege

---

# Credential Dumping (Overview)

Common Tools

- Mimikatz
- Meterpreter hashdump
- Windows Credential Manager

> Only use credential dumping techniques in authorized environments.

---

# Useful Tools

| Tool | Purpose |
|------|----------|
| WinPEAS | Windows Enumeration |
| Seatbelt | System Enumeration |
| PowerUp | Service Checks |
| PrivescCheck | Misconfiguration Scanner |
| Metasploit | Local Exploit Suggestion |

---

# Real Lab Example

## Windows Machine

```cmd
whoami

systeminfo

whoami /priv

net user

winPEAS.exe
```

---

# Best Practices

✔ Enumerate before exploiting.

✔ Check privileges first.

✔ Look for service misconfigurations.

✔ Identify vulnerable software.

✔ Document every step.

---

# Interview Questions

## What is Privilege Escalation?

The process of gaining higher privileges after obtaining initial access.

---

## Which command shows Windows privileges?

```cmd
whoami /priv
```

---

## Which command lists local users?

```cmd
net user
```

---

## Which command displays saved credentials?

```cmd
cmdkey /list
```

---

## Name two Windows privilege escalation tools.

- WinPEAS
- Seatbelt

---

# CEH Exam Tips

✔ Enumeration is the most important step.

✔ Learn common Windows privilege escalation techniques.

✔ Be familiar with WinPEAS and PowerUp.

✔ Understand service misconfigurations and unquoted service paths.

✔ Document findings and recommend remediation.

---

# Key Takeaways

- Windows privilege escalation relies on identifying misconfigurations rather than immediately exploiting vulnerabilities.
- Thorough enumeration is critical for discovering escalation paths.
- Tools like WinPEAS and Seatbelt significantly speed up assessments.
- Proper documentation of findings and remediation recommendations is essential during professional penetration tests.

---

## Related Notes

- `08-Metasploit-System-Hacking.md`
- `09-Meterpreter-Commands.md`
- `11-Privilege-Escalation-Linux.md`
- `14-Post-Exploitation-Checklist.md`
- `20-Cheat-Sheet.md`
