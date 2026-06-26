# MITRE-ATTACK-Mapping.md

# CEH v13 – Module 10

# MITRE ATT&CK Mapping – Denial of Service (DoS)

---

# Overview

The **MITRE ATT&CK Framework** is a globally recognized knowledge base of adversary tactics and techniques based on real-world observations. Although Denial of Service (DoS) is not part of every attack lifecycle, MITRE documents specific techniques related to disrupting system and network availability.

This document maps the concepts covered in **CEH v13 Module 10 – Denial of Service** to the relevant MITRE ATT&CK techniques.

---

# MITRE ATT&CK Tactic

| Tactic     | ATT&CK ID | Description                                                                                                                                                                                                                            |
| ---------- | --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Impact** | TA0040    | Techniques used by adversaries to manipulate, interrupt, or destroy systems and data after gaining or attempting access. Denial of Service techniques fall under this tactic because they aim to disrupt the availability of services. |

---

# Technique 1 – Network Denial of Service

## ATT&CK ID

**T1498**

## Name

**Network Denial of Service**

## Description

Adversaries attempt to prevent access to network services by overwhelming the target with excessive traffic or exploiting weaknesses in network protocols.

---

### Examples

* TCP SYN Flood
* UDP Flood
* ICMP Flood
* DNS Amplification
* NTP Amplification
* Smurf Attack
* Reflection Attacks

---

### Target

* Routers
* Firewalls
* Load Balancers
* Web Servers
* DNS Servers
* Internet Gateways

---

### Detection

* Sudden bandwidth spikes
* Large numbers of SYN packets
* High packet rate
* Excessive ICMP traffic
* NetFlow anomalies
* Firewall alerts
* IDS/IPS alerts

---

### Mitigation

* Firewalls
* ACLs
* Rate Limiting
* DDoS Protection Services
* Anycast Routing
* Traffic Filtering
* CDN
* Load Balancing

---

# Technique 2 – Endpoint Denial of Service

## ATT&CK ID

**T1499**

## Name

**Endpoint Denial of Service**

## Description

Adversaries consume CPU, memory, storage, or application resources on a host to make the endpoint or service unavailable.

---

### Examples

* HTTP Flood
* Slowloris
* Slow POST
* Resource Exhaustion
* Application Layer DoS

---

### Target

* Web Servers
* Application Servers
* Database Servers
* Authentication Servers

---

### Detection

* High CPU utilization
* Memory exhaustion
* Numerous open HTTP sessions
* Slow response time
* Increased application latency
* Error logs

---

### Mitigation

* Web Application Firewall (WAF)
* Request Rate Limiting
* Reverse Proxy
* Load Balancer
* Session Timeout Configuration
* Application Monitoring

---

# CEH Attack Mapping

| CEH Topic             | MITRE Technique |
| --------------------- | --------------- |
| TCP SYN Flood         | T1498           |
| UDP Flood             | T1498           |
| ICMP Flood            | T1498           |
| DNS Amplification     | T1498           |
| NTP Amplification     | T1498           |
| Smurf Attack          | T1498           |
| HTTP Flood            | T1499           |
| Slowloris             | T1499           |
| Slow POST             | T1499           |
| Application Layer DoS | T1499           |

---

# MITRE ATT&CK Matrix Position

```text
Impact (TA0040)
│
├── T1498 – Network Denial of Service
│      ├── SYN Flood
│      ├── UDP Flood
│      ├── ICMP Flood
│      ├── DNS Amplification
│      ├── NTP Amplification
│      └── Smurf Attack
│
└── T1499 – Endpoint Denial of Service
       ├── HTTP Flood
       ├── Slowloris
       ├── Slow POST
       └── Resource Exhaustion
```

---

# Detection Data Sources

| Data Source                          | Why It Matters                           |
| ------------------------------------ | ---------------------------------------- |
| Firewall Logs                        | Detect blocked or excessive traffic      |
| IDS / IPS Alerts                     | Identify attack signatures               |
| NetFlow                              | Observe abnormal traffic volumes         |
| Packet Captures (Wireshark, tcpdump) | Analyze packet patterns                  |
| Web Server Logs                      | Detect excessive HTTP requests           |
| System Logs                          | Identify crashes and resource exhaustion |
| CPU & Memory Monitoring              | Detect endpoint overload                 |
| SIEM                                 | Correlate events from multiple sources   |

---

# Defensive Security Controls

| Security Control        | Purpose                                 |
| ----------------------- | --------------------------------------- |
| Firewall                | Filter malicious traffic                |
| IDS                     | Detect attack patterns                  |
| IPS                     | Detect and block malicious traffic      |
| WAF                     | Protect web applications                |
| CDN                     | Distribute traffic and absorb attacks   |
| Load Balancer           | Spread incoming requests across servers |
| Rate Limiting           | Restrict excessive client requests      |
| Anycast Routing         | Distribute traffic geographically       |
| DDoS Mitigation Service | Filter and absorb attack traffic        |

---

# SOC Analyst Perspective

During a suspected DoS/DDoS attack, a SOC analyst should:

1. Detect unusual traffic patterns.
2. Identify the attack type (Network or Application Layer).
3. Monitor firewall, IDS/IPS, and SIEM alerts.
4. Review packet captures using Wireshark or tcpdump.
5. Correlate logs from multiple data sources.
6. Escalate the incident according to the Incident Response Plan.
7. Enable mitigation controls such as WAF, rate limiting, or DDoS protection.
8. Verify service restoration.
9. Document Indicators of Compromise (IoCs), timelines, and lessons learned.

---

# Skills Gained

After completing this module, you should be able to:

* Understand the MITRE ATT&CK Impact tactic.
* Map DoS and DDoS attacks to ATT&CK techniques.
* Differentiate Network DoS (T1498) from Endpoint DoS (T1499).
* Recognize common denial-of-service attack patterns.
* Identify relevant log sources for detection.
* Recommend enterprise-grade mitigation strategies.
* Apply MITRE ATT&CK terminology in VAPT reports and SOC investigations.

---

# Interview Questions

### Q1. Which MITRE ATT&CK tactic includes DoS attacks?

**Answer:** **Impact (TA0040)**

---

### Q2. Which ATT&CK technique covers SYN Flood attacks?

**Answer:** **T1498 – Network Denial of Service**

---

### Q3. Which ATT&CK technique covers Slowloris attacks?

**Answer:** **T1499 – Endpoint Denial of Service**

---

### Q4. Why should cybersecurity professionals use MITRE ATT&CK?

**Answer:**
MITRE ATT&CK provides a standardized framework for describing adversary behavior, improving threat detection, incident response, threat hunting, security assessments, and communication across security teams.

---

# Key Takeaways

* **TA0040 (Impact)** contains the primary DoS-related techniques.
* **T1498** focuses on disrupting **network services** through traffic-based attacks.
* **T1499** focuses on exhausting **endpoint or application resources**.
* Mapping CEH topics to MITRE ATT&CK strengthens practical understanding and aligns learning with industry-standard threat intelligence frameworks.
