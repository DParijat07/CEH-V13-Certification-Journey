# Module 10 — Denial-of-Service

This directory contains practical exercises related to **Denial-of-Service (DoS) attacks** from CEH v13.

The focus is on understanding service availability, resource exhaustion, traffic analysis, DoS indicators, and defensive measures through controlled lab simulations and safe traffic-analysis exercises.

## Practical Areas

- DoS and DDoS fundamentals
- Availability and resource exhaustion concepts
- TCP connection behavior analysis
- Network traffic pattern analysis
- SYN flood concepts and detection
- ICMP traffic analysis
- Application-layer DoS concepts
- Rate limiting and traffic filtering
- Service availability monitoring
- DoS mitigation and incident response

## Directory Structure

```text
Module-10/
│
├── 01-DoS-and-DDoS-Fundamentals/
├── 02-TCP-Connection-Behavior-Analysis/
├── 03-SYN-Flood-Detection/
├── 04-ICMP-Traffic-Analysis/
├── 05-Application-Layer-DoS-Analysis/
├── 06-Service-Availability-Monitoring/
└── 07-DoS-Mitigation-and-Defense/
```

## Tools and Resources

Tools and resources may include:

- Wireshark
- tcpdump
- TShark
- Nmap for authorized service discovery
- Linux system monitoring utilities
- Web server access logs
- Firewall and rate-limiting configurations
- Pre-recorded network traffic captures

## Practical Workflow

**Prepare Lab → Establish Baseline → Observe Traffic → Identify Anomalies → Analyze Service Impact → Apply Defensive Controls → Verify → Document**

## Evidence and Documentation

Each exercise should document, where applicable:

- Objective and authorized scope
- Lab topology and target configuration
- Tools and monitoring methods
- Baseline and observed traffic patterns
- Relevant screenshots, logs, or packet captures
- Indicators of resource exhaustion
- Potential service impact
- Mitigation and prevention recommendations
- Lessons learned

## Authorization and Safety

Do not perform DoS or DDoS attacks against public websites, production services, or third-party infrastructure without explicit authorization and an approved testing plan. Prefer offline packet analysis, defensive configuration exercises, and isolated simulations that cannot affect external systems.

## Learning Outcome

The objective is to understand availability-related threats, recognize suspicious traffic patterns, evaluate service resilience, and identify defensive measures that help maintain service availability.

**CEH v13 Certification Journey — Practical Learning and Proof of Work**
