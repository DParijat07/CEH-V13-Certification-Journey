# Module 12 – Evading IDS, Firewalls & Honeypots
## Interview Questions & Answers

---

# Firewall

### 1. What is a firewall?

A firewall is a network security device or software that monitors and filters incoming and outgoing traffic based on predefined security rules.

---

### 2. Why is a firewall used?

To prevent unauthorized access while allowing legitimate network communication.

---

### 3. What are the primary functions of a firewall?

- Traffic filtering
- Access control
- Logging
- Network segmentation
- Policy enforcement

---

### 4. What are the different types of firewalls?

- Packet Filtering Firewall
- Stateful Inspection Firewall
- Proxy Firewall
- Circuit-Level Gateway
- Next-Generation Firewall (NGFW)

---

### 5. What is Packet Filtering?

Packet filtering examines packets based on:

- Source IP
- Destination IP
- Source Port
- Destination Port
- Protocol

---

### 6. What is Stateful Inspection?

Stateful inspection tracks active network connections and makes filtering decisions based on the connection state.

---

### 7. What is a Next-Generation Firewall (NGFW)?

An advanced firewall that provides:

- Deep Packet Inspection
- Application Awareness
- Intrusion Prevention
- Malware Detection
- SSL Inspection

---

### 8. Give examples of enterprise firewalls.

- Palo Alto Networks
- Fortinet FortiGate
- Cisco Firepower
- Check Point
- Sophos XGS

---

### 9. What is the difference between a network firewall and a host firewall?

Network Firewall protects an entire network.

Host Firewall protects a single computer.

---

### 10. What is the Principle of Least Privilege?

Only the minimum required network access should be allowed.

---

# IDS

### 11. What is IDS?

An Intrusion Detection System monitors network or host activities and generates alerts when suspicious behavior is detected.

---

### 12. Does IDS block attacks?

No.

It only detects and alerts.

---

### 13. What are the types of IDS?

- Network IDS (NIDS)
- Host IDS (HIDS)

---

### 14. What is NIDS?

Network IDS monitors traffic flowing across the network.

---

### 15. What is HIDS?

Host IDS monitors activities occurring on an individual computer.

---

### 16. Name some IDS tools.

- Snort
- Suricata
- Zeek
- Wazuh
- OSSEC

---

### 17. What is Signature-Based Detection?

Detection using known attack signatures.

---

### 18. What is Anomaly-Based Detection?

Detection based on deviations from normal behavior.

---

### 19. What are False Positives?

Legitimate activity incorrectly classified as malicious.

---

### 20. What are False Negatives?

Malicious activity that is not detected.

---

# IPS

### 21. What is IPS?

An Intrusion Prevention System monitors and automatically blocks malicious traffic.

---

### 22. How is IPS different from IDS?

IDS detects attacks.

IPS detects and blocks attacks.

---

### 23. Why is IPS called an inline device?

Because all traffic passes through it before reaching the destination.

---

### 24. Can IPS generate alerts?

Yes.

It both blocks attacks and generates alerts.

---

### 25. Name common IPS actions.

- Drop packets
- Block IP
- Reset connection
- Generate alert
- Log events

---

# Comparison

### 26. Firewall vs IDS?

Firewall controls traffic.

IDS monitors traffic.

---

### 27. IDS vs IPS?

IDS detects.

IPS detects and prevents.

---

### 28. Firewall vs IPS?

Firewall filters based on rules.

IPS inspects traffic for malicious activity and blocks attacks.

---

### 29. Which technology works passively?

IDS.

---

### 30. Which technologies work inline?

Firewall and IPS.

---

# Honeypots

### 31. What is a Honeypot?

A decoy system designed to attract attackers.

---

### 32. Why are Honeypots deployed?

- Threat intelligence
- Malware analysis
- Detection
- Research

---

### 33. What is a Honeynet?

A network of multiple honeypots.

---

### 34. What is a Honeytoken?

A fake digital asset that generates alerts when accessed.

---

### 35. Types of Honeypots?

- Production
- Research

---

### 36. Interaction levels?

- Low
- Medium
- High

---

### 37. Advantages of Honeypots?

- Low false positives
- Intelligence gathering
- Incident response support

---

### 38. Limitations of Honeypots?

- Require monitoring
- May be identified by attackers
- Do not directly protect production systems

---

# Defense Evasion

### 39. What is Defense Evasion?

Techniques that reduce the visibility of malicious activity to security controls.

---

### 40. Why should defenders understand Defense Evasion?

To improve detection rules, monitoring, and incident response.

---

# SOC

### 41. Which logs are most useful for detecting suspicious activity?

- Firewall Logs
- IDS Alerts
- IPS Events
- Windows Event Logs
- DNS Logs
- VPN Logs
- Proxy Logs
- EDR Logs

---

### 42. What is SIEM?

A Security Information and Event Management platform used for centralized log collection, correlation, monitoring, and alerting.

---

### 43. Name popular SIEM solutions.

- Splunk
- Microsoft Sentinel
- IBM QRadar
- Elastic Security

---

### 44. What is Defense-in-Depth?

Using multiple layers of security controls instead of relying on a single defense.

---

### 45. Why is centralized logging important?

It enables correlation of events, faster detection, investigation, and incident response.

---

# MITRE ATT&CK

### 46. Which MITRE ATT&CK tactic is most closely related to this module?

Defense Evasion (TA0005).

---

### 47. What is an IOC?

Indicator of Compromise — evidence that suggests a system may have been compromised.

---

### 48. What is EDR?

Endpoint Detection and Response, a solution for monitoring, detecting, investigating, and responding to endpoint threats.

---

### 49. Why are behavioral analytics important?

They help identify suspicious activities that may not match known attack signatures.

---

### 50. What is the most important takeaway from Module 12?

No single security control is enough. Organizations should implement a layered defense using Firewalls, IDS, IPS, Honeypots, EDR, SIEM, and continuous monitoring to effectively detect and respond to cyber threats.
