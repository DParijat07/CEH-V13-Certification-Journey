# Social Engineering Attack Lifecycle

## Overview

Most social engineering attacks follow a structured process rather than occurring randomly.

Attackers gather information, build trust, manipulate victims, and achieve specific objectives.

---

# Phase 1: Reconnaissance

## Objective

Collect information about the target.

---

## Information Sources

### Public Sources

* Company Websites
* LinkedIn Profiles
* Social Media Accounts
* Press Releases
* GitHub Repositories

### Technical Sources

* Email Formats
* Phone Numbers
* Organizational Structure

---

## Example

An attacker discovers:

```text
Name: John Smith
Role: Finance Manager
Email: john.smith@company.com
Manager: Sarah Jones
```

---

# Phase 2: Target Selection

## Objective

Identify valuable individuals.

---

## Common Targets

* Executives
* HR Personnel
* Finance Teams
* System Administrators
* IT Support Staff

---

## Why?

These individuals often have access to sensitive information or systems.

---

# Phase 3: Relationship Building

## Objective

Gain the victim's trust.

---

## Common Methods

### Impersonation

Pretending to be:

* IT Support
* HR Department
* Vendor
* Manager

### Familiarity

Using information collected during reconnaissance.

---

## Example

```text
Hello John,

I'm contacting you regarding the finance software update discussed by Sarah.
```

The victim may trust the message because it contains familiar information.

---

# Phase 4: Exploitation

## Objective

Convince the victim to perform an action.

---

## Common Actions

* Open an attachment
* Click a malicious link
* Reveal credentials
* Install software
* Transfer money

---

## Example

```text
Please log in immediately to verify your account.
```

---

# Phase 5: Objective Achievement

## Objective

Complete the attack.

---

## Potential Outcomes

### Credential Theft

```text
Victim
    ↓
Fake Login Page
    ↓
Credentials Stolen
```

### Malware Installation

```text
Victim Opens File
       ↓
Malware Installed
```

### Unauthorized Access

```text
Credentials
      ↓
VPN Access
      ↓
Internal Network Access
```

---

# Complete Lifecycle Diagram

```text
Reconnaissance
      ↓
Target Selection
      ↓
Relationship Building
      ↓
Exploitation
      ↓
Objective Achievement
```

---

# Defensive Measures

## During Reconnaissance

* Limit public information exposure.
* Review social media disclosures.

## During Relationship Building

* Verify identities.
* Follow security procedures.

## During Exploitation

* Be cautious of unexpected requests.
* Verify links and attachments.

## After Detection

* Report incidents immediately.
* Reset compromised credentials.
* Conduct incident response activities.

---

# Key Takeaways

* Social Engineering attacks are planned and structured.
* Attackers perform reconnaissance before targeting victims.
* Trust-building is a critical step in the attack process.
* Successful exploitation relies on human interaction.
* Awareness and verification can break the attack lifecycle at multiple stages.
