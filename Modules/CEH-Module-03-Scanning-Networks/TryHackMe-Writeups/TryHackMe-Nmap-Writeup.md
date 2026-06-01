# TryHackMe Write-Up: Nmap

## Room Name

Nmap

## Platform

TryHackMe

## Difficulty

Easy

---

## Objective

Learn how to use Nmap for:

* Host Discovery
* Port Scanning
* Service Enumeration
* OS Detection
* NSE Script Scanning

---

## Key Concepts Learned

### 1. Basic Scan

```bash
nmap <target>
```

Purpose:

* Discover open ports.

---

### 2. SYN Scan

```bash
nmap -sS <target>
```

Purpose:

* Fast stealth scanning.

---

### 3. Service Version Detection

```bash
nmap -sV <target>
```

Purpose:

* Identify service versions.

---

### 4. Operating System Detection

```bash
nmap -O <target>
```

Purpose:

* Identify operating system.

---

### 5. Aggressive Scan

```bash
nmap -A <target>
```

Includes:

* Version Detection
* OS Detection
* Script Scanning
* Traceroute

---

### 6. NSE Scripts

```bash
nmap --script vuln <target>
```

Purpose:

* Run vulnerability detection scripts.

---

### 7. UDP Scan

```bash
nmap -sU <target>
```

Purpose:

* Discover UDP services.

---

## Important Flags Learned

| Flag     | Purpose             |
| -------- | ------------------- |
| -sS      | SYN Scan            |
| -sV      | Version Detection   |
| -O       | OS Detection        |
| -A       | Aggressive Scan     |
| -Pn      | Skip Host Discovery |
| -p       | Specify Port        |
| -T4      | Faster Scan         |
| --script | Run NSE Scripts     |

---

## Skills Gained

* Reconnaissance
* Enumeration
* Service Detection
* Vulnerability Discovery
* Nmap Scripting Engine Usage

---

## Real-World Relevance

Nmap is one of the most widely used tools by:

* Security Analysts
* SOC Analysts
* Penetration Testers
* Red Teamers
* System Administrators

It is often the first tool used during network assessment and security audits.

---

## Key Takeaways

* Nmap is a powerful reconnaissance tool.
* Enumeration is critical before vulnerability assessment.
* NSE scripts significantly enhance scanning capabilities.
* Understanding services is essential for identifying attack surfaces.

---

## Room Status

✅ Completed Successfully

## Tools Used

* Nmap
* Kali Linux
* TryHackMe Lab Environment
