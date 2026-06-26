# Attack-Techniques.md

# CEH v13 – Module 10

# Denial of Service (DoS) Attack Techniques

---

# Overview

A **Denial of Service (DoS)** attack aims to make a target system, service, application, or network unavailable to legitimate users by exhausting resources or exploiting weaknesses in communication protocols.

This document summarizes the most common DoS and DDoS attack techniques covered in CEH v13.

---

# 1. TCP SYN Flood

## Description

A TCP SYN Flood exploits the **TCP Three-Way Handshake** by sending a large number of SYN packets without completing the connection.

### Attack Flow

```text
Attacker
    │
    ├── SYN ─────────────► Server
    │
    │◄──── SYN/ACK ──────
    │
    └── No ACK Sent
```

The server keeps waiting for the final ACK.

Eventually:

* Half-open connections accumulate
* Connection queue becomes full
* Legitimate users cannot connect

### Target

* Web Servers
* Mail Servers
* SSH Servers

### Impact

* Memory exhaustion
* CPU utilization
* Connection exhaustion

---

# 2. UDP Flood

## Description

The attacker sends a massive number of UDP packets to random destination ports.

The victim attempts to process every packet and often generates ICMP Destination Unreachable responses.

### Impact

* High CPU usage
* Increased bandwidth consumption
* Network congestion

### Target Services

* DNS
* VoIP
* Streaming services

---

# 3. ICMP Flood (Ping Flood)

## Description

Large numbers of ICMP Echo Requests are sent to overwhelm the victim.

### Impact

* Consumes network bandwidth
* High CPU utilization
* Slower response time

---

# 4. Ping of Death

## Description

The attacker sends malformed or oversized ICMP packets exceeding the maximum IP packet size.

Older operating systems may crash or reboot.

### Modern Status

Most modern operating systems are patched.

---

# 5. Smurf Attack

## Description

The attacker sends spoofed ICMP Echo Requests to a network broadcast address.

Every host replies to the spoofed victim.

### Process

```text
Attacker
      │
      ▼
Broadcast Network
      │
 ┌────┴─────┐
Host Host Host Host
      │
      ▼
Victim
```

### Impact

Traffic amplification resulting in service disruption.

---

# 6. DNS Amplification Attack

## Description

An attacker sends small spoofed DNS queries to open DNS resolvers.

The resolver replies with much larger responses to the victim.

### Advantages

* High amplification factor
* IP spoofing hides attacker identity

---

# 7. NTP Amplification

## Description

Abuses publicly accessible Network Time Protocol (NTP) servers.

Small requests generate significantly larger responses.

### Impact

Very high bandwidth consumption.

---

# 8. SSDP Amplification

## Description

Uses Universal Plug and Play (UPnP) devices.

Responses are amplified toward the victim.

---

# 9. Memcached Amplification

## Description

Targets exposed Memcached servers.

One of the largest DDoS amplification attacks recorded.

### Characteristics

* Massive amplification
* Multi-Gbps attacks
* Difficult to mitigate

---

# 10. HTTP Flood

## Description

Targets web applications using seemingly legitimate HTTP GET or POST requests.

Unlike SYN floods, HTTP floods consume application resources.

### Impact

* High CPU utilization
* Database overload
* Web application slowdown

---

# 11. Slowloris Attack

## Description

Maintains hundreds or thousands of partially completed HTTP connections.

Each connection stays open for an extended period.

### Advantages

* Low attacker bandwidth
* Difficult detection
* Effective against Apache servers

---

# 12. Slow POST Attack

## Description

The attacker slowly uploads HTTP POST requests.

The web server waits for the complete request.

### Result

Connection pool exhaustion.

---

# 13. Fragmentation Attack

## Description

Malformed IP fragments consume system resources during packet reassembly.

Examples include:

* Teardrop Attack
* Overlapping Fragment Attack

---

# 14. Application Layer DoS

## Description

Targets specific application functionality instead of bandwidth.

Examples:

* Login page flooding
* Search function abuse
* Database-intensive requests
* API request flooding

---

# 15. Botnet-Based DDoS

## Description

Thousands of compromised devices simultaneously attack the victim.

### Common Botnets

* Mirai
* Mozi
* Mantis

### Advantages

* Massive traffic generation
* Distributed attack sources
* Difficult attribution

---

# Reflection Attack

## Description

Uses legitimate third-party servers to reflect attack traffic.

### Examples

* DNS Reflection
* NTP Reflection
* SSDP Reflection

---

# Amplification Attack

## Description

The attacker sends a small request that produces a significantly larger response.

### Common Protocols

* DNS
* NTP
* Memcached
* CLDAP

---

# Comparison Table

| Attack            | Layer       | Primary Target    |
| ----------------- | ----------- | ----------------- |
| SYN Flood         | Network     | TCP Connections   |
| UDP Flood         | Network     | Bandwidth         |
| ICMP Flood        | Network     | Bandwidth         |
| Ping of Death     | Network     | Operating System  |
| Smurf             | Network     | Broadcast Network |
| DNS Amplification | Network     | Bandwidth         |
| NTP Amplification | Network     | Bandwidth         |
| HTTP Flood        | Application | Web Server        |
| Slowloris         | Application | HTTP Connections  |
| Slow POST         | Application | Web Applications  |
| Fragmentation     | Network     | IP Stack          |
| Botnet DDoS       | Multiple    | Infrastructure    |

---

# Indicators of DoS Attack

* Sudden spike in traffic
* High CPU utilization
* High memory consumption
* Numerous half-open TCP sessions
* Slow application response
* Connection timeouts
* Network congestion
* Service unavailability

---

# Detection Tools

* Wireshark
* tcpdump
* Zeek
* Snort
* Suricata
* NetFlow Analyzer
* SIEM Platforms

---

# Key Takeaways

* DoS attacks primarily target **Availability**.
* SYN Flood exploits the TCP handshake.
* HTTP Flood targets application resources.
* Slowloris exhausts web server connections.
* Amplification attacks abuse legitimate services.
* Botnets enable large-scale Distributed Denial of Service (DDoS) attacks.
* Early detection and layered defenses are essential for mitigating DoS attacks.
