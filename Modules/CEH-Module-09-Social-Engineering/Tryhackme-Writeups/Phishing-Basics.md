# TryHackMe — "Phishing Basics" Walkthrough

**Platform:** TryHackMe

**Difficulty:** Easy

**Category:** Social Engineering / Phishing

**Status:** Completed

---

# Overview

This room introduces phishing from the perspective of an ethical hacker and penetration tester. Rather than exploiting technical vulnerabilities, phishing targets human psychology through carefully crafted messages and deceptive content.

The room covers:

* Fundamentals of phishing
* Psychology behind social engineering
* Common phishing attack types
* Email and URL manipulation techniques
* Anatomy of a phishing campaign
* Overview of phishing frameworks
* Practical laboratory demonstration using a controlled environment

> **Disclaimer**
>
> All activities were performed inside the TryHackMe laboratory for educational purposes only. The techniques discussed should only be used with explicit authorization during security assessments.

---

# Learning Objectives

After completing this room, I understood:

* What phishing is
* Why phishing remains effective
* Different phishing attack types
* Human psychology used in attacks
* URL and email manipulation concepts
* Credential harvesting theory
* Phishing campaign lifecycle
* Common phishing frameworks used during security assessments

---

# Task 1 — Introduction

## Key Concepts

Modern organizations often invest heavily in firewalls, endpoint protection, intrusion detection systems, and access controls.

However, one of the most common attack vectors remains:

> **The Human Element**

Instead of attacking systems directly, attackers manipulate people into:

* Clicking malicious links
* Opening attachments
* Revealing credentials
* Installing malware
* Approving unauthorized actions

This makes phishing one of the most common initial access techniques.

---

# Task 2 — Phishing Fundamentals

## What is Phishing?

Phishing is a social engineering attack where an attacker impersonates a trusted entity to convince victims to perform actions that compromise security.

Typical objectives include:

* Credential theft
* Financial fraud
* Malware delivery
* Initial network access
* Information disclosure

---

## Types of Phishing

### Phishing

Mass email campaigns targeting many users.

Characteristics

* Generic message
* Large audience
* Low personalization

---

### Spear Phishing

Highly targeted attack against a specific individual.

Characteristics

* Personalized content
* OSINT-based
* Higher success rate

---

### Whaling

Targets executives or senior management.

Examples

* CEO
* CFO
* Directors
* Finance Heads

Often attempts:

* Wire transfer fraud
* Sensitive document theft
* Executive credential compromise

---

# Task 3 — Psychology Behind Phishing

One of the most valuable sections of the room.

## Social Engineering Principles

### Scarcity

Creates fear of missing an opportunity.

Example:

* Limited offer
* Only a few seats remaining

---

### Urgency

Encourages immediate action.

Examples

* Account expires today
* Password reset required immediately

---

### Authority

Uses trusted positions.

Examples

* HR
* IT Department
* CEO
* Finance Manager

---

### Fear

Creates panic.

Examples

* Security breach
* Unauthorized login
* Account compromise

---

### Curiosity

Encourages victims to discover hidden information.

Examples

* Confidential document
* Salary update
* Secret roadmap

---

### Trust

Impersonates familiar people or organizations.

Examples

* Microsoft
* Google
* Internal employees
* Banks

---

## Cognitive Biases

The room also introduced common decision-making biases.

### Overconfidence Bias

"I would never fall for phishing."

---

### Confirmation Bias

People trust messages matching their expectations.

---

### Authority Bias

People obey authority figures without verification.

---

# Task 4 — Technical Phishing Techniques

## URL Manipulation

Common techniques include:

* URL masking
* Typosquatting
* Homograph attacks
* URL shorteners

Purpose:

* Increase trust
* Hide malicious destinations
* Trick victims into clicking

---

## Email Spoofing

Email spoofing attempts to impersonate legitimate senders.

The room introduced concepts including:

* Display name spoofing
* From field manipulation
* Reply-To abuse
* SMTP limitations

---

## Email Authentication

Modern organizations protect domains using:

* SPF
* DKIM
* DMARC

These technologies help reduce email spoofing.

---

## Credential Harvesting

The room demonstrated how attackers may imitate login pages to collect credentials inside a controlled lab.

Educational focus:

* Understand attacker methodology
* Learn defensive detection
* Recognize suspicious login pages

---

## Payload Delivery

Theoretical overview included:

* Office documents
* Macros
* Benign payload demonstrations
* Execution flow

---

# Task 5 — Anatomy of a Phishing Campaign

A professional phishing engagement generally follows five phases.

## 1. Planning

Define:

* Scope
* Objectives
* Authorization
* Rules of engagement

---

## 2. Reconnaissance

Gather public information using OSINT.

Possible sources:

* LinkedIn
* Company website
* Press releases
* Social media

---

## 3. Scenario Development

Develop realistic but harmless phishing simulations.

Examples:

* HR announcements
* Password expiration notices
* Internal policy updates

---

## 4. Execution

Monitor campaign metrics including:

* Email opens
* Link clicks
* Simulated credential submissions
* User reports

---

## 5. Reporting

Present findings without identifying individuals.

Typical recommendations:

* Security awareness training
* Multi-factor authentication
* Improved email authentication
* Regular phishing simulations

---

# Task 6 — Practical Laboratory

The practical exercise demonstrated a controlled phishing simulation inside the TryHackMe lab.

### Lab Objectives

* Explore a phishing simulation workflow
* Observe how credential harvesting works in a safe environment
* Understand phishing infrastructure from a defender's perspective

### Skills Practiced

* Navigating a phishing simulation framework
* Understanding phishing landing pages
* Observing simulated credential collection
* Reviewing campaign workflow

> No real systems or users were targeted. All activities remained within the authorized training environment.

---

# Key Tools Introduced

## GoPhish

Purpose

* Phishing campaign management
* Email templates
* Analytics
* Tracking

---

## Social Engineering Toolkit (SET)

Purpose

* Security awareness demonstrations
* Controlled phishing simulations
* Social engineering education

---

## Evilginx (Conceptual)

Purpose

* Reverse proxy framework
* Advanced phishing research
* Session interception concepts

---

# Skills Gained

After completing this room I can now understand:

* Phishing methodology
* Social engineering principles
* Human attack surface
* Email spoofing concepts
* URL manipulation
* Credential harvesting theory
* Phishing campaign planning
* Security awareness best practices

---

# Key Takeaways

* Humans remain one of the largest security attack surfaces.
* Effective phishing relies more on psychology than technology.
* OSINT significantly improves targeted phishing realism.
* Modern email authentication reduces spoofing risks.
* Regular phishing simulations help organizations improve security awareness.
* Security awareness training is one of the strongest defenses against phishing attacks.

---

# MITRE ATT&CK Mapping

| Tactic               | Technique                                     |
| -------------------- | --------------------------------------------- |
| Initial Access       | Phishing                                      |
| Initial Access       | Spearphishing Link                            |
| Initial Access       | Spearphishing Attachment                      |
| Credential Access    | Input Capture (Credential Collection Concept) |
| Reconnaissance       | Gather Victim Identity Information            |
| Resource Development | Acquire Infrastructure (Conceptual)           |

---

# Defensive Recommendations

* Enable Multi-Factor Authentication (MFA)
* Deploy SPF, DKIM, and DMARC
* Conduct regular phishing simulations
* Train employees to verify URLs
* Encourage prompt reporting of suspicious emails
* Implement email security gateways
* Monitor authentication logs
* Apply least-privilege access controls

---

# References

* OWASP
* MITRE ATT&CK
* NIST Security Awareness Guidance
* TryHackMe Phishing Room
* Social Engineering Toolkit Documentation
* GoPhish Documentation

---

# Conclusion

This room provided an excellent introduction to phishing from both offensive and defensive perspectives. It demonstrated how attackers leverage psychology, reconnaissance, and deception to gain initial access, while emphasizing the importance of ethical testing, user awareness, and layered defensive controls in reducing organizational risk.
