# CEH v13 Module 02 – Footprinting and Reconnaissance

## Overview

Footprinting and Reconnaissance is the first operational phase of ethical hacking. Before attempting to identify vulnerabilities or exploit systems, an ethical hacker gathers as much information as possible about the target. This information helps build a detailed profile of the target organization, reducing uncertainty and improving the effectiveness of later attack phases.

Reconnaissance can be performed passively (without directly interacting with the target) or actively (through direct interaction). Ethical hackers use Open Source Intelligence (OSINT), DNS analysis, WHOIS lookups, search engine techniques, social media intelligence, metadata extraction, and specialized reconnaissance tools to collect valuable information.

Understanding reconnaissance techniques is essential because every penetration test begins with information gathering. The quality of information collected during this phase directly influences the success of subsequent activities such as scanning, enumeration, vulnerability assessment, and exploitation.

---

# Learning Objectives

After completing this module, you should be able to:

- Understand the purpose of footprinting and reconnaissance.
- Differentiate between passive and active reconnaissance.
- Collect publicly available information using OSINT techniques.
- Perform DNS and WHOIS reconnaissance.
- Identify IP address ranges, Autonomous Systems (ASNs), and network ownership.
- Enumerate subdomains and internet-facing assets.
- Use reconnaissance tools such as Maltego, theHarvester, Recon-ng, SpiderFoot, FOCA, Shodan, and Censys.
- Gather information from websites, search engines, GitHub repositories, cloud services, and social media.
- Understand metadata analysis and information leakage.
- Recognize defensive measures that reduce reconnaissance success.

---

# Why Footprinting Matters

Reconnaissance provides attackers and penetration testers with valuable intelligence before interacting with the target.

The information collected may reveal:

- Public IP addresses
- Domain names
- DNS records
- Employee information
- Email addresses
- Network infrastructure
- Cloud services
- Open ports
- Internet-facing servers
- Technology stack
- Security misconfigurations
- Public documents containing metadata

Well-executed reconnaissance often allows attackers to identify weaknesses without directly attacking the target.

---

# Passive vs Active Reconnaissance

## Passive Reconnaissance

Passive reconnaissance collects information without directly communicating with the target.

Examples include:

- Search engines
- WHOIS databases
- Public DNS records
- Company websites
- LinkedIn
- GitHub
- Job advertisements
- Public documents
- Social media

Advantages:

- Difficult to detect
- Low operational risk
- No direct interaction with target systems

---

## Active Reconnaissance

Active reconnaissance involves direct interaction with target systems.

Examples include:

- DNS queries
- Ping sweeps
- Port scanning
- Banner grabbing
- Service enumeration
- Traceroute

Advantages:

- More accurate
- More detailed
- Reveals live infrastructure

Disadvantages:

- Easier to detect
- May trigger IDS/IPS alerts
- Requires authorization during ethical hacking engagements

---

# Module Topics

This module covers:

- Footprinting fundamentals
- Reconnaissance methodology
- Open Source Intelligence (OSINT)
- Search engine footprinting
- Google Dorking
- WHOIS
- DNS footprinting
- DNS records
- Reverse DNS lookups
- DNS Zone Transfers
- IP addressing
- Autonomous Systems (ASN)
- BGP information
- Website footprinting
- Email footprinting
- Metadata extraction
- Employee enumeration
- Social Media Intelligence (SOCMINT)
- GitHub reconnaissance
- Cloud reconnaissance
- Wireless reconnaissance
- Dark web intelligence
- Information leakage
- Countermeasures

---

# Common Reconnaissance Tools

This module introduces a variety of industry-standard reconnaissance tools.

## OSINT Tools

- theHarvester
- Recon-ng
- SpiderFoot
- Maltego
- FOCA

## Internet Intelligence

- Shodan
- Censys
- ZoomEye

## DNS Tools

- dig
- nslookup
- dnsenum
- dnsrecon

## Search Engine Intelligence

- Google Dorks
- Bing Search Operators
- Netcraft
- BuiltWith

---

# Practical Skills You'll Learn

After completing this module, you should be able to:

- Gather organizational information using OSINT.
- Perform DNS reconnaissance.
- Identify public infrastructure.
- Enumerate subdomains.
- Discover exposed internet services.
- Analyze website technologies.
- Extract metadata from documents.
- Identify employee information from public sources.
- Use professional reconnaissance tools.
- Produce a structured reconnaissance report.

---

# Real-World Applications

Footprinting is widely used in:

- Penetration testing
- Red Team operations
- Bug bounty hunting
- Vulnerability assessments
- SOC investigations
- Threat intelligence
- Incident response
- Digital forensics
- Attack surface management

---

# Defensive Perspective

Organizations should reduce information leakage by:

- Limiting publicly exposed information.
- Using WHOIS privacy where appropriate.
- Removing sensitive metadata from documents.
- Restricting unnecessary DNS records.
- Monitoring internet-facing assets.
- Conducting regular attack surface reviews.
- Training employees on social engineering risks.
- Monitoring for exposed credentials and repositories.

---

# CEH Exam Tips

Remember:

- Reconnaissance is the first phase of ethical hacking.
- Passive reconnaissance does not directly interact with the target.
- Active reconnaissance involves communication with target systems.
- OSINT relies on publicly available information.
- DNS and WHOIS are essential sources of reconnaissance data.
- Metadata can unintentionally reveal sensitive information.
- Information gathered during reconnaissance guides later phases such as scanning, enumeration, and exploitation.

---

# Module Summary

Module 02 introduces the information-gathering techniques used at the beginning of every ethical hacking engagement. By combining passive and active reconnaissance methods with OSINT tools, DNS analysis, search engine techniques, and internet intelligence platforms, ethical hackers can build a comprehensive understanding of a target's external attack surface.

Mastering footprinting enables security professionals to identify exposed assets, understand organizational infrastructure, and improve defensive measures before vulnerabilities are exploited.

---

# Recommended Practice

To reinforce the concepts in this module:

- Practice WHOIS lookups on public domains.
- Perform DNS enumeration in a lab environment.
- Explore Shodan and Censys for internet-facing assets.
- Use theHarvester and Recon-ng against test domains.
- Analyze metadata from publicly available PDF and Office documents.
- Review your own online footprint to understand information exposure.

---

# Key Takeaways

- Reconnaissance is the foundation of every successful penetration test.
- Passive reconnaissance minimizes detection by using publicly available information.
- Active reconnaissance provides detailed technical information but is more likely to be detected.
- OSINT, DNS analysis, metadata extraction, and reconnaissance tools help build a complete target profile.
- Reducing public information exposure is a critical defensive strategy against reconnaissance-based attacks.
