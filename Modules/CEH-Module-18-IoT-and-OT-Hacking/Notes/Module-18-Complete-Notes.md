---

# Module 18 – IoT and OT Hacking

# Part 1 – Internet of Things (IoT) Fundamentals

## Overview

The **Internet of Things (IoT)** refers to a network of physical devices embedded with sensors, software, processors, and communication capabilities that enable them to collect, exchange, and process data over networks.

IoT has transformed industries by enabling automation, real-time monitoring, predictive maintenance, and smart decision-making. However, the rapid growth of connected devices has also expanded the attack surface, making IoT security a major concern for organizations.

---

# What is IoT?

The Internet of Things (IoT) is an ecosystem of interconnected physical devices that communicate with each other and with cloud or edge services.

Examples include:

- Smart home devices
- Smart watches
- Fitness trackers
- Smart TVs
- Smart lighting
- Connected vehicles
- Medical devices
- Industrial sensors
- Smart agriculture systems

---

# Characteristics of IoT

Common characteristics include:

- Connectivity
- Automation
- Remote management
- Real-time data collection
- Machine-to-machine (M2M) communication
- Scalability
- Low-power operation
- Intelligence through analytics

---

# Core Components of IoT

A typical IoT ecosystem consists of:

- Sensors
- Actuators
- Embedded processors
- Communication modules
- IoT gateway
- Edge devices
- Cloud platform
- Applications
- Users

Each component contributes to collecting, transmitting, processing, and acting on data.

---

# Sensors

## Overview

Sensors detect physical or environmental conditions and convert them into digital information.

Common examples include:

- Temperature sensors
- Humidity sensors
- Pressure sensors
- Motion sensors
- Light sensors
- Smoke detectors
- GPS sensors
- Accelerometers

### Examples of Use

- Smart thermostats
- Wearable fitness devices
- Industrial monitoring
- Environmental monitoring
- Smart agriculture

---

# Actuators

## Overview

Actuators receive commands from a controller and perform physical actions.

Examples include:

- Electric motors
- Valves
- Relays
- Robotic arms
- Smart locks
- Pumps

### Purpose

Actuators allow IoT systems to interact with the physical environment by performing automated actions.

---

# Embedded Systems

IoT devices typically contain embedded systems designed for dedicated tasks.

Components include:

- Microcontroller (MCU)
- Memory
- Firmware
- Communication interface
- Power management

Embedded systems are optimized for low power consumption and reliability.

---

# IoT Gateway

An IoT gateway acts as an intermediary between IoT devices and cloud or enterprise systems.

Responsibilities include:

- Data aggregation
- Protocol translation
- Device management
- Security enforcement
- Network connectivity

Gateways reduce direct exposure of edge devices to external networks.

---

# Edge Computing

## Overview

Edge computing processes data close to where it is generated rather than sending all data to the cloud.

### Benefits

- Reduced latency
- Faster decision-making
- Lower bandwidth usage
- Improved reliability
- Better privacy

Examples include industrial controllers, smart cameras, and edge AI devices.

---

# Cloud Computing in IoT

Cloud platforms provide centralized services for IoT environments.

Common functions include:

- Device management
- Data storage
- Analytics
- Machine learning
- Dashboards
- Remote monitoring
- Alerting

Cloud computing enables organizations to manage thousands or millions of connected devices efficiently.

---

# IoT Communication Protocols

IoT devices communicate using specialized protocols depending on bandwidth, power consumption, and application requirements.

Common protocols include:

- MQTT
- CoAP
- HTTP/HTTPS
- Bluetooth Low Energy (BLE)
- Zigbee
- Z-Wave
- Wi-Fi
- LoRaWAN
- NB-IoT
- Cellular (4G/5G)

The choice of protocol depends on the specific IoT deployment and operational requirements.

---

# IoT Architecture

A simplified IoT architecture consists of four layers:

1. Device Layer
2. Network Layer
3. Processing Layer
4. Application Layer

### Device Layer

Includes:

- Sensors
- Actuators
- Embedded devices

### Network Layer

Responsible for communication between devices, gateways, and cloud services.

### Processing Layer

Handles:

- Data processing
- Analytics
- Storage
- Device management

### Application Layer

Provides services to end users, such as:

- Mobile applications
- Web dashboards
- Industrial control interfaces
- Business analytics

---

# Common IoT Applications

IoT is widely used across multiple sectors.

Examples include:

- Smart homes
- Smart cities
- Healthcare
- Industrial automation (IIoT)
- Agriculture
- Transportation
- Energy management
- Logistics
- Environmental monitoring

---

# Benefits of IoT

Organizations adopt IoT to achieve:

- Automation
- Improved efficiency
- Real-time visibility
- Predictive maintenance
- Reduced operational costs
- Better customer experiences
- Data-driven decision-making

---

# Challenges of IoT

Common challenges include:

- Large attack surface
- Weak authentication
- Default credentials
- Limited device resources
- Firmware vulnerabilities
- Privacy concerns
- Device lifecycle management
- Lack of standardization
- Physical security risks

---

# CEH Exam Tips

Remember:

- IoT connects physical devices to networks.
- Sensors collect information from the environment.
- Actuators perform physical actions.
- Gateways connect IoT devices to enterprise or cloud environments.
- Edge computing processes data close to the source.
- Cloud platforms provide centralized IoT management.
- MQTT and CoAP are common IoT communication protocols.
- IoT devices often have limited computing resources, making security challenging.

---

# Key Takeaways

- IoT enables connected devices to collect, exchange, and process information automatically.
- Sensors, actuators, embedded systems, gateways, edge computing, and cloud platforms form the foundation of modern IoT ecosystems.
- While IoT provides significant operational benefits, it also introduces unique security challenges that require strong device management, secure communication, and continuous monitoring.

---

# Part 2 – Operational Technology (OT) and Industrial Control Systems (ICS)

## Overview

Operational Technology (OT) refers to hardware and software used to monitor, control, and automate physical processes. OT systems are commonly found in manufacturing plants, power grids, transportation systems, water treatment facilities, oil and gas operations, and other critical infrastructure.

Industrial Control Systems (ICS) are specialized OT systems designed to control industrial operations safely and efficiently.

Unlike traditional IT systems that focus on data processing, OT systems primarily focus on controlling physical processes where reliability and safety are critical.

---

# Operational Technology (OT)

## Definition

Operational Technology (OT) consists of programmable systems that interact with physical equipment and industrial processes.

Common industries using OT include:

- Manufacturing
- Power generation
- Oil and gas
- Water treatment
- Transportation
- Healthcare
- Smart buildings
- Mining

---

# Characteristics of OT

Typical characteristics include:

- Real-time operation
- High availability
- Long equipment life cycles
- Safety-critical processes
- Specialized industrial protocols
- Physical process control
- Continuous operation

---

# Industrial Control Systems (ICS)

## Overview

Industrial Control Systems (ICS) are integrated systems used to monitor and control industrial operations.

ICS environments typically include:

- SCADA
- PLCs
- RTUs
- DCS
- HMIs
- Engineering Workstations
- Historians
- Industrial Networks

---

# Supervisory Control and Data Acquisition (SCADA)

## Overview

SCADA systems provide centralized monitoring and supervisory control of geographically distributed industrial assets.

Common functions include:

- Monitoring field devices
- Collecting operational data
- Generating alarms
- Displaying system status
- Supervisory control

### Typical Use Cases

- Power distribution
- Water treatment
- Pipelines
- Railway systems
- Oil and gas

---

# Programmable Logic Controller (PLC)

## Overview

A PLC is an industrial computer designed to automate machinery and manufacturing processes.

Responsibilities include:

- Reading sensor inputs
- Executing programmed logic
- Controlling actuators
- Monitoring industrial equipment

PLCs are known for their reliability and ability to operate in harsh industrial environments.

---

# Remote Terminal Unit (RTU)

## Overview

RTUs collect information from remote industrial sites and communicate with SCADA systems.

Functions include:

- Sensor data collection
- Remote monitoring
- Device control
- Alarm reporting

RTUs are commonly deployed where industrial equipment is geographically dispersed.

---

# Distributed Control System (DCS)

## Overview

A Distributed Control System (DCS) controls industrial processes through multiple distributed controllers rather than a single centralized controller.

Advantages include:

- High reliability
- Scalability
- Fault tolerance
- Continuous process control

DCS is commonly used in:

- Chemical plants
- Oil refineries
- Pharmaceutical manufacturing
- Power plants

---

# Human Machine Interface (HMI)

## Overview

An HMI provides operators with a graphical interface to monitor and control industrial processes.

Typical functions include:

- Equipment monitoring
- Alarm visualization
- Trend analysis
- Process control
- Status dashboards

HMIs improve operational awareness and decision-making.

---

# Engineering Workstation

Engineering workstations are specialized computers used to:

- Configure PLCs
- Develop control logic
- Deploy firmware
- Manage industrial controllers
- Troubleshoot industrial systems

Because they have administrative access, engineering workstations are considered high-value assets.

---

# Historian

A Historian is a database optimized for storing time-series industrial data.

Typical information stored includes:

- Sensor readings
- Process measurements
- Alarm history
- Equipment status
- Operational trends

Historians support reporting, compliance, and predictive maintenance.

---

# Industrial Networks

Industrial devices communicate through dedicated industrial networks.

Common components include:

- PLCs
- RTUs
- HMIs
- Sensors
- Actuators
- Switches
- Industrial gateways

Industrial networks prioritize reliability, determinism, and availability.

---

# Purdue Enterprise Reference Architecture (PERA)

The Purdue Model divides industrial environments into logical levels.

### Level 0

Physical process

Examples:

- Sensors
- Actuators
- Motors
- Valves

---

### Level 1

Basic control

Examples:

- PLCs
- RTUs
- Intelligent controllers

---

### Level 2

Supervisory control

Examples:

- HMIs
- SCADA servers
- Historians

---

### Level 3

Operations management

Examples:

- Manufacturing Execution Systems (MES)
- Plant management systems

---

### Level 4

Enterprise IT

Examples:

- Business applications
- ERP systems
- Corporate networks
- Email servers

The Purdue Model promotes network segmentation between OT and IT environments.

---

# IT vs OT

| Information Technology (IT) | Operational Technology (OT) |
|-----------------------------|-----------------------------|
| Protects information | Controls physical processes |
| Focus on Confidentiality | Focus on Availability and Safety |
| Frequent updates | Controlled maintenance windows |
| Standard protocols | Industrial protocols |
| Short device lifecycle | Long device lifecycle |
| Business applications | Industrial equipment |

---

# Industrial Communication Protocols

Common OT protocols include:

- Modbus
- DNP3
- OPC UA
- PROFINET
- EtherNet/IP
- BACnet
- IEC 61850

These protocols enable communication between industrial devices and control systems.

---

# Critical Infrastructure

Critical infrastructure includes systems essential to society and the economy.

Examples:

- Electrical grids
- Water treatment plants
- Transportation
- Healthcare
- Telecommunications
- Manufacturing
- Oil and gas
- Chemical facilities

Disruptions to these environments can have significant safety and economic impacts.

---

# CEH Exam Tips

Remember:

- OT controls physical processes.
- ICS is the overall industrial control environment.
- SCADA supervises and monitors industrial systems.
- PLCs automate industrial machinery.
- RTUs collect data from remote locations.
- DCS controls continuous industrial processes.
- HMIs provide operator interfaces.
- Historians store industrial time-series data.
- The Purdue Model separates OT and IT into logical levels.
- OT prioritizes availability and safety over confidentiality.

---

# Key Takeaways

- Operational Technology (OT) focuses on controlling physical systems, while Industrial Control Systems (ICS) provide the technologies used to automate and monitor industrial operations.
- SCADA, PLCs, RTUs, DCS, HMIs, engineering workstations, and historians are core components of industrial environments.
- Network segmentation, standardized architectures such as the Purdue Model, and secure industrial communication are essential for protecting critical infrastructure.

---

# Part 3 – IoT and OT Threats

## Overview

The rapid adoption of Internet of Things (IoT) devices and Operational Technology (OT) systems has significantly increased the cyber attack surface. Many IoT devices have limited computing resources, long operational lifecycles, and inconsistent security controls. Likewise, OT environments prioritize availability and safety, making traditional IT security approaches difficult to implement.

Understanding common threats helps organizations implement effective defensive strategies and reduce operational risk.

---

# IoT Malware

## Overview

IoT malware is malicious software designed to compromise connected devices such as smart cameras, routers, sensors, and industrial controllers.

Potential impacts include:

- Device compromise
- Data theft
- Service disruption
- Unauthorized remote control
- Botnet participation

### Defensive Controls

- Keep firmware updated
- Disable unnecessary services
- Use strong authentication
- Monitor device behavior
- Segment IoT networks

---

# Botnets

## Overview

A botnet is a collection of compromised devices remotely controlled by an attacker.

IoT devices are often targeted because of:

- Weak passwords
- Default credentials
- Limited security controls
- Internet exposure

### Historical Example

**Mirai** (2016) was a well-known IoT botnet that infected internet-connected devices using default credentials and was responsible for several large distributed denial-of-service (DDoS) attacks.

### Defensive Controls

- Change default passwords
- Disable unused remote access
- Apply firmware updates
- Monitor unusual outbound traffic

---

# Weak Authentication

Many IoT devices are deployed with weak authentication mechanisms.

Examples include:

- Default usernames
- Default passwords
- Weak password policies
- Shared administrative accounts

### Defensive Controls

- Enforce strong passwords
- Enable Multi-Factor Authentication (MFA) where supported
- Remove default credentials
- Apply least privilege

---

# Firmware Vulnerabilities

Firmware controls low-level device functionality.

Security risks include:

- Outdated firmware
- Unpatched vulnerabilities
- Insecure update mechanisms
- Unsigned firmware

### Defensive Controls

- Apply vendor firmware updates
- Verify firmware integrity
- Use secure update mechanisms
- Enable Secure Boot where available

---

# Insecure APIs

Many IoT devices expose APIs for remote management.

Potential risks include:

- Weak authentication
- Excessive permissions
- Poor input validation
- Information disclosure

### Defensive Controls

- Strong authentication
- Encryption (HTTPS/TLS)
- Access control
- API monitoring
- Rate limiting

---

# Wireless Threats

IoT devices commonly use wireless technologies such as:

- Wi-Fi
- Bluetooth Low Energy (BLE)
- Zigbee
- Z-Wave
- LoRaWAN

Potential risks include:

- Unauthorized access
- Signal interception
- Device spoofing
- Denial-of-service attacks

### Defensive Controls

- Strong encryption
- Secure pairing
- Disable unused wireless interfaces
- Monitor wireless networks

---

# Supply Chain Risks

IoT devices often rely on third-party hardware, firmware, and software components.

Potential risks include:

- Compromised hardware
- Malicious firmware
- Vulnerable software libraries
- Counterfeit devices

### Defensive Controls

- Purchase from trusted vendors
- Validate firmware authenticity
- Maintain software inventories
- Perform supply chain risk assessments

---

# Cloud Security Risks

Many IoT deployments rely on cloud platforms.

Potential risks include:

- Misconfigured cloud services
- Weak identity management
- Exposed storage
- Insecure APIs
- Data leakage

### Defensive Controls

- Implement least privilege
- Enable MFA
- Encrypt sensitive data
- Monitor cloud activity
- Conduct regular security reviews

---

# Physical Security Risks

Unlike traditional servers, many IoT devices are deployed in physically accessible locations.

Potential risks include:

- Device theft
- Hardware tampering
- Unauthorized maintenance
- Component replacement

### Defensive Controls

- Secure installation locations
- Tamper-resistant hardware
- Physical access controls
- Asset inventory management

---

# Insider Threats

Employees, contractors, or trusted individuals may intentionally or unintentionally introduce security risks.

Examples include:

- Misconfiguration
- Unauthorized device installation
- Credential misuse
- Policy violations

### Defensive Controls

- Role-based access control (RBAC)
- Logging and monitoring
- User awareness training
- Separation of duties

---

# Industrial OT Threats

Industrial environments face threats that may affect both cybersecurity and physical operations.

Examples include:

- Unauthorized controller access
- Network disruption
- Industrial malware
- Device misconfiguration
- Unsafe process manipulation

Potential impacts include:

- Production downtime
- Equipment damage
- Financial loss
- Safety incidents

---

# Industrial Ransomware

Ransomware targeting industrial environments can disrupt manufacturing and critical infrastructure.

Potential impacts include:

- Production interruption
- Operational downtime
- Data unavailability
- Financial loss

### Defensive Controls

- Offline backups
- Network segmentation
- Patch management
- Incident response planning
- Continuous monitoring

---

# Safety Impacts

In OT environments, cybersecurity incidents may directly affect human safety.

Possible consequences include:

- Equipment malfunction
- Environmental damage
- Production failures
- Worker injuries
- Service disruption

Because of these risks, OT security places a strong emphasis on availability, integrity, and safety.

---

# Blue Team Detection Opportunities

Security teams should monitor for:

- Unknown IoT devices joining the network
- Default credentials still in use
- Firmware update failures
- Unexpected outbound traffic
- Unauthorized configuration changes
- Abnormal controller communications
- Repeated authentication failures
- Device compliance violations
- Unexpected cloud connections
- Industrial network anomalies

---

# Security Monitoring Checklist

Organizations should regularly review:

- Asset inventories
- Firmware versions
- Device authentication logs
- Network traffic
- Wireless activity
- Cloud access logs
- Configuration changes
- Security alerts
- SIEM dashboards

---

# CEH Exam Tips

Remember:

- IoT devices commonly have limited resources and long lifecycles.
- Weak authentication and default credentials remain major risks.
- Firmware security is critical.
- Mirai is a historical example of an IoT botnet.
- Industrial ransomware can affect both business operations and safety.
- OT security prioritizes availability and safe operation.
- Continuous monitoring helps detect abnormal behavior before major incidents occur.

---

# Key Takeaways

- IoT and OT environments face unique security challenges including weak authentication, firmware vulnerabilities, insecure APIs, wireless threats, supply chain risks, and industrial malware.
- Security controls such as strong authentication, secure firmware updates, network segmentation, monitoring, and user awareness significantly reduce organizational risk.
- Protecting industrial environments requires balancing cybersecurity with operational continuity and physical safety.

---

# Part 4 – IoT and OT Security Defense

## Overview

Securing Internet of Things (IoT) and Operational Technology (OT) environments requires a layered security strategy. Unlike traditional IT systems, industrial environments must balance cybersecurity with operational continuity and physical safety.

Organizations should implement preventive, detective, and corrective security controls to reduce cyber risks while ensuring reliable operation of connected devices and industrial systems.

---

# Defense-in-Depth

## Overview

Defense-in-depth is a layered security strategy that applies multiple independent security controls throughout an environment.

Security layers include:

- Physical security
- Device security
- Network security
- Identity and access management
- Application security
- Monitoring and logging
- Incident response
- User awareness

If one security control fails, additional layers continue protecting the environment.

---

# Zero Trust

## Overview

Zero Trust is a security model based on the principle:

> **"Never Trust, Always Verify."**

Every user, device, and application must be authenticated and authorized before accessing resources.

### Core Principles

- Verify identity continuously
- Validate device compliance
- Apply least privilege
- Assume breach
- Monitor continuously

Zero Trust is increasingly adopted in enterprise IoT and industrial environments.

---

# Network Segmentation

Network segmentation separates networks into smaller security zones.

Examples include:

- Corporate IT Network
- Industrial OT Network
- IoT Device Network
- Guest Network
- Management Network

### Benefits

- Limits lateral movement
- Reduces attack surface
- Improves monitoring
- Simplifies incident containment

Industrial environments often follow the Purdue Model for segmentation.

---

# Secure Boot

Secure Boot verifies the integrity of firmware and software during device startup.

Benefits include:

- Prevents unauthorized firmware
- Protects boot process
- Improves device integrity
- Reduces persistent malware risk

---

# Secure Firmware

Firmware security is critical because firmware controls device functionality.

Best practices include:

- Signed firmware
- Verified updates
- Secure update mechanisms
- Vendor-supported firmware
- Regular update schedules

---

# Device Identity

Every connected device should have a unique identity.

Common approaches include:

- Digital certificates
- Device identifiers
- Hardware security modules
- TPM (Trusted Platform Module)
- Secure elements

Unique identities improve authentication and asset management.

---

# Public Key Infrastructure (PKI)

PKI manages digital certificates and cryptographic keys.

Functions include:

- Device authentication
- Certificate management
- Secure communication
- Digital signatures
- Identity verification

PKI is widely used in enterprise IoT deployments.

---

# Encryption

Encryption protects information during storage and transmission.

### Data at Rest

Protects stored information using device or storage encryption.

### Data in Transit

Protects communication using protocols such as:

- TLS
- HTTPS
- IPsec
- VPN

Encryption reduces the risk of unauthorized data disclosure.

---

# Asset Management

Organizations should maintain a complete inventory of:

- IoT devices
- PLCs
- RTUs
- HMIs
- SCADA servers
- Network equipment
- Firmware versions
- Software versions

Benefits include:

- Improved visibility
- Better patch management
- Faster incident response
- Compliance support

---

# Vulnerability Management

Vulnerability management is a continuous process that includes:

- Asset identification
- Vulnerability assessment
- Risk prioritization
- Remediation
- Verification

Industrial environments should carefully evaluate updates before deployment to avoid operational disruption.

---

# Patch Management

Patch management reduces exposure to known vulnerabilities.

Best practices include:

- Vendor-approved updates
- Testing before deployment
- Maintenance windows
- Documentation
- Rollback procedures

Because many OT systems operate continuously, updates are typically scheduled during planned maintenance periods.

---

# Industrial Firewalls

Industrial firewalls protect communication between industrial networks.

Benefits include:

- Traffic filtering
- Protocol inspection
- Network segmentation
- Threat prevention

Industrial firewalls are commonly placed between IT and OT environments.

---

# Intrusion Detection and Prevention Systems (IDS/IPS)

IDS monitors network traffic for suspicious activity.

IPS can automatically block detected threats.

Industrial IDS solutions monitor:

- SCADA traffic
- PLC communications
- Industrial protocols
- Network anomalies

---

# Security Information and Event Management (SIEM)

SIEM platforms collect, correlate, and analyze security events from multiple sources.

Common log sources include:

- Firewalls
- PLC management systems
- SCADA servers
- Authentication systems
- IoT gateways
- Industrial switches
- IDS/IPS
- Cloud platforms

Benefits include:

- Centralized monitoring
- Threat detection
- Incident investigation
- Compliance reporting

---

# Continuous Monitoring

Organizations should continuously monitor:

- Device health
- Firmware versions
- Authentication events
- Network traffic
- Configuration changes
- Security alerts
- Industrial communications

Continuous monitoring improves early threat detection.

---

# Incident Response

An industrial incident response process typically includes:

1. Preparation
2. Detection
3. Analysis
4. Containment
5. Eradication
6. Recovery
7. Lessons Learned

In OT environments, containment decisions should consider operational safety before system shutdown.

---

# Backup and Recovery

Organizations should maintain secure backups of:

- Device configurations
- PLC programs
- SCADA configurations
- Historian databases
- Critical operational data

Recovery procedures should be tested regularly.

---

# User Awareness

Employees should receive training on:

- Social engineering
- Password security
- Device handling
- Reporting suspicious activity
- Safe use of removable media
- Physical security

Human awareness remains an essential layer of defense.

---

# Enterprise IoT Security Best Practices

Organizations should:

- Maintain an accurate asset inventory
- Change default credentials
- Enable strong authentication
- Encrypt sensitive communications
- Segment IoT and OT networks
- Apply vendor-approved firmware updates
- Monitor continuously using SIEM
- Deploy IDS/IPS
- Restrict administrative privileges
- Implement Zero Trust principles
- Perform regular security assessments
- Develop and test incident response plans

---

# CEH Exam Tips

Remember:

- Defense-in-depth uses multiple security layers.
- Zero Trust requires continuous verification.
- Network segmentation limits lateral movement.
- Secure Boot protects device startup.
- PKI manages certificates and cryptographic identities.
- Encryption protects data at rest and in transit.
- Industrial firewalls protect OT networks.
- IDS detects suspicious activity; IPS can block it.
- SIEM centralizes monitoring and incident detection.
- Incident response in OT must prioritize safety and availability.

---

# Key Takeaways

- Effective IoT and OT security relies on layered defenses, strong authentication, secure firmware, encryption, continuous monitoring, and well-defined operational procedures.
- Industrial environments require specialized security controls that protect both cyber assets and physical processes.
- A combination of Defense-in-Depth, Zero Trust, network segmentation, SIEM integration, and incident response planning significantly improves the resilience of connected industrial systems.

---

# Part 5 – MITRE ATT&CK for ICS, Blue Team Perspective & Module Summary

## Overview

Critical infrastructure and industrial environments require continuous monitoring because cyber incidents can affect not only information systems but also physical processes and human safety.

The **MITRE ATT&CK for ICS (Industrial Control Systems)** framework provides a structured knowledge base of adversary tactics and techniques targeting industrial environments. Security teams use it to improve detection, threat hunting, incident response, and defensive planning.

---

# MITRE ATT&CK for ICS

## What is ATT&CK for ICS?

MITRE ATT&CK for ICS documents real-world adversary behaviors against industrial environments such as:

- Manufacturing
- Power generation
- Oil and gas
- Water treatment
- Transportation
- Chemical processing
- Smart infrastructure

It helps defenders understand **how attackers operate** so that security controls and monitoring can be improved.

---

# ATT&CK for ICS Tactics

Common ATT&CK tactics include:

| ATT&CK Tactic | Purpose |
|--------------|---------|
| Initial Access | Gain access to the industrial environment |
| Execution | Execute malicious code or commands |
| Persistence | Maintain long-term access |
| Privilege Escalation | Obtain elevated permissions |
| Evasion | Avoid detection by security controls |
| Discovery | Gather information about industrial assets |
| Lateral Movement | Move between industrial systems |
| Collection | Gather operational information |
| Command and Control | Communicate with attacker infrastructure |
| Inhibit Response Function | Prevent operators from responding effectively |
| Impair Process Control | Manipulate industrial processes |
| Impact | Disrupt or damage industrial operations |

---

# Representative ATT&CK Techniques

Examples of techniques associated with industrial environments include:

- Valid Accounts
- Remote Services
- External Remote Services
- Modify Controller Logic
- Network Sniffing
- Data from Local System
- Remote File Copy
- Program Download
- Exploitation of Remote Services

> **Note:** ATT&CK techniques and IDs are updated periodically. Refer to the latest MITRE ATT&CK for ICS documentation for current mappings.

---

# Blue Team Detection Opportunities

Security teams should monitor for:

- Unauthorized engineering workstation access
- Unexpected PLC logic changes
- Unauthorized firmware updates
- New devices appearing on industrial networks
- Unexpected controller communications
- Authentication failures
- Privileged account misuse
- Configuration changes
- Abnormal industrial protocol traffic
- Unexpected remote access sessions

---

# SIEM Use Cases

Industrial environments should integrate logs into a SIEM platform.

Common log sources include:

- SCADA servers
- HMIs
- PLC management systems
- Firewalls
- IDS/IPS
- VPN gateways
- Authentication systems
- IoT gateways
- Windows/Linux servers supporting OT

Typical SIEM alerts include:

- Failed authentication attempts
- Configuration changes
- New device enrollment
- Firmware update events
- Policy violations
- Network anomalies
- Malware detections
- Unauthorized remote access

---

# Threat Hunting

Threat hunters should proactively investigate:

- Unusual PLC communications
- Unknown devices
- Unexpected engineering workstation activity
- Firmware changes
- Unauthorized remote connections
- Industrial protocol anomalies
- Repeated authentication failures
- Device compliance issues
- Unexpected cloud connectivity

Threat hunting complements automated monitoring by identifying suspicious behavior that may not trigger predefined alerts.

---

# Security Monitoring Checklist

Security teams should regularly review:

- Asset inventory
- Firmware versions
- Device identities
- Authentication logs
- Firewall logs
- IDS/IPS alerts
- Industrial protocol traffic
- Configuration changes
- Backup status
- SIEM dashboards
- Network segmentation effectiveness

---

# CEH Revision Notes

Remember:

- IoT connects physical devices through networks.
- OT controls physical processes.
- ICS is the overall industrial control environment.
- SCADA supervises industrial operations.
- PLCs automate machinery.
- RTUs collect remote sensor information.
- DCS controls continuous industrial processes.
- HMIs provide operator interfaces.
- The Purdue Model separates enterprise IT and industrial OT.
- Defense-in-Depth and Zero Trust strengthen industrial security.
- SIEM enables centralized monitoring.
- ATT&CK for ICS describes attacker behaviors against industrial environments.

---

# Interview Tips

Be prepared to explain:

- IoT architecture
- OT vs IT
- ICS components
- SCADA architecture
- PLC functionality
- HMI purpose
- Purdue Model
- Industrial communication protocols
- IoT security challenges
- Defense-in-Depth
- Zero Trust
- Network segmentation
- Industrial firewalls
- IDS vs IPS
- SIEM integration
- MITRE ATT&CK for ICS
- Incident response in OT environments

---

# Key Takeaways

- IoT and OT environments require specialized security approaches because cyber incidents can directly affect physical systems and human safety.
- Industrial cybersecurity combines asset visibility, network segmentation, strong authentication, secure firmware, continuous monitoring, and structured incident response.
- MITRE ATT&CK for ICS provides a valuable framework for understanding adversary behavior and improving defensive capabilities in industrial environments.

---

# Module Summary

Module 18 introduced the foundations of Internet of Things (IoT), Operational Technology (OT), and Industrial Control Systems (ICS). It covered IoT architectures, industrial components such as SCADA, PLCs, RTUs, DCS, and HMIs, common threats, enterprise and industrial security controls, MITRE ATT&CK for ICS, and Blue Team monitoring concepts.

These topics provide a strong foundation for the CEH certification, SOC operations, industrial cybersecurity, and critical infrastructure protection.
