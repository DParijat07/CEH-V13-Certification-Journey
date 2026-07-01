# IEMLabs CEHv13 AI - Class 10 Notes

**Date:** Day 36

---

# Topics Covered

## 1. Introduction to OWASP Top 10

### What is OWASP?

OWASP (Open Worldwide Application Security Project) is a non-profit organization focused on improving software security. One of its most popular resources is the **OWASP Top 10**, a list of the most critical web application security risks.

### Why OWASP Top 10 Matters

* Industry standard for web application security
* Used by penetration testers during web assessments
* Helps developers build secure applications
* Frequently asked in cybersecurity interviews
* Basis for many CEH, eJPT and OSCP web security concepts

### OWASP Top 10 (2025)

| ID  | Vulnerability                          |
| --- | -------------------------------------- |
| A01 | Broken Access Control                  |
| A02 | Security Misconfiguration              |
| A03 | Software Supply Chain Failures         |
| A04 | Cryptographic Failures                 |
| A05 | Injection                              |
| A06 | Insecure Design                        |
| A07 | Authentication Failures                |
| A08 | Software or Data Integrity Failures    |
| A09 | Security Logging and Alerting Failures |
| A10 | Mishandling of Exceptional Conditions  |

---

# 2. Web Directory Enumeration

## Objective

Discover hidden directories and files that are not linked from the website but are still accessible.

### Why Directory Enumeration?

* Discover admin panels
* Backup files
* Login pages
* Configuration files
* Sensitive directories
* Development environments
* API endpoints

---

## Gobuster Introduction

Gobuster is a fast directory and file brute-forcing tool written in Go.

### Basic Syntax

```bash
gobuster dir -u http://TARGET-IP -w WORDLIST
```

---

### Common Command

```bash
gobuster dir \
-u http://192.168.x.x \
-w /usr/share/wordlists/dirb/common.txt
```

---

### Ignore Specific Status Codes

```bash
gobuster dir \
-u http://TARGET-IP \
-w /usr/share/wordlists/dirb/common.txt \
-b 404
```

---

### Add File Extensions

```bash
gobuster dir \
-u http://TARGET-IP \
-w wordlist.txt \
-x php,html,txt
```

---

### Useful Options

| Option | Purpose                |
| ------ | ---------------------- |
| -u     | Target URL             |
| -w     | Wordlist               |
| -x     | File extensions        |
| -t     | Number of threads      |
| -o     | Save output            |
| -b     | Blacklist status codes |
| -k     | Ignore SSL certificate |

---

## Common Wordlists

```
/usr/share/wordlists/dirb/common.txt

/usr/share/wordlists/dirbuster/

SecLists
```

---

# 3. Wireshark Review

## Purpose

Wireshark is a network protocol analyzer used to capture and inspect network traffic in real time.

### Activities Reviewed

* Packet capture
* Protocol identification
* Packet inspection
* Applying filters
* Traffic analysis

---

## Important Protocols Observed

* ICMP
* TCP
* UDP
* HTTP
* DNS
* ARP

---

# 4. Analyzing Nmap Traffic in Wireshark

The instructor demonstrated how different Nmap scan techniques generate different packet patterns.

### Example Workflow

1. Start packet capture.
2. Run Nmap scan.
3. Stop capture.
4. Analyze packets.
5. Identify scanning behavior.

---

## Packet Types Observed

* SYN packets
* SYN/ACK responses
* RST packets
* ICMP packets
* TCP handshake

---

## Example Filters

ICMP

```
icmp
```

TCP

```
tcp
```

HTTP

```
http
```

DNS

```
dns
```

Specific IP

```
ip.addr == 192.168.x.x
```

---

# 5. ICMP (Ping) Traffic Analysis

Observed how ping works.

Request

```
Echo Request
```

Response

```
Echo Reply
```

Useful filter

```
icmp
```

Learning points

* RTT observation
* Packet size
* Source and destination
* Connectivity verification

---

# Practical Skills Learned

* Introduction to OWASP Top 10
* Web directory enumeration
* Using Gobuster
* Packet analysis with Wireshark
* Reading ICMP traffic
* Understanding Nmap scanning packets
* Applying Wireshark filters

---

# Commands Practiced

```bash
gobuster dir -u http://TARGET-IP -w /usr/share/wordlists/dirb/common.txt
```

```bash
gobuster dir -u http://TARGET-IP -w wordlist.txt -x php,html
```

```bash
ping TARGET-IP
```

```bash
nmap TARGET-IP
```

---

# Key Takeaways

* OWASP Top 10 is essential knowledge for web penetration testing.
* Directory enumeration is a critical reconnaissance step.
* Gobuster helps discover hidden resources efficiently.
* Wireshark provides visibility into network communications.
* Understanding packet flow improves network troubleshooting and detection capabilities.
* Observing Nmap traffic helps differentiate various scanning techniques from normal network activity.

---

# Homework / Self Practice

* Practice Gobuster against lab web applications.
* Review all OWASP Top 10 categories.
* Capture and analyze Ping traffic in Wireshark.
* Capture and analyze Nmap scan traffic.
* Experiment with different Wireshark display filters.
* Continue documenting practical labs for GitHub.
