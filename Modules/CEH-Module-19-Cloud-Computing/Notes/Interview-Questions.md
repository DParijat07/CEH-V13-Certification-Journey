# Cloud Computing – Interview Questions

## Overview

This document contains common interview questions for **CEH v13**, **SOC Analyst (L1)**, **Cloud Security**, and **Blue Team** roles.

---

# Cloud Fundamentals

### 1. What is Cloud Computing?

Cloud computing is the on-demand delivery of computing resources such as servers, storage, networking, databases, and applications over the Internet.

---

### 2. What are the five essential characteristics of cloud computing?

- On-Demand Self-Service
- Broad Network Access
- Resource Pooling
- Rapid Elasticity
- Measured Service

---

### 3. What are the main benefits of cloud computing?

- Scalability
- Cost efficiency
- High availability
- Flexibility
- Disaster recovery
- Global accessibility

---

### 4. What is virtualization?

Virtualization allows multiple virtual machines to run on a single physical server through a hypervisor.

---

### 5. Difference between Virtual Machines and Containers?

| Virtual Machines | Containers |
|------------------|------------|
| Includes guest OS | Shares host OS kernel |
| More resource usage | Lightweight |
| Slower startup | Faster startup |
| Better isolation | Higher density |

---

# Cloud Service Models

### 6. What is IaaS?

Infrastructure as a Service provides virtual infrastructure such as virtual machines, storage, and networking.

---

### 7. What is PaaS?

Platform as a Service provides a managed platform for application development without managing the operating system.

---

### 8. What is SaaS?

Software as a Service delivers complete software applications over the Internet.

---

### 9. What is FaaS?

Function as a Service (Serverless Computing) executes application code without requiring server management.

---

### 10. Difference between IaaS, PaaS, and SaaS?

| Model | Customer Manages |
|---------|-----------------|
| IaaS | OS, Applications, Data |
| PaaS | Applications, Data |
| SaaS | Users and Data |

---

# Cloud Deployment Models

### 11. What is a Public Cloud?

Infrastructure shared among multiple customers and managed by a cloud provider.

---

### 12. What is a Private Cloud?

Cloud infrastructure dedicated to a single organization.

---

### 13. What is a Hybrid Cloud?

A combination of public and private cloud environments.

---

### 14. What is Multi-Cloud?

Using services from multiple cloud providers such as AWS, Azure, and GCP.

---

# Cloud Architecture

### 15. What is a VPC?

A Virtual Private Cloud is an isolated virtual network within a public cloud.

---

### 16. Difference between Public and Private Subnets?

- Public Subnet → Internet accessible
- Private Subnet → Internal resources only

---

### 17. What is a Load Balancer?

A service that distributes incoming traffic across multiple servers to improve availability and performance.

---

### 18. What is IAM?

Identity and Access Management controls who can access cloud resources and what actions they are allowed to perform.

---

### 19. What is RBAC?

Role-Based Access Control assigns permissions based on organizational roles.

---

### 20. What is the Principle of Least Privilege?

Users receive only the minimum permissions required to perform their job.

---

# Shared Responsibility

### 21. What is the Shared Responsibility Model?

Security responsibilities are divided between the cloud provider and the customer.

---

### 22. What does the cloud provider secure?

Typically:

- Physical infrastructure
- Networking hardware
- Hypervisors
- Data centers

---

### 23. What does the customer secure?

Typically:

- Applications
- Data
- IAM
- Configurations
- Operating systems (IaaS)

---

# Cloud Security

### 24. What is Defense-in-Depth?

Using multiple independent security controls to protect cloud environments.

---

### 25. What is Zero Trust?

A security model based on the principle:

**Never Trust, Always Verify.**

---

### 26. Why is MFA important?

It reduces the risk of account compromise by requiring multiple authentication factors.

---

### 27. What is encryption?

The process of converting readable data into ciphertext to protect confidentiality.

---

### 28. Difference between Data at Rest and Data in Transit?

- Data at Rest → Stored data
- Data in Transit → Data moving across networks

---

### 29. What is KMS?

Key Management Service securely stores and manages encryption keys.

---

### 30. What is Secrets Management?

Secure storage of passwords, API keys, certificates, and tokens.

---

# Cloud Threats

### 31. What is cloud misconfiguration?

Incorrect or insecure cloud settings that expose resources.

---

### 32. Why are misconfigurations dangerous?

They may expose storage, identities, APIs, or services to attackers.

---

### 33. What is Shadow IT?

Unauthorized cloud services used without organizational approval.

---

### 34. What is cryptojacking?

Unauthorized cryptocurrency mining using cloud resources.

---

### 35. What is account hijacking?

Unauthorized takeover of a legitimate cloud account.

---

### 36. What are insecure APIs?

APIs lacking proper authentication, authorization, or input validation.

---

### 37. What are insider threats?

Security risks caused by authorized users, intentionally or accidentally.

---

### 38. What is ransomware?

Malware that encrypts data and demands payment for recovery.

---

### 39. What is CSPM?

Cloud Security Posture Management continuously identifies cloud misconfigurations.

---

### 40. What is CWPP?

Cloud Workload Protection Platform protects cloud workloads such as VMs and containers.

---

# Blue Team

### 41. What logs should be monitored?

- Authentication logs
- API logs
- Firewall logs
- Storage logs
- Database logs
- Activity logs

---

### 42. What indicators suggest account compromise?

- Impossible travel
- Multiple failed logins
- New administrator accounts
- Unusual API activity

---

### 43. What indicators suggest cryptojacking?

- High CPU utilization
- Increased cloud costs
- Unexpected workloads

---

### 44. Why are SIEM platforms important?

They centralize logs, correlate events, and generate security alerts.

---

### 45. What is threat hunting?

Proactively searching for attacker activity not detected by automated tools.

---

# CEH Quick Revision

### 46. Which service model provides the most customer control?

IaaS

---

### 47. Which service model provides the least customer management?

SaaS

---

### 48. Which deployment model combines public and private cloud?

Hybrid Cloud

---

### 49. Which cloud service executes code without managing servers?

FaaS (Serverless Computing)

---

### 50. Which security principle gives users minimum permissions?

Principle of Least Privilege

---

### 51. Which framework documents attacker tactics and techniques?

MITRE ATT&CK

---

### 52. Which security solution discovers Shadow IT?

CASB

---

### 53. Which solution detects cloud misconfigurations?

CSPM

---

### 54. Which solution protects cloud workloads?

CWPP

---

### 55. Which authentication method greatly reduces credential theft?

Multi-Factor Authentication (MFA)

---

# Scenario-Based Questions

### 56. A storage bucket is publicly accessible. What is the primary risk?

Unauthorized access and data exposure.

---

### 57. An employee receives administrator permissions accidentally. Which security principle was violated?

Principle of Least Privilege.

---

### 58. Multiple failed login attempts followed by a successful login from another country are detected. What could this indicate?

Possible credential compromise or account takeover.

---

### 59. Cloud billing suddenly increases without business justification. What could be a likely cause?

Cryptojacking or unauthorized resource creation.

---

### 60. Why should cloud logs be retained?

To support investigations, compliance, threat hunting, and incident response.

---

# Key Takeaways

- Understand cloud service models (IaaS, PaaS, SaaS, FaaS).
- Know cloud deployment models (Public, Private, Hybrid, Multi-Cloud).
- Learn IAM, MFA, Least Privilege, and the Shared Responsibility Model.
- Recognize common cloud threats such as misconfiguration, credential theft, insecure APIs, and ransomware.
- Be familiar with cloud security technologies including CASB, CSPM, CWPP, SIEM, and Zero Trust.
- Practice explaining cloud concepts using simple, real-world examples during interviews.
