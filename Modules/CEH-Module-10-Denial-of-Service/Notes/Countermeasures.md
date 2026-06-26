# Countermeasures.md

# CEH v13 – Module 10

# Denial of Service (DoS) & Distributed Denial of Service (DDoS) Countermeasures

---

# Overview

Denial of Service (DoS) and Distributed Denial of Service (DDoS) attacks primarily target the **Availability** component of the CIA Triad. The objective of defense is to ensure services remain accessible to legitimate users while minimizing the impact of malicious traffic.

---

# Defense-in-Depth Strategy

Effective DoS protection relies on **multiple layers of security controls** rather than a single solution.

```text
Internet
     │
Firewall
     │
IDS / IPS
     │
Load Balancer
     │
Web Application Firewall (WAF)
     │
Application Server
```

---

# 1. Firewalls

## Purpose

Firewalls filter incoming and outgoing traffic based on predefined security rules.

### Benefits

* Block unwanted ports
* Restrict suspicious IP addresses
* Drop malformed packets
* Prevent unauthorized access

### Best Practices

* Enable stateful inspection
* Deny unnecessary ports
* Use ACLs
* Regularly review firewall rules

---

# 2. Intrusion Detection & Prevention Systems (IDS/IPS)

## IDS

Monitors network traffic and generates alerts.

Examples:

* Snort
* Suricata
* Zeek

---

## IPS

Detects and actively blocks malicious traffic before it reaches the target.

---

# 3. Rate Limiting

## Purpose

Restrict the number of requests a client can make within a specific period.

### Advantages

* Reduces brute-force attacks
* Prevents request flooding
* Protects APIs
* Limits automated abuse

Example:

```text
100 Requests / Minute / User
```

---

# 4. Access Control Lists (ACLs)

ACLs allow administrators to permit or deny network traffic based on:

* IP Address
* Protocol
* Port Number
* Direction

---

# 5. Load Balancing

## Purpose

Distribute incoming traffic across multiple servers.

### Benefits

* Prevents server overload
* Improves availability
* Provides fault tolerance
* Supports scalability

Popular Load Balancers:

* HAProxy
* Nginx
* AWS Elastic Load Balancer
* F5 BIG-IP

---

# 6. Web Application Firewall (WAF)

## Purpose

Protects web applications against application-layer attacks.

Can detect:

* HTTP Floods
* SQL Injection
* Cross-Site Scripting (XSS)
* Malicious Bots
* Slow HTTP attacks

Popular WAF Solutions

* Cloudflare WAF
* AWS WAF
* ModSecurity
* Azure WAF

---

# 7. Content Delivery Network (CDN)

## Purpose

Distributes website content across multiple geographically distributed servers.

### Benefits

* Reduces server load
* Absorbs attack traffic
* Improves response time
* Provides redundancy

Popular CDN Providers

* Cloudflare
* Akamai
* Fastly
* Amazon CloudFront

---

# 8. DDoS Protection Services

Cloud-based DDoS mitigation services filter malicious traffic before it reaches the organization's infrastructure.

Common Features

* Traffic Scrubbing
* Behavioral Analysis
* Anycast Routing
* Automatic Mitigation
* Global Filtering

Examples

* Cloudflare DDoS Protection
* AWS Shield
* Google Cloud Armor
* Azure DDoS Protection

---

# 9. Network Monitoring

Continuous monitoring helps detect attacks early.

Monitor:

* Bandwidth usage
* Packet rate
* Connection count
* CPU utilization
* Memory utilization
* Network latency

Useful Tools

* Wireshark
* Zeek
* NetFlow
* Grafana
* Prometheus

---

# 10. Traffic Filtering

Block:

* Spoofed IP Addresses
* Malformed Packets
* Suspicious Protocols
* Known Malicious Networks

Filtering Techniques

* Ingress Filtering
* Egress Filtering
* Geo-IP Blocking
* IP Reputation Filtering

---

# 11. SYN Cookies

## Purpose

Protect against TCP SYN Flood attacks.

Instead of allocating resources immediately, the server delays connection allocation until the TCP handshake is completed.

### Benefits

* Prevents Half-Open Connection Exhaustion
* Reduces Memory Consumption

---

# 12. Anycast Routing

Anycast distributes traffic to the nearest available data center.

Advantages

* Reduces latency
* Distributes attack traffic
* Improves resilience
* Supports global availability

---

# 13. Redundant Infrastructure

High availability architecture minimizes downtime.

Examples

* Multiple Servers
* Multiple Data Centers
* Backup Internet Links
* Failover Systems

---

# 14. System Hardening

Reduce the attack surface by:

* Disabling unused services
* Closing unnecessary ports
* Applying security patches
* Updating operating systems
* Removing default accounts

---

# 15. Patch Management

Keep systems updated.

Benefits

* Fix known vulnerabilities
* Improve stability
* Prevent exploitation

---

# 16. Capacity Planning

Organizations should estimate expected traffic and ensure sufficient:

* CPU
* Memory
* Storage
* Internet Bandwidth

---

# Incident Response During a DoS Attack

## Step 1

Identify abnormal traffic.

---

## Step 2

Determine attack type.

Examples

* SYN Flood
* UDP Flood
* HTTP Flood

---

## Step 3

Activate mitigation controls.

Examples

* Enable Rate Limiting
* Apply Firewall Rules
* Enable WAF
* Redirect Traffic

---

## Step 4

Monitor service availability.

---

## Step 5

Collect logs and evidence.

---

## Step 6

Perform post-incident analysis.

---

# Best Practices

✅ Enable Firewalls

✅ Deploy IDS/IPS

✅ Use Rate Limiting

✅ Configure WAF

✅ Implement CDN

✅ Apply Security Patches

✅ Monitor Network Traffic

✅ Maintain Regular Backups

✅ Prepare Incident Response Plans

✅ Perform Security Assessments

---

# Enterprise Security Architecture

```text
                Internet
                    │
          DDoS Protection Service
                    │
               CDN / Anycast
                    │
                Firewall
                    │
              IDS / IPS
                    │
          Load Balancer
                    │
         Web Application Firewall
                    │
            Web/Application Server
                    │
                Database
```

---

# CEH Exam Tips

* Firewalls filter malicious traffic.
* WAF protects web applications.
* IDS detects attacks.
* IPS detects **and blocks** attacks.
* Rate limiting reduces request flooding.
* SYN Cookies mitigate SYN Flood attacks.
* CDNs distribute traffic and improve availability.
* DDoS protection services absorb and filter attack traffic.
* Defense-in-depth provides stronger protection than relying on a single security control.

---

# Key Takeaways

* No single solution can completely prevent DoS or DDoS attacks.
* A layered security architecture combining firewalls, IDS/IPS, WAFs, CDNs, and DDoS mitigation services provides the most effective defense.
* Continuous monitoring, timely patching, and a well-practiced incident response plan are essential for maintaining service availability during attack scenarios.
