# DoS-vs-DDoS-CheatSheet.md

# CEH v13 – Module 10

# DoS vs DDoS Cheat Sheet

---

# Quick Definition

## Denial of Service (DoS)

A **Denial of Service (DoS)** attack is launched from a **single attacking machine** with the objective of making a system, application, or network unavailable to legitimate users.

---

## Distributed Denial of Service (DDoS)

A **Distributed Denial of Service (DDoS)** attack is launched from **multiple compromised systems (Botnets)** simultaneously, making it much more powerful and difficult to defend against.

---

# DoS vs DDoS Comparison

| Feature          | DoS           | DDoS             |
| ---------------- | ------------- | ---------------- |
| Attack Source    | Single System | Multiple Systems |
| Traffic Volume   | Low to Medium | Very High        |
| Detection        | Easier        | More Difficult   |
| Blocking         | Easier        | Complex          |
| Uses Botnet      | No            | Yes              |
| IP Addresses     | One/Few       | Thousands        |
| Impact           | Moderate      | Severe           |
| Cost to Attacker | Low           | Higher           |

---

# CIA Triad Mapping

| Security Principle | Impact           |
| ------------------ | ---------------- |
| Confidentiality    | ❌                |
| Integrity          | ❌                |
| Availability       | ✅ Primary Target |

---

# Common DoS Attack Types

### TCP SYN Flood

* Exploits TCP Three-Way Handshake
* Creates Half-Open Connections
* Exhausts Server Resources

---

### UDP Flood

* Massive UDP Packets
* Consumes CPU
* Consumes Bandwidth

---

### ICMP Flood

* Ping Flood
* High Network Traffic
* Service Slowdown

---

### HTTP Flood

* Targets Web Applications
* Uses Legitimate HTTP Requests
* Hard to Detect

---

### Slowloris

* Opens Many HTTP Connections
* Sends Partial Requests Slowly
* Exhausts Web Server Connections

---

### Ping of Death

* Oversized ICMP Packets
* Crashes Vulnerable Systems

---

### Smurf Attack

* Uses ICMP Broadcast
* IP Spoofing
* Traffic Amplification

---

### DNS Amplification

* Small DNS Query
* Large DNS Response
* Reflection Attack

---

### NTP Amplification

* Abuses NTP Servers
* High Amplification Factor

---

### Memcached Amplification

* Extremely Large Responses
* One of the Largest Recorded DDoS Techniques

---

# Botnet

## Definition

A **Botnet** is a collection of compromised computers or IoT devices remotely controlled by an attacker through a Command and Control (C2) server.

---

## Botnet Uses

* DDoS
* Spam
* Malware Distribution
* Credential Stuffing
* Cryptocurrency Mining

---

# Reflection Attack

## Concept

Traffic is reflected through a legitimate server.

Example:

```text
Attacker
     │
     ▼
DNS Server
     │
     ▼
Victim
```

Examples:

* DNS Reflection
* NTP Reflection
* SSDP Reflection

---

# Amplification Attack

## Concept

Small Request → Huge Response

Goal:

Generate maximum traffic using minimum attacker bandwidth.

Protocols:

* DNS
* NTP
* Memcached
* CLDAP

---

# Attack Layers

| Layer             | Example       |
| ----------------- | ------------- |
| Network Layer     | SYN Flood     |
| Network Layer     | UDP Flood     |
| Network Layer     | ICMP Flood    |
| Network Layer     | Smurf         |
| Network Layer     | Ping of Death |
| Application Layer | HTTP Flood    |
| Application Layer | Slowloris     |
| Application Layer | Slow POST     |

---

# Symptoms of DoS Attack

* Slow Network
* High CPU Usage
* High Memory Usage
* Connection Timeouts
* Packet Loss
* Increased Latency
* Web Service Unavailable

---

# Detection Methods

* Firewall Logs
* IDS / IPS
* SIEM
* Wireshark
* tcpdump
* NetFlow
* Zeek
* Suricata
* Snort

---

# Prevention Techniques

* Firewalls
* ACLs
* Rate Limiting
* Load Balancers
* CDN
* Web Application Firewall (WAF)
* DDoS Protection Service
* Traffic Filtering
* Anycast Routing
* Redundant Infrastructure

---

# CEH Exam Points

✅ DoS = Single Source

✅ DDoS = Multiple Sources

✅ Botnet = Compromised Devices

✅ SYN Flood = Half-Open Connections

✅ HTTP Flood = Application Layer

✅ Slowloris = Slow HTTP Headers

✅ Smurf = ICMP Broadcast

✅ DNS Amplification = Reflection Attack

✅ Availability = Main Target

---

# Frequently Asked Interview Questions

### Q1. Difference between DoS and DDoS?

**Answer:**

DoS originates from one attacking machine, whereas DDoS uses multiple compromised devices (botnets), making it more difficult to detect and mitigate.

---

### Q2. Which CIA principle is affected?

Availability.

---

### Q3. What is a Botnet?

A network of compromised systems remotely controlled by an attacker to perform malicious activities such as DDoS attacks.

---

### Q4. Why is DDoS difficult to stop?

Because attack traffic originates from thousands of distributed systems instead of a single source.

---

### Q5. Name three Application Layer attacks.

* HTTP Flood
* Slowloris
* Slow POST

---

# One-Line Revision

> **DoS = One Attacker** | **DDoS = Thousands of Attackers (Botnet)** | **Goal = Disrupt Availability**
