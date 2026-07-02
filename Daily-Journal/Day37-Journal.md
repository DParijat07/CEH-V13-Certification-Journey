# Day 37 – CEH Journey

**Date:** 02/07/2026
**Day:** 37

---

# Today's Activities

## TryHackMe – Mr. Robot CTF

Today I continued solving the **Mr. Robot** room on TryHackMe using my Kali Linux virtual machine.

### Activities Performed

* Verified connectivity with the target machine.
* Performed reconnaissance using Ping and Nmap.
* Conducted service and version detection.
* Enumerated the web application using Gobuster.
* Analyzed the `robots.txt` file and discovered hidden resources.
* Downloaded the `fsocity.dic` wordlist and obtained the first flag.
* Enumerated the WordPress application.
* Retrieved encoded credentials from the license page and decoded them.
* Successfully authenticated to the WordPress administrator panel.
* Modified the active theme's `404.php` file to obtain an initial reverse shell.
* Triggered the payload by accessing a non-existent page.
* Established a reverse shell using Netcat.
* Performed Linux system enumeration.
* Identified the `robot` user's home directory and recovered an MD5 password hash.
* Cracked the password hash and switched to the `robot` user.
* Captured the second flag.
* Performed privilege escalation enumeration.
* Checked `sudo` privileges.
* Enumerated SUID binaries using the `find` command.
* Identified an SUID-enabled Nmap binary.
* Researched **GTFOBins** to understand the privilege escalation technique.
* Used the vulnerable interactive mode of Nmap to gain root privileges.
* Captured the final flag and successfully completed the room.

---

## Documentation

Started documenting the **Mr. Robot** room professionally.

Planned documentation includes:

* Complete TryHackMe Walkthrough with screenshots.
* Professional VAPT Report.
* Technical notes and learning outcomes.
* CEH Module Mapping.
* MITRE ATT&CK Mapping.

---

## OT / ICS / SCADA Workshop

Today I also attended an introductory workshop covering Industrial Cybersecurity fundamentals.

### Topics Covered

* Introduction to Operational Technology (OT)
* Industrial Control Systems (ICS)
* Supervisory Control and Data Acquisition (SCADA)
* Differences between IT and OT environments
* Basic Industrial Network Architecture
* Importance of Cybersecurity in Critical Infrastructure
* Real-world applications of ICS and SCADA systems

This workshop provided a foundational understanding of industrial cybersecurity and highlighted the growing importance of securing critical infrastructure.

---

## GitHub Progress

* Continued maintaining my daily GitHub contribution streak.
* Updated project documentation with new technical notes.
* Prepared the repository structure for the upcoming Mr. Robot walkthrough and professional VAPT report.

---

# Skills Practiced

* Network Reconnaissance
* Service Enumeration
* Web Enumeration
* WordPress Enumeration
* Reverse Shell Generation
* Linux Post-Exploitation
* Password Hash Analysis
* Linux Privilege Escalation
* GTFOBins Research
* Technical Documentation
* Industrial Cybersecurity Fundamentals

---

# CEH Module Mapping

* **Module 03:** Scanning Networks
* **Module 04:** Enumeration
* **Module 06:** System Hacking

---

# Key Learning Outcomes

* Reinforced the importance of systematic enumeration before exploitation.
* Learned how exposed information can lead to credential compromise.
* Gained practical experience in authenticated WordPress exploitation.
* Understood Linux privilege escalation using SUID misconfigurations and GTFOBins.
* Improved professional documentation practices by separating technical walkthroughs from client-style VAPT reports.
* Built foundational knowledge of OT, ICS, and SCADA environments and their role in critical infrastructure cybersecurity.

---

**Status:** ✅ Productive learning day completed.
