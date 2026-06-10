# Day15-Journal

**Date:** 10/06/2026

## Daily Summary

Today I attended my **5th CEH training class at IEMLabs**. The session focused on understanding and exploiting vulnerable services running on the **Metasploitable 2** machine using Kali Linux and Metasploit Framework.

---

## Topics Covered in Class

### 1. Host Discovery and Network Enumeration

Before exploitation, I performed network reconnaissance to identify the target machine within my lab environment.

**Tools Used:**

* arp-scan
* netdiscover

**Objective:**

* Discover live hosts on the local network.
* Identify the IP address of the Metasploitable 2 machine.

---

### 2. Port Scanning and Service Enumeration

After identifying the target IP address, I conducted reconnaissance using Nmap.

**Activities Performed:**

* Port scanning
* Service detection
* Version detection

**Objective:**

* Identify open ports.
* Determine running services.
* Detect service versions for vulnerability assessment.

---

### 3. Operating System Identification

Learned a basic technique for identifying operating systems by observing the **TTL (Time To Live)** value from ping responses.

**Examples:**

* TTL ≈ 64 → Linux/Unix systems
* TTL ≈ 128 → Windows systems

**Learning Outcome:**

* Understood how TTL values can provide clues about the target operating system during reconnaissance.

---

### 4. Exploitation Using Metasploit Framework

Introduced to the use of **Metasploit Framework (msfconsole)**.

**Concepts Learned:**

* Auxiliary Modules
* Exploit Modules
* Basic Metasploit workflow

**Targeted Services:**

* Port 21 (FTP)
* Port 22 (SSH)
* Port 23 (Telnet)

**Activities Performed:**

* Searched for relevant Metasploit modules.
* Loaded exploit and auxiliary modules.
* Configured target parameters.
* Executed modules against vulnerable services.

**Learning Outcome:**

* Gained practical exposure to using Metasploit for service exploitation and security testing in a controlled lab environment.

---

## Future Research and Practice Plan

I plan to continue exploring Metasploitable 2 and perform deeper enumeration and vulnerability assessment on the remaining services.

### Areas to Explore

* Service Enumeration
* File Enumeration
* Web Enumeration
* FTP Enumeration
* SSH Enumeration
* Telnet Enumeration
* SMB Enumeration
* Database Enumeration
* SQL Injection Testing
* Web Vulnerability Assessment
* Metasploit Exploitation Modules
* Manual Exploitation Techniques
* Post-Exploitation Fundamentals

### Goal

Successfully enumerate and understand all major services running on Metasploitable 2 while documenting findings in a professional penetration testing style.

---

## Self-Study Activities

### TryHackMe

* Maintained TryHackMe learning streak.
* Continued hands-on cybersecurity practice.

### GitHub

* Maintained GitHub contribution streak.
* Continued documenting cybersecurity learning journey.

### Communication Skills

* Practiced communicative English for **1 hour**.
* Focused on improving speaking confidence and fluency.

---

## Key Learnings of the Day

* Host discovery using arp-scan and netdiscover.
* Service and version enumeration using Nmap.
* Basic OS fingerprinting through TTL analysis.
* Introduction to Metasploit auxiliary and exploit modules.
* Practical exploitation of FTP, SSH, and Telnet services in a lab environment.
* Importance of enumeration before exploitation.

---

## Day Reflection

Today's session strengthened my understanding of the penetration testing methodology: **Reconnaissance → Enumeration → Vulnerability Identification → Exploitation**. Working with Metasploitable 2 and Metasploit Framework provided practical exposure to real-world attack workflows in a safe lab environment. My next objective is to perform deeper service enumeration and explore additional vulnerabilities across the remaining exposed services.

**Status:** ✅ Day 15 Completed
**TryHackMe Streak:** Maintained
**GitHub Streak:** Maintained
**English Practice:** Completed
**CEH Journey Progress:** Ongoing
