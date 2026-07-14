# Module 16 – Hacking Wireless Networks

---

# Introduction to Wireless Networks

## Overview

A **wireless network** enables devices to communicate without physical cables by using radio frequency (RF) signals.

Wireless networking has become the standard communication method for homes, enterprises, educational institutions, healthcare organizations, and public infrastructure because it provides mobility, flexibility, and ease of deployment.

However, because wireless communication occurs over the air, it introduces additional security challenges that require proper authentication, encryption, monitoring, and defensive controls.

---

# What is a Wireless Local Area Network (WLAN)?

A **Wireless Local Area Network (WLAN)** connects devices within a limited geographical area using Wi-Fi technology instead of Ethernet cables.

Examples include:

- Home Wi-Fi
- Office wireless networks
- University campuses
- Airports
- Hotels
- Coffee shops

---

# Advantages of Wireless Networks

Wireless networking offers several benefits:

- Mobility
- Flexibility
- Easy deployment
- Reduced cabling costs
- Scalability
- Support for mobile devices
- Remote connectivity

---

# Limitations of Wireless Networks

Despite their advantages, wireless networks have some limitations:

- Signal interference
- Limited coverage area
- Shared bandwidth
- Lower throughput than wired networks
- Greater exposure to unauthorized access
- Environmental obstacles (walls, buildings, weather)

---

# Wireless Communication

Wireless communication uses **electromagnetic radio waves** to transmit information between devices.

Unlike wired communication, signals travel through the air instead of physical cables.

Communication depends on:

- Frequency
- Signal strength
- Channel selection
- Distance
- Environmental conditions

---

# IEEE 802.11 Standard

The **IEEE 802.11** family of standards defines how Wi-Fi networks operate.

It specifies:

- Physical layer (PHY)
- Data Link layer (MAC)
- Channel usage
- Authentication methods
- Communication procedures

---

# Common IEEE 802.11 Standards

| Standard | Frequency | Maximum Data Rate | Notes |
|-----------|-----------|------------------|------|
| 802.11a | 5 GHz | 54 Mbps | Less interference |
| 802.11b | 2.4 GHz | 11 Mbps | Longer range |
| 802.11g | 2.4 GHz | 54 Mbps | Backward compatible |
| 802.11n (Wi-Fi 4) | 2.4 / 5 GHz | Up to 600 Mbps | MIMO support |
| 802.11ac (Wi-Fi 5) | 5 GHz | Multi-Gbps | Improved speed |
| 802.11ax (Wi-Fi 6 / 6E) | 2.4 / 5 / 6 GHz | Higher efficiency | Better performance in dense environments |
| 802.11be (Wi-Fi 7) | 2.4 / 5 / 6 GHz | Extremely High Throughput (EHT) | Latest generation with improved speed and reduced latency |

---

# Wireless Network Architecture

A basic wireless network consists of:

```
Internet
    │
Router
    │
Access Point
    │
~~~~~~~~~~~~~~~~~~~~
Wireless Devices
```

The **Access Point (AP)** provides wireless connectivity between client devices and the wired network.

---

# Infrastructure Mode

Infrastructure Mode is the most common wireless deployment.

Characteristics:

- Uses an Access Point
- Centralized communication
- Internet connectivity
- Common in homes and enterprises

---

# Ad Hoc Mode

Ad Hoc Mode allows devices to communicate directly without an Access Point.

Characteristics:

- Peer-to-peer communication
- Temporary networks
- No centralized management
- Limited scalability

---

# Wireless Network Components

## Access Point (AP)

An Access Point connects wireless devices to a wired network.

Functions:

- Broadcasts wireless signals
- Manages client connections
- Enforces authentication
- Applies encryption policies

---

## Wireless Client

A wireless client is any device that connects to a Wi-Fi network.

Examples:

- Laptop
- Smartphone
- Tablet
- Smart TV
- IoT devices
- Printers

---

## Wireless Router

A wireless router combines:

- Router
- Switch
- Access Point

It provides Internet access and manages local wireless communication.

---

# SSID (Service Set Identifier)

The **SSID** is the human-readable name of a wireless network.

Examples:

- Office-WiFi
- Home_Network
- Guest_WiFi

The SSID helps users identify available wireless networks.

---

# BSSID (Basic Service Set Identifier)

A **BSSID** uniquely identifies an individual Access Point.

Characteristics:

- Based on the AP's MAC address
- Unique for each Access Point
- Used internally by wireless devices

---

# ESSID (Extended Service Set Identifier)

An **ESSID** allows multiple Access Points to share the same network name.

Benefits:

- Roaming support
- Larger wireless coverage
- Enterprise deployments

---

# Frequency Bands

## 2.4 GHz

Advantages:

- Longer range
- Better wall penetration

Disadvantages:

- More interference
- Fewer non-overlapping channels

---

## 5 GHz

Advantages:

- Higher speeds
- Less interference
- More available channels

Disadvantages:

- Shorter range
- Reduced wall penetration

---

## 6 GHz

Advantages:

- Higher bandwidth
- Lower latency
- Less congestion
- Supports Wi-Fi 6E and Wi-Fi 7

Disadvantages:

- Shorter effective range
- Requires compatible hardware

---

# Wireless Channels

Wi-Fi networks communicate over channels within each frequency band.

Proper channel selection helps:

- Reduce interference
- Improve performance
- Increase reliability

---

# Why Wireless Networks Need Security

Unlike wired networks, wireless signals travel through the air and can potentially be received by nearby devices.

Without proper security, organizations may face risks such as:

- Unauthorized access
- Data interception
- Information disclosure
- Service disruption
- Device impersonation

---

# CEH Exam Tips

Remember:

- IEEE 802.11 defines Wi-Fi standards.
- Infrastructure Mode uses an Access Point.
- Ad Hoc Mode enables peer-to-peer communication.
- SSID is the wireless network name.
- BSSID uniquely identifies an Access Point.
- 2.4 GHz offers greater range, while 5 GHz generally provides higher speeds.
- Wi-Fi 6 (802.11ax) improves efficiency in dense environments.
- Wi-Fi 7 (802.11be) introduces Extremely High Throughput (EHT).

---

# Key Takeaways

- Wireless networks provide mobility and flexibility but require strong security controls.
- Understanding WLAN architecture, IEEE 802.11 standards, wireless components, and frequency bands is essential before studying wireless authentication, encryption, and security threats.

---

# Wireless Authentication and Security

## Overview

Wireless authentication verifies the identity of devices before granting access to a wireless network.

Modern Wi-Fi security combines:

- Authentication
- Authorization
- Encryption
- Access Control

Together, these mechanisms protect wireless communications against unauthorized access.

---

# Authentication vs Authorization

## Authentication

Authentication verifies **who** the user or device is.

Examples:

- Password
- Digital certificate
- Enterprise credentials

---

## Authorization

Authorization determines **what resources** an authenticated user or device is permitted to access.

Examples:

- Guest Wi-Fi
- Employee Wi-Fi
- Administrator Network

---

# Open Authentication

Open Authentication allows devices to associate with a wireless network without verifying identity.

Characteristics:

- No password required
- Common on public Wi-Fi
- Minimal security

Examples:

- Airports
- Hotels
- Cafés

---

# Wi-Fi Protected Access (WPA)

WPA was introduced to replace the insecure WEP protocol.

Features:

- Improved authentication
- Better encryption
- Dynamic key generation

Although more secure than WEP, WPA has largely been replaced by WPA2 and WPA3.

---

# WPA2

WPA2 became the long-standing wireless security standard.

Features:

- AES encryption
- CCMP protocol
- Stronger authentication
- Better protection than WPA

WPA2 remains widely deployed but should be upgraded to WPA3 where possible.

---

# WPA3

WPA3 is the latest Wi-Fi security standard.

Advantages include:

- Stronger authentication
- Improved encryption
- Better protection against password guessing
- Enhanced security for public Wi-Fi
- Forward secrecy
- Improved resilience against modern attacks

WPA3 is the recommended standard for new deployments.

---

# Personal vs Enterprise Security

## WPA Personal (WPA-PSK)

Characteristics:

- Shared password
- Simple deployment
- Suitable for homes and small offices

Advantages:

- Easy to configure
- Low administrative overhead

Limitations:

- Shared credentials
- Difficult user management
- Password sharing risks

---

## WPA Enterprise

Characteristics:

- Individual user authentication
- Uses IEEE 802.1X
- Integrates with authentication servers

Advantages:

- Centralized management
- Individual user accounts
- Better auditing
- Improved security

Common in:

- Enterprises
- Universities
- Government organizations
- Hospitals

---

# IEEE 802.1X

IEEE 802.1X is a network access control standard used in enterprise environments.

It provides:

- User authentication
- Device authentication
- Centralized access control

Benefits:

- Strong authentication
- Improved security
- Scalable management

---

# RADIUS Server

A **Remote Authentication Dial-In User Service (RADIUS)** server manages authentication requests for enterprise wireless networks.

Functions:

- Authentication
- Authorization
- Accounting (AAA)

Advantages:

- Centralized authentication
- User management
- Logging and auditing
- Policy enforcement

---

# Wireless Encryption

Encryption protects wireless data from unauthorized access during transmission.

Modern Wi-Fi primarily uses AES-based encryption.

---

# WEP (Wired Equivalent Privacy)

WEP was the first widely adopted Wi-Fi security protocol.

Characteristics:

- Legacy protocol
- Weak encryption
- Deprecated

WEP should **never** be used in production environments.

---

# TKIP (Temporal Key Integrity Protocol)

TKIP was introduced as a temporary improvement over WEP.

Characteristics:

- Better than WEP
- Transitional technology
- Legacy support only

TKIP has also been deprecated.

---

# AES (Advanced Encryption Standard)

AES is the current encryption standard for modern wireless networks.

Benefits:

- Strong encryption
- Efficient performance
- Government-approved encryption algorithm
- Widely supported

---

# CCMP (Counter Mode with CBC-MAC Protocol)

CCMP is the encryption protocol used with AES in WPA2.

Benefits:

- Data confidentiality
- Data integrity
- Authentication
- Replay protection

---

# GCMP (Galois/Counter Mode Protocol)

GCMP is used in newer Wi-Fi standards, including WPA3.

Advantages:

- Higher performance
- Improved efficiency
- Strong security

---

# Protected Management Frames (PMF)

Protected Management Frames improve wireless security by protecting management traffic.

Benefits:

- Prevents management frame tampering
- Reduces spoofing risks
- Improves wireless resilience

PMF is mandatory for WPA3-certified devices.

---

# Strong Password Policy

Wireless networks should use:

- Long passphrases
- Complex passwords
- Unique credentials
- Regular password updates
- Multi-factor authentication where applicable

---

# Enterprise Best Practices

Organizations should:

- Deploy WPA3 whenever possible
- Use Enterprise authentication
- Implement IEEE 802.1X
- Use RADIUS servers
- Disable legacy protocols
- Enable Protected Management Frames
- Regularly update firmware
- Monitor authentication logs

---

# CEH Exam Tips

Remember:

- WEP is deprecated and insecure.
- TKIP is a legacy protocol.
- AES is the recommended encryption algorithm.
- CCMP is associated with WPA2.
- GCMP is commonly used with WPA3.
- WPA3 provides stronger security than WPA2.
- IEEE 802.1X is used for Enterprise authentication.
- RADIUS provides Authentication, Authorization, and Accounting (AAA).
- Protected Management Frames (PMF) help secure management traffic.

---

# Key Takeaways

- Modern wireless security depends on strong authentication, robust encryption, and centralized access control.
- WPA3, AES, IEEE 802.1X, and RADIUS represent current best practices for enterprise wireless deployments.
- Legacy protocols such as WEP and TKIP should be avoided due to known security weaknesses.

---

# Wireless Threats and Attack Concepts

## Overview

Wireless networks are inherently more exposed than wired networks because radio signals propagate through the air. Attackers within signal range may attempt to intercept, disrupt, or misuse wireless communications if adequate security controls are not in place.

Understanding common wireless threats helps security professionals implement effective preventive and detective controls.

---

# Common Wireless Threats

Wireless networks may face threats such as:

- Unauthorized network access
- Rogue devices
- Weak authentication
- Signal interception
- Network disruption
- Device impersonation
- Social engineering

---

# Rogue Access Point (Rogue AP)

## Overview

A Rogue Access Point is an unauthorized wireless access point connected to an organization's network.

It may be installed intentionally or unintentionally by employees or attackers.

### Risks

- Unauthorized network access
- Security policy violations
- Data exposure
- Bypass of security controls

### Defensive Controls

- Wireless IDS/IPS (WIDS/WIPS)
- Network Access Control (NAC)
- Regular wireless audits
- Rogue AP detection tools
- Asset inventory management

---

# Evil Twin Network

## Overview

An Evil Twin is a fraudulent wireless network designed to imitate a legitimate Wi-Fi network.

Users may unknowingly connect if the network name appears trustworthy.

### Potential Impact

- Credential theft
- Traffic interception
- User deception
- Session compromise

### Defensive Controls

- WPA3 Enterprise
- Certificate validation
- User awareness training
- Disable automatic Wi-Fi connections
- Wireless monitoring

---

# Packet Sniffing

## Overview

Packet sniffing refers to capturing and analyzing network traffic.

In authorized environments, packet analysis is used for:

- Troubleshooting
- Network monitoring
- Incident response
- Security investigations

If wireless traffic is not adequately protected, sensitive information may be exposed.

### Defensive Controls

- WPA3 encryption
- HTTPS
- VPN usage
- Strong authentication
- Encrypted application protocols

---

# MAC Address Spoofing

## Overview

Every network interface has a unique MAC (Media Access Control) address.

Attackers may attempt to impersonate another device by changing the MAC address presented to the network.

### Risks

- Bypass weak MAC-based filtering
- Device impersonation
- Unauthorized access attempts

### Defensive Controls

- IEEE 802.1X authentication
- NAC
- Device certificates
- Continuous monitoring

---

# Replay Attacks

## Overview

In a replay attack, previously captured network communications are retransmitted in an attempt to achieve an unauthorized result.

### Defensive Controls

- WPA3
- Nonce-based protocols
- Session validation
- Modern encryption protocols
- Timestamp verification

---

# Deauthentication Attacks (Conceptual)

## Overview

Wireless networks exchange management frames to control client connectivity.

If these management frames are not protected, an attacker may attempt to force devices to disconnect from a wireless network.

### Potential Impact

- Service interruption
- Temporary loss of connectivity
- User frustration
- Opportunity for social engineering

### Defensive Controls

- Protected Management Frames (PMF)
- WPA3
- Wireless IDS/IPS
- Continuous wireless monitoring

---

# Wireless Denial of Service (DoS)

## Overview

Wireless Denial of Service attempts to reduce or interrupt the availability of wireless communication.

Possible effects include:

- Slow network performance
- Client disconnections
- Reduced availability
- Business disruption

### Defensive Controls

- RF monitoring
- Redundant access points
- Wireless IDS/IPS
- Proper channel planning

---

# Radio Frequency (RF) Jamming

## Overview

RF jamming occurs when excessive radio interference disrupts legitimate wireless communication.

### Impact

- Signal degradation
- Connection failures
- Reduced network availability

### Defensive Controls

- RF spectrum analysis
- Wireless monitoring
- Channel optimization
- Physical security

---

# Weak Wireless Passwords

Weak or predictable passwords significantly reduce wireless security.

Examples of poor practices:

- Default passwords
- Short passwords
- Shared passwords
- Dictionary words
- Password reuse

### Best Practices

- Long passphrases
- Complex passwords
- Unique credentials
- Password rotation where appropriate
- Multi-factor authentication for enterprise environments

---

# Social Engineering Against Wi-Fi Users

Attackers may use deception rather than technical exploitation.

Examples include:

- Fake captive portals
- Phishing pages
- Fake support requests
- Fraudulent hotspot names

### Defensive Controls

- Security awareness training
- Verify network names
- Use VPN on public Wi-Fi
- Validate certificates
- Report suspicious networks

---

# Wireless Security Monitoring

Security teams should monitor for:

- Unknown access points
- Unexpected SSIDs
- Authentication failures
- Sudden client disconnections
- Unusual wireless traffic
- Excessive management frames
- RF interference
- Unauthorized devices

---

# Blue Team Detection Opportunities

Indicators of suspicious activity include:

- New or unauthorized access points
- Large numbers of failed authentication attempts
- Unexpected changes in wireless clients
- Repeated client disconnects
- Abnormal signal patterns
- Excessive broadcast traffic
- High-volume management frame activity

---

# CEH Exam Tips

Remember:

- Rogue APs are unauthorized access points.
- Evil Twin networks imitate legitimate Wi-Fi networks.
- Packet sniffing can be legitimate for monitoring or malicious if unauthorized.
- MAC addresses identify network interfaces but should not be relied upon as the sole security control.
- WPA3 and Protected Management Frames (PMF) improve protection against management frame abuse.
- User awareness is an important layer of wireless security.

---

# Key Takeaways

- Wireless networks face unique security challenges because communication occurs over radio frequencies.
- Common threats include rogue access points, Evil Twin networks, packet sniffing, MAC spoofing, replay attacks, deauthentication, RF interference, and social engineering.
- A layered defense—including WPA3, IEEE 802.1X, PMF, WIDS/WIPS, continuous monitoring, and user awareness—significantly improves wireless security.

---

# Wireless Network Defense and Security Best Practices

## Overview

Securing a wireless network requires more than strong encryption. Organizations should adopt a **defense-in-depth** approach by combining secure configuration, strong authentication, continuous monitoring, user awareness, and regular security assessments.

---

# Defense-in-Depth

Defense-in-depth applies multiple layers of security to reduce the likelihood and impact of an attack.

Typical layers include:

- Secure wireless configuration
- Strong authentication
- Encryption
- Network segmentation
- Wireless monitoring
- Endpoint security
- Logging and SIEM
- User awareness training

---

# Wireless Security Best Practices

Organizations should:

- Deploy WPA3 whenever possible
- Disable legacy protocols such as WEP and TKIP
- Use strong, unique passphrases
- Change default administrator credentials
- Keep firmware updated
- Disable unnecessary wireless features
- Regularly review wireless configurations
- Conduct periodic security assessments

---

# Network Segmentation

Wireless users should be separated based on business requirements.

Examples:

- Corporate Wi-Fi
- Guest Wi-Fi
- IoT devices
- BYOD (Bring Your Own Device)

### Benefits

- Limits lateral movement
- Protects sensitive systems
- Improves access control
- Reduces attack surface

---

# Network Access Control (NAC)

Network Access Control verifies that users and devices meet organizational security requirements before granting network access.

### Functions

- User authentication
- Device authentication
- Policy enforcement
- Compliance verification
- Access restriction

### Benefits

- Prevents unauthorized devices
- Improves visibility
- Supports Zero Trust principles

---

# Wireless Intrusion Detection System (WIDS)

A **Wireless Intrusion Detection System (WIDS)** monitors wireless activity and alerts administrators to suspicious events.

### Capabilities

- Detect rogue access points
- Identify unauthorized devices
- Monitor authentication failures
- Detect unusual wireless behavior
- Generate security alerts

---

# Wireless Intrusion Prevention System (WIPS)

A **Wireless Intrusion Prevention System (WIPS)** extends WIDS by helping prevent or contain detected threats.

### Functions

- Block unauthorized devices
- Enforce wireless security policies
- Detect policy violations
- Reduce wireless attack exposure

---

# Rogue Access Point Detection

Organizations should continuously monitor for unauthorized wireless devices.

Detection methods include:

- Wireless surveys
- RF monitoring
- WIDS/WIPS
- Asset inventory comparison
- Scheduled security audits

---

# Wireless Monitoring

Continuous monitoring improves visibility into wireless activity.

Monitor for:

- New access points
- Unknown SSIDs
- Client associations
- Authentication failures
- Signal anomalies
- RF interference
- Configuration changes

---

# Logging and SIEM Integration

Wireless infrastructure should send logs to a centralized SIEM platform.

Important log sources:

- Wireless controllers
- Access points
- RADIUS servers
- Authentication servers
- NAC solutions
- Firewalls

### Benefits

- Centralized visibility
- Correlation of events
- Faster incident detection
- Compliance reporting

---

# Enterprise Authentication

Enterprise environments should implement:

- IEEE 802.1X
- RADIUS authentication
- Individual user accounts
- Certificate-based authentication (where applicable)
- Role-Based Access Control (RBAC)

Benefits:

- Centralized identity management
- Better auditing
- Improved accountability

---

# Zero Trust for Wireless Networks

Zero Trust assumes that no user or device should be trusted by default.

Key principles:

- Verify identity continuously
- Apply least privilege
- Monitor all access
- Validate device posture
- Restrict unnecessary permissions

---

# Firmware and Patch Management

Keep wireless infrastructure updated.

Regularly update:

- Access Points
- Wireless controllers
- Routers
- Client devices
- Authentication servers

Benefits:

- Fix known vulnerabilities
- Improve stability
- Enhance security features

---

# User Awareness

Technology alone cannot secure wireless networks.

Organizations should educate users to:

- Verify network names (SSID)
- Avoid unknown Wi-Fi networks
- Use VPNs on public Wi-Fi
- Report suspicious access points
- Protect wireless credentials
- Keep devices updated

---

# Incident Response

If suspicious wireless activity is detected:

1. Identify the affected network or device.
2. Preserve logs and evidence.
3. Contain unauthorized access.
4. Investigate the root cause.
5. Remove unauthorized devices if confirmed.
6. Update configurations or credentials if required.
7. Monitor for recurring activity.
8. Document lessons learned.

---

# Security Testing

Regular wireless security assessments should include:

- Wireless configuration reviews
- Rogue AP detection
- Coverage assessments
- Authentication testing
- Encryption verification
- Firmware review
- Compliance checks

---

# CEH Exam Tips

Remember:

- WPA3 is the preferred wireless security standard.
- WIDS detects suspicious wireless activity.
- WIPS helps prevent or contain wireless threats.
- NAC controls which users and devices can access the network.
- Network segmentation reduces the impact of compromise.
- SIEM improves centralized monitoring and incident detection.
- Zero Trust applies to wireless environments by continuously verifying users and devices.

---

# Key Takeaways

- Effective wireless security requires multiple layers of protection rather than relying on a single control.
- Strong authentication, modern encryption, continuous monitoring, WIDS/WIPS, NAC, network segmentation, and user awareness are key components of a secure wireless environment.
- Regular security assessments and timely updates help organizations maintain a resilient wireless infrastructure.

---

# MITRE ATT&CK Mapping, Blue Team Perspective & Module Summary

## Overview

Wireless attacks often target authentication mechanisms, wireless infrastructure, or users connected to Wi-Fi networks. While many wireless attack methods are not individual MITRE ATT&CK techniques, they can enable adversary behaviors that align with multiple ATT&CK tactics.

Understanding these mappings helps defenders improve monitoring, threat hunting, and incident response.

---

# MITRE ATT&CK Tactics Related to Wireless Threats

| ATT&CK Tactic | Relevance |
|--------------|-----------|
| Initial Access | Compromising wireless access points or user connectivity. |
| Discovery | Identifying wireless devices, access points, or network information. |
| Credential Access | Obtaining wireless authentication credentials. |
| Collection | Capturing sensitive network traffic or user data. |
| Defense Evasion | Avoiding wireless monitoring and security controls. |
| Impact | Disrupting wireless availability or services. |

---

# Common ATT&CK Techniques

| Technique | ATT&CK ID | Relevance |
|-----------|-----------|-----------|
| Exploit Public-Facing Application | T1190 | May be used if wireless management interfaces are exposed. |
| Valid Accounts | T1078 | Use of compromised wireless or enterprise credentials. |
| Data from Information Repositories | T1213 | Accessing sensitive information after network access is obtained. |
| Network Sniffing | T1040 | Capturing network traffic where protections are inadequate. |
| Endpoint Denial of Service | T1499 | Disrupting wireless services or client connectivity. |

> **Note:** MITRE ATT&CK documents adversary behavior. It does not document Wi-Fi protocols themselves.

---

# Blue Team Detection Opportunities

Security teams should monitor for:

- Rogue Access Points
- Unknown SSIDs
- Unexpected client associations
- Authentication failures
- Multiple failed connection attempts
- Repeated client disconnects
- RF interference
- Unexpected administrator logins
- Unauthorized configuration changes
- Abnormal wireless traffic volumes

---

# SIEM Use Cases

SIEM platforms can generate alerts for:

- Rogue AP detection
- Authentication anomalies
- Failed IEEE 802.1X authentications
- RADIUS failures
- Unexpected wireless controller changes
- Excessive client disconnections
- Large authentication spikes
- Wireless infrastructure configuration changes

Common SIEM platforms include:

- Splunk
- Microsoft Sentinel
- IBM QRadar
- Elastic Security
- Wazuh

---

# Wireless Threat Hunting

Threat hunters should investigate:

- New wireless devices
- Unknown MAC addresses
- Unauthorized SSIDs
- Changes in wireless coverage
- RF interference
- Authentication anomalies
- Configuration drift
- Excessive management traffic
- Abnormal roaming behavior

---

# Security Monitoring Checklist

Regularly review:

- Access Point health
- Wireless controller logs
- RADIUS logs
- Authentication failures
- Firmware versions
- Client inventories
- Rogue AP reports
- WIDS/WIPS alerts
- SIEM dashboards

---

# CEH Revision Notes

Remember:

- IEEE 802.11 defines Wi-Fi standards.
- Infrastructure Mode uses an Access Point.
- WPA3 is the recommended wireless security standard.
- WPA2 remains widely deployed.
- WEP and TKIP are deprecated.
- IEEE 802.1X provides enterprise authentication.
- RADIUS supports Authentication, Authorization, and Accounting (AAA).
- Protected Management Frames (PMF) improve management frame security.
- WIDS detects suspicious wireless activity.
- WIPS helps prevent wireless attacks.
- NAC controls user and device access.
- Network segmentation limits lateral movement.

---

# Interview Tips

Be prepared to explain:

- Wireless networking fundamentals
- IEEE 802.11 standards
- Difference between WPA2 and WPA3
- Personal vs Enterprise Wi-Fi
- Role of IEEE 802.1X
- RADIUS authentication
- Rogue Access Points
- Evil Twin networks
- WIDS vs WIPS
- Network segmentation
- NAC
- Zero Trust in wireless environments
- Wireless monitoring
- SIEM integration

---

# Key Takeaways

- Wireless communication introduces unique security challenges because transmissions occur over radio frequencies.
- Strong authentication, WPA3, IEEE 802.1X, RADIUS, Protected Management Frames (PMF), and network segmentation significantly improve wireless security.
- Continuous monitoring using WIDS/WIPS, SIEM, and regular security assessments helps organizations detect and respond to wireless threats.
- User awareness and secure configuration are essential components of a defense-in-depth strategy.

---

# Module Summary

Module 16 introduced wireless networking fundamentals, IEEE 802.11 standards, Wi-Fi authentication and encryption, common wireless threats, enterprise wireless security controls, defensive monitoring, MITRE ATT&CK mapping, and Blue Team detection strategies.

These concepts provide a strong foundation for CEH certification, wireless security assessments, SOC monitoring, and enterprise network security.
