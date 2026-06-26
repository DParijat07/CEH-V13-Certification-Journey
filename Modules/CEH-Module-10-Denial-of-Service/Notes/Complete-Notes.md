# Module 10 – Denial of Service (DoS)

## CEH v13 Complete Notes

> **Module:** 10 – Denial of Service (DoS)
> **Certification:** Certified Ethical Hacker (CEH) v13
> **Category:** Network Security / Availability Attacks

---

# Learning Objectives

After completing this module, you should be able to:

* Understand the concept of Denial of Service (DoS).
* Differentiate between DoS and Distributed Denial of Service (DDoS).
* Identify different types of DoS attacks.
* Understand botnets and amplification attacks.
* Learn DoS attack lifecycle.
* Identify indicators of DoS attacks.
* Understand mitigation and defensive techniques.
* Perform basic traffic analysis during DoS attacks.

---

# What is Denial of Service (DoS)?

A **Denial of Service (DoS)** attack is an attempt to make a computer system, server, application, or network unavailable to legitimate users by overwhelming its resources or exploiting protocol weaknesses.

The primary security objective targeted is:

> **Availability** (CIA Triad)

---

# CIA Triad Mapping

| Principle       | Effect               |
| --------------- | -------------------- |
| Confidentiality | ❌ Not primary target |
| Integrity       | ❌ Usually unaffected |
| Availability    | ✅ Primary target     |

---

# Types of DoS Attacks

## 1. Volume-Based Attacks

Flood the target with massive traffic.

Examples:

* UDP Flood
* ICMP Flood
* DNS Amplification
* NTP Amplification

---

## 2. Protocol Attacks

Exploit weaknesses in network protocols.

Examples:

* TCP SYN Flood
* Ping of Death
* Smurf Attack
* Fragmentation Attack

---

## 3. Application Layer Attacks

Target application services instead of bandwidth.

Examples:

* HTTP Flood
* Slowloris
* Slow POST
* DNS Query Flood

---

# DoS vs DDoS

| DoS                      | DDoS                          |
| ------------------------ | ----------------------------- |
| Single attacking machine | Multiple attacking machines   |
| Easier to block          | Difficult to mitigate         |
| Lower traffic volume     | Extremely high traffic volume |
| Limited impact           | Massive impact                |
| Easier attribution       | Harder attribution            |

---

# Distributed Denial of Service (DDoS)

A DDoS attack uses hundreds or thousands of compromised devices (botnet) to attack a single target simultaneously.

Characteristics:

* Large-scale attack
* Distributed sources
* Difficult to block
* High bandwidth consumption

---

# Botnet

A **Botnet** is a collection of compromised systems (bots or zombies) remotely controlled by an attacker through a Command and Control (C2) infrastructure.

Common Botnet Uses:

* DDoS attacks
* Spam campaigns
* Credential stuffing
* Malware distribution
* Cryptocurrency mining

---

# Common DoS Attack Techniques

## TCP SYN Flood

### Concept

The attacker sends numerous TCP SYN packets but never completes the TCP three-way handshake.

Result:

* Half-open connections
* Server resource exhaustion
* Legitimate users denied service

---

## UDP Flood

The attacker sends massive UDP packets to random ports.

Effects:

* High CPU utilization
* Bandwidth exhaustion
* Network congestion

---

## ICMP Flood (Ping Flood)

Large numbers of ICMP Echo Requests overwhelm the target.

Effects:

* Network congestion
* Increased CPU usage

---

## Ping of Death

Oversized malformed ICMP packets crash vulnerable systems.

Modern systems are generally patched against this attack.

---

## Smurf Attack

The attacker sends spoofed ICMP requests to a broadcast address.

All hosts reply to the spoofed victim, amplifying traffic.

---

## HTTP Flood

Targets web servers using legitimate-looking HTTP requests.

Characteristics:

* Difficult to detect
* Mimics real user behavior
* Targets web applications

---

## Slowloris Attack

Keeps many HTTP connections open by sending partial requests very slowly.

Effects:

* Connection exhaustion
* Minimal attacker bandwidth
* Effective against web servers

---

# Reflection and Amplification Attacks

These attacks exploit legitimate servers to amplify attack traffic.

Examples:

* DNS Amplification
* NTP Amplification
* SSDP Amplification
* Memcached Amplification

Advantages for attackers:

* Traffic amplification
* Source IP hiding
* High attack efficiency

---

# Symptoms of a DoS Attack

Indicators include:

* Slow network performance
* High bandwidth usage
* Service unavailability
* Frequent connection timeouts
* Increased CPU utilization
* Memory exhaustion
* Large numbers of half-open TCP sessions

---

# Detection Methods

Security teams detect DoS attacks using:

* IDS/IPS
* SIEM platforms
* Network monitoring tools
* Firewall logs
* NetFlow analysis
* Wireshark packet analysis
* Performance monitoring

---

# Common Defensive Measures

## Network-Level Protection

* Firewalls
* Rate limiting
* Access Control Lists (ACLs)
* Traffic filtering

---

## Infrastructure Protection

* Load balancing
* Redundant servers
* High Availability clusters
* Content Delivery Networks (CDNs)

---

## Application Protection

* Web Application Firewall (WAF)
* CAPTCHA
* Request throttling
* Session limits

---

## DDoS Protection Services

Organizations often rely on cloud-based mitigation services capable of absorbing and filtering malicious traffic before it reaches the target infrastructure.

---

# Incident Response During DoS

1. Detect unusual traffic.
2. Verify attack indicators.
3. Identify attack vector.
4. Enable mitigation controls.
5. Block malicious traffic where possible.
6. Monitor service recovery.
7. Document the incident.
8. Perform post-incident review.

---

# CEH Exam Tips

Remember:

* DoS targets **Availability**.
* DDoS involves multiple compromised systems.
* SYN Flood exploits the TCP handshake.
* Slowloris targets HTTP connections.
* Amplification attacks abuse legitimate services.
* Botnets are commonly used for DDoS campaigns.

---

# Real-World Examples

* Mirai Botnet
* Dyn DNS DDoS Attack (2016)
* GitHub Memcached DDoS Attack
* Cloudflare DDoS Case Studies

---

# MITRE ATT&CK Mapping

| Technique | Description                |
| --------- | -------------------------- |
| T1498     | Network Denial of Service  |
| T1499     | Endpoint Denial of Service |

---

# Tools Used in DoS Detection

* Wireshark
* tcpdump
* NetFlow Analyzer
* Zeek
* Snort
* Suricata
* Security Information and Event Management (SIEM)

---

# Key Interview Questions

### What is Denial of Service?

A Denial of Service attack attempts to make a service unavailable to legitimate users by exhausting system or network resources.

---

### Difference between DoS and DDoS?

DoS originates from a single source, whereas DDoS is launched simultaneously from many compromised systems (botnets), making it more difficult to mitigate.

---

### What is a Botnet?

A botnet is a network of malware-infected devices controlled remotely by an attacker, often used to conduct DDoS attacks and other malicious activities.

---

### What is a SYN Flood?

A SYN Flood exploits the TCP three-way handshake by creating numerous half-open connections, consuming server resources until legitimate users cannot connect.

---

### Which element of the CIA Triad is affected?

Availability.

---

# Key Takeaways

* DoS attacks primarily target system availability.
* DDoS attacks are significantly more powerful due to distributed attack sources.
* Botnets play a central role in modern DDoS attacks.
* Detection relies on monitoring traffic anomalies and system performance.
* Layered defenses, including firewalls, WAFs, CDNs, and DDoS mitigation services, are essential for protection.

---

# Skills Gained

* Understanding DoS attack methodologies
* Differentiating DoS and DDoS attacks
* Recognizing common attack vectors
* Identifying signs of service disruption
* Applying mitigation and defensive strategies
* Performing basic network traffic analysis
* Understanding the importance of availability in cybersecurity
