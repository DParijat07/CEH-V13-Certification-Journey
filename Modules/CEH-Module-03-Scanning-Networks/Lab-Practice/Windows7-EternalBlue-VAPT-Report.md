# Vulnerability Assessment and Penetration Testing Report

## Project Title

Windows 7 SMB Vulnerability Assessment and Exploitation Lab

---

## Executive Summary

A vulnerability assessment was performed against a Windows 7 virtual machine in a controlled lab environment.

The assessment identified an SMB-related vulnerability associated with MS17-010 (EternalBlue), which could allow unauthorized remote code execution.

The objective was to understand the vulnerability lifecycle from discovery to validation in an isolated educational environment.

---

## Scope

### Target

* Windows 7 Virtual Machine

### Attacker System

* Kali Linux

### Network

* NAT Network

---

## Methodology

### 1. Host Discovery

Tools:

* Netdiscover
* ARP-Scan

Objective:

* Identify active hosts on the network.

---

### 2. Port Scanning

Tool:

* Nmap

Objective:

* Discover open ports and services.

Findings:

* TCP/445 open
* SMB service running

---

### 3. Service Enumeration

Tool:

* Nmap Service Version Detection

Objective:

* Identify operating system and service versions.

Findings:

* Windows 7 Host
* SMB Service

---

### 4. Vulnerability Assessment

Tool:

* Nmap NSE Vulnerability Scripts

Objective:

* Detect known vulnerabilities.

Finding:

* MS17-010 SMB Vulnerability

Severity:

* Critical

CVSS:

* 9.8

---

### 5. Exploitation Validation

Tool:

* Metasploit Framework

Objective:

* Validate vulnerability existence.

Result:

* Successful remote access obtained in a controlled environment.

---

## Risk Assessment

### Vulnerability

MS17-010 (EternalBlue)

### Impact

* Remote Code Execution
* Unauthorized System Access
* Credential Theft
* Lateral Movement
* Full System Compromise

### Severity

Critical

---

## Evidence Summary

| Phase                   | Status     |
| ----------------------- | ---------- |
| Host Discovery          | Successful |
| Port Discovery          | Successful |
| Service Enumeration     | Successful |
| Vulnerability Detection | Successful |
| Exploit Validation      | Successful |

---

## Remediation

1. Apply Microsoft security patches.
2. Disable SMBv1.
3. Restrict SMB exposure.
4. Implement network segmentation.
5. Deploy endpoint protection.
6. Conduct regular vulnerability assessments.

---

## Conclusion

The assessment successfully identified and validated a critical SMB vulnerability in a Windows 7 system. This project demonstrates the complete VAPT workflow including discovery, enumeration, vulnerability identification, validation, and remediation planning.

---

## Skills Demonstrated

* Host Discovery
* Network Enumeration
* Nmap Scanning
* Vulnerability Assessment
* Metasploit Usage
* Report Writing
* Risk Analysis
* Remediation Planning
