# Day 06 Journal

Date: 01/06/2026

## Topics Covered

* Kali Linux setup on VMware
* Windows 7 victim machine setup
* NAT network configuration
* Host discovery using Netdiscover
* Host discovery using ARP-Scan
* Nmap port scanning
* Service version detection
* Vulnerability scanning using Nmap NSE
* Understanding MS17-010 vulnerability
* Exploitation workflow demonstration
* Meterpreter session interaction
* Process enumeration concepts
* Process migration concepts
* Credential access concepts
* File system interaction concepts

---

## What I Learned

Today I learned how attackers and security professionals identify systems within a network and gather information about them. I used Netdiscover and ARP-Scan to locate active hosts, followed by Nmap to discover services and identify potential vulnerabilities.

I also learned how vulnerability assessment helps security professionals identify weaknesses before attackers exploit them. The lab demonstrated the lifecycle from reconnaissance to validation in a safe environment.

---

## Challenges Faced

* Setting up VMware networking correctly.
* Understanding the difference between host discovery and port scanning.
* Interpreting Nmap scan results.

---

## Key Commands Practiced

```bash
netdiscover

arp-scan -l

nmap <ip>

nmap -sV <ip>

nmap --script vuln <ip>
```

---

## Skills Improved

* Linux Command Line
* Network Reconnaissance
* Enumeration
* Vulnerability Assessment
* Documentation

---

## Next Plan

* Complete additional TryHackMe rooms.
* Study CEH Module 03 in detail.
* Practice Nmap enumeration techniques.
* Learn advanced scanning options.

---

## Daily Progress Rating

⭐⭐⭐⭐⭐ (5/5)
