# Search Skills - TryHackMe Write-up

> **Platform:** TryHackMe
> **Room:** Search Skills
> **Learning Path:** Cyber Security 101
> **Mapped CEH Module:** Module 02 – Footprinting & Reconnaissance
> **Difficulty:** Easy
> **Status:** ✅ Completed

---

# Overview

The **Search Skills** room introduces several essential online resources used by cybersecurity professionals for reconnaissance, vulnerability research, malware analysis, and technical documentation. Rather than focusing on attacking systems, this room teaches how to efficiently locate accurate information using trusted security platforms.

Effective research is a fundamental skill for penetration testers, SOC analysts, incident responders, and security researchers.

---

# Learning Objectives

After completing this room, I learned how to:

* Search internet-connected devices using Shodan.
* Analyze suspicious files using VirusTotal.
* Research vulnerabilities using CVE databases.
* Read official technical documentation and Linux manual pages.
* Locate Proof-of-Concept (PoC) code on GitHub.
* Develop efficient information gathering and research skills.

---

# Task 1 – Introduction

The room emphasizes that cybersecurity professionals constantly rely on online resources to gather intelligence during both offensive and defensive security operations.

### Key Learning

* Research skills are as important as technical skills.
* Knowing where to search often saves significant time during investigations.
* Reliable sources improve the accuracy of security assessments.

---

# Task 2 – Shodan (TryScanMe)

## What is Shodan?

Shodan is a search engine that continuously scans internet-connected devices and services. It indexes publicly accessible systems, allowing users to identify exposed servers, IoT devices, industrial control systems, web servers, and networking equipment.

Unlike traditional search engines that index websites, Shodan indexes services running on public IP addresses.

## Information Learned

Shodan can reveal:

* Public IP addresses
* Running services
* Open ports
* Software versions
* Geographic location
* Organization ownership
* Hostnames

## Common Search Filters

| Filter      | Purpose                                        |
| ----------- | ---------------------------------------------- |
| `country:`  | Search devices within a specific country       |
| `port:`     | Search a particular service port               |
| `org:`      | Search systems owned by an organization or ASN |
| `hostname:` | Search by hostname or domain                   |

## Practical Activity

Performed searches using the simulated TryScanMe platform to identify publicly exposed Apache web servers and analyze service information associated with discovered IP addresses.

## Security Relevance

During reconnaissance, Shodan helps identify publicly exposed assets that may contain vulnerable software versions requiring further assessment.

---

# Task 3 – VirusTotal (TryDetectMe)

## What is VirusTotal?

VirusTotal is a threat intelligence platform that scans files, URLs, domains, and hashes using multiple antivirus engines.

Instead of relying on a single antivirus product, VirusTotal aggregates detection results from numerous security vendors.

## Information Learned

VirusTotal can analyze:

* Files
* URLs
* Domains
* IP addresses
* File hashes

## Practical Activity

Used the simulated TryDetectMe interface to analyze a suspicious executable and review the detection results reported by multiple security vendors.

## Security Relevance

VirusTotal assists defenders by:

* Identifying malware
* Validating suspicious files
* Investigating phishing links
* Gathering threat intelligence
* Supporting incident response

---

# Task 4 – Common Vulnerabilities and Exposures (CVE)

## What is CVE?

The Common Vulnerabilities and Exposures (CVE) program provides standardized identifiers for publicly disclosed security vulnerabilities.

Each vulnerability receives a unique identifier such as:

```
CVE-2026-1337
```

## CVSS

The Common Vulnerability Scoring System (CVSS) measures vulnerability severity based on factors including:

* Impact
* Exploitability
* Attack Complexity
* Availability
* Confidentiality
* Integrity

Organizations use CVSS scores to prioritize remediation efforts.

## Practical Activity

Searched for a simulated CVE within the vulnerability database and reviewed its technical description and associated CVSS classification.

## Security Relevance

Security professionals frequently research CVEs to:

* Understand newly disclosed vulnerabilities
* Assess organizational risk
* Identify available patches
* Locate Proof-of-Concept exploits

---

# Task 5 – Technical Documentation (Linux MAN Pages)

## Importance of Documentation

Official documentation is the most reliable source for learning security tools and troubleshooting unexpected behavior.

Rather than depending solely on blogs or tutorials, cybersecurity professionals should consult official documentation whenever possible.

## Linux MAN Pages

Linux manual pages provide built-in documentation for commands and utilities.

General syntax:

```bash
man <command>
```

Example:

```bash
man nc
```

This displays detailed information about the Netcat utility, including syntax, options, and usage examples.

## Practical Activity

Used a simulated MAN page to locate command examples and understand Netcat usage.

## Security Relevance

Reading manual pages helps professionals:

* Learn command syntax
* Understand available options
* Troubleshoot tools
* Improve command-line proficiency

---

# Task 6 – GitHub

## GitHub in Cybersecurity

GitHub is widely used by researchers to publish:

* Proof-of-Concept exploits
* Security tools
* Detection scripts
* Technical documentation
* Research reports

Searching GitHub using a CVE identifier often reveals community-developed resources related to that vulnerability.

## Practical Activity

Reviewed a repository containing a simulated Proof-of-Concept for a fictitious CVE and identified the demonstration script described in the project's README.

## Security Relevance

GitHub is an essential platform for:

* Security research
* Tool development
* Open-source collaboration
* Vulnerability analysis

Security professionals should always verify repositories before executing any downloaded code.

---

# Skills Gained

* Open Source Intelligence (OSINT)
* Information Gathering
* Reconnaissance
* Threat Intelligence
* Vulnerability Research
* Malware Analysis Fundamentals
* Technical Documentation Research
* Linux Command Reference Usage
* Security Research Methodology

---

# CEH Module Mapping

This room aligns closely with **CEH v13 Module 02 – Footprinting & Reconnaissance**.

Topics reinforced include:

* Open Source Intelligence (OSINT)
* Information Gathering
* Public Asset Discovery
* Vulnerability Intelligence
* Threat Research
* Technical Documentation
* Security Research Methodology

---

# Tools & Resources Covered

* Shodan
* VirusTotal
* CVE Database
* CVSS
* Linux MAN Pages
* GitHub

---

# Key Takeaways

* Research is a core cybersecurity skill.
* Public intelligence sources provide valuable information during reconnaissance.
* Official documentation is more reliable than third-party tutorials.
* CVE and CVSS help security teams understand and prioritize vulnerabilities.
* VirusTotal supports malware analysis through multi-engine scanning.
* GitHub is a valuable source for security research and Proof-of-Concept code but repositories should always be validated before use.

---

# Personal Reflection

This room demonstrated that effective cybersecurity professionals spend a significant amount of time researching before performing technical tasks. Learning where to find trustworthy information is essential for penetration testing, vulnerability assessment, incident response, and security operations. Developing strong search skills improves both efficiency and decision-making during security assessments.
