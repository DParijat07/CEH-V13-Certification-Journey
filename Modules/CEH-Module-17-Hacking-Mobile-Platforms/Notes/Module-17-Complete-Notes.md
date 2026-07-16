# Module 17 – Hacking Mobile Platforms

---

# Mobile Platform Fundamentals

## Overview

Mobile devices have become essential for communication, business, banking, healthcare, education, and enterprise operations. Because they store sensitive personal and organizational data, smartphones and tablets are attractive targets for cyber attackers.

Understanding mobile operating systems, device architecture, communication technologies, and security models is essential for defending modern mobile environments.

---

# What is Mobile Computing?

Mobile computing refers to the use of portable computing devices that communicate over wireless networks while allowing users to access data and services from virtually anywhere.

Examples include:

- Smartphones
- Tablets
- Smartwatches
- Rugged mobile devices
- Mobile Point-of-Sale (mPOS) terminals

---

# Characteristics of Mobile Computing

Key characteristics include:

- Portability
- Wireless connectivity
- Mobility
- Always-on communication
- Cloud integration
- Sensor-based functionality
- Location awareness

---

# Mobile Device Components

A modern mobile device consists of both hardware and software components.

### Hardware Components

- Processor (CPU)
- Graphics Processing Unit (GPU)
- Memory (RAM)
- Internal Storage
- Battery
- Display
- Camera
- Microphone
- Speakers
- SIM/eSIM
- Wi-Fi Adapter
- Bluetooth Module
- NFC Chip
- GPS Receiver

---

### Software Components

- Operating System
- Applications
- System Services
- Security Framework
- Device Drivers
- File System

---

# Mobile Operating Systems

A Mobile Operating System (Mobile OS) manages hardware resources, applications, user interfaces, and security controls.

The two dominant mobile operating systems are:

- Android
- iOS

Other platforms include:

- HarmonyOS
- KaiOS
- Embedded Linux-based mobile systems

---

# Android Overview

Android is an open-source mobile operating system developed by Google.

Characteristics:

- Linux-based kernel
- Highly customizable
- Large application ecosystem
- Google Play Store
- Used by multiple manufacturers

Common manufacturers include:

- Samsung
- Google
- Xiaomi
- OnePlus
- Motorola
- Nothing

---

# iOS Overview

iOS is Apple's proprietary mobile operating system.

Characteristics:

- Closed ecosystem
- Strong security architecture
- Tight hardware and software integration
- App Store ecosystem
- Regular security updates

Supported devices include:

- iPhone
- Certain iPad models (historically, before iPadOS separation)

---

# Mobile Ecosystem

The mobile ecosystem includes:

- Mobile devices
- Operating systems
- Applications
- App stores
- Cloud services
- Wireless networks
- Mobile users
- Enterprise management platforms

---

# Mobile Communication Technologies

Mobile devices communicate using multiple wireless technologies, including:

- Cellular (3G, 4G LTE, 5G)
- Wi-Fi
- Bluetooth
- Near Field Communication (NFC)
- GPS
- Satellite positioning services

---

# SIM and eSIM

## SIM (Subscriber Identity Module)

A SIM stores subscriber identity information used by cellular networks.

Functions include:

- User identification
- Network authentication
- Subscriber information

---

## eSIM

An eSIM (Embedded SIM) is a programmable SIM integrated into the device hardware.

Advantages include:

- Remote provisioning
- Multiple carrier profiles
- Improved flexibility
- Reduced physical hardware requirements

---

# Mobile Applications

Mobile applications (Apps) extend device functionality.

Categories include:

- Productivity
- Banking
- Healthcare
- Communication
- Social Media
- Navigation
- Enterprise
- Entertainment

Applications are typically installed from trusted application stores.

---

# App Distribution Platforms

Common application marketplaces include:

- Google Play Store
- Apple App Store
- Enterprise App Stores
- Managed corporate application repositories

Organizations should encourage users to install applications only from trusted sources.

---

# Enterprise Mobile Usage

Organizations commonly use mobile devices for:

- Email
- Collaboration
- VPN access
- Cloud services
- Business applications
- Multi-factor authentication
- Secure communications

Enterprise mobile security is therefore an important component of cybersecurity programs.

---

# Mobile Security Challenges

Common challenges include:

- Lost or stolen devices
- Malicious applications
- Weak authentication
- Data leakage
- Untrusted wireless networks
- Outdated software
- Social engineering
- User privacy concerns

---

# CEH Exam Tips

Remember:

- Android is Linux-based.
- iOS is Apple's proprietary mobile operating system.
- Smartphones communicate using multiple wireless technologies.
- Mobile devices contain both hardware and software security components.
- Enterprise environments commonly manage mobile devices using centralized security controls.

---

# Key Takeaways

- Mobile devices are critical computing platforms that require strong security controls.
- Android and iOS dominate the mobile operating system market.
- Mobile computing relies on wireless communication technologies such as cellular networks, Wi-Fi, Bluetooth, NFC, and GPS.
- Understanding mobile architecture provides the foundation for learning mobile security, threats, and enterprise defense strategies.

---

# Android and iOS Security

## Overview

Android and iOS are designed with multiple built-in security mechanisms to protect users, applications, and sensitive data.

Modern mobile operating systems implement **defense-in-depth**, combining secure boot processes, application sandboxing, encryption, permission models, hardware-backed security, and regular security updates.

---

# Android Security

## Android Architecture

Android consists of several layers:

- Linux Kernel
- Hardware Abstraction Layer (HAL)
- Native Libraries
- Android Runtime (ART)
- Application Framework
- Applications

Each layer contributes to the overall security of the operating system.

---

# Linux Kernel

Android uses a Linux-based kernel.

The kernel is responsible for:

- Process management
- Memory management
- Device drivers
- File system management
- Network communication
- Security enforcement

---

# Android Application Sandbox

Each Android application runs inside its own sandbox.

Benefits include:

- Isolation between applications
- Reduced unauthorized data access
- Improved system stability
- Better security

Applications cannot freely access another application's data without explicit permission.

---

# Permission Model

Android applications must request permission before accessing sensitive resources.

Examples include:

- Camera
- Microphone
- Contacts
- SMS
- Location
- Storage

Users can review and manage permissions through device settings.

---

# Application Signing

Every Android application must be digitally signed before installation.

Benefits:

- Verifies application integrity
- Identifies the application developer
- Helps prevent unauthorized modification

---

# Secure Boot and Verified Boot

Android verifies software integrity during startup.

These mechanisms help ensure that only trusted software is loaded.

Benefits:

- Detects unauthorized modifications
- Protects operating system integrity
- Improves device security

---

# Google Play Protect

Google Play Protect helps improve application security by:

- Scanning installed applications
- Detecting potentially harmful apps
- Performing continuous security checks
- Helping users identify unsafe applications

---

# Android Keystore

Android Keystore provides secure storage for cryptographic keys.

Benefits:

- Hardware-backed protection (on supported devices)
- Secure key management
- Protection against key extraction

---

# SELinux

Security-Enhanced Linux (SELinux) enforces mandatory access control within Android.

Benefits:

- Restricts unauthorized access
- Limits application privileges
- Reduces the impact of vulnerabilities

---

# Android Security Updates

Google and device manufacturers regularly release security updates that:

- Patch vulnerabilities
- Improve platform security
- Address newly discovered threats

Keeping devices updated is an important security best practice.

---

# iOS Security

## iOS Architecture

iOS uses a layered security architecture designed to protect applications, user data, and system resources.

Security is built into both the hardware and software.

---

# Secure Boot Chain

The iOS boot process verifies each stage before loading the next.

Benefits:

- Ensures software integrity
- Prevents unauthorized operating systems
- Protects against boot-level tampering

---

# Code Signing

Every iOS application must be digitally signed before it can run.

Benefits:

- Verifies application authenticity
- Prevents unauthorized code execution
- Protects platform integrity

---

# Application Sandbox

Each iOS application operates within its own isolated environment.

Benefits:

- Application isolation
- Reduced unauthorized access
- Improved privacy
- Enhanced system security

---

# Secure Enclave

The Secure Enclave is a dedicated hardware security component found in modern Apple devices.

Functions include:

- Protecting biometric data
- Secure cryptographic operations
- Hardware-backed key protection

---

# Face ID and Touch ID

Apple provides biometric authentication through:

- Face ID
- Touch ID

Benefits:

- Strong user authentication
- Convenient access
- Secure identity verification

---

# Keychain

The iOS Keychain securely stores sensitive information such as:

- Passwords
- Certificates
- Cryptographic keys
- Authentication tokens

Applications can securely access Keychain data using approved APIs.

---

# Data Protection

iOS protects user data through encryption and controlled access.

Features include:

- File encryption
- Hardware-backed security
- Controlled access based on device state
- Secure data storage

---

# App Store Security

Apple reviews applications before publication on the App Store.

Objectives include:

- Malware reduction
- Policy compliance
- Improved application quality
- Better user protection

---

# Security Updates

Apple regularly releases security updates to:

- Patch vulnerabilities
- Improve platform security
- Address newly discovered threats

Users should install updates promptly.

---

# Android vs iOS Security

| Feature | Android | iOS |
|---------|----------|------|
| Kernel | Linux | XNU |
| App Store | Google Play | Apple App Store |
| Application Sandbox | Yes | Yes |
| Code Signing | Yes | Yes |
| Secure Boot | Yes | Yes |
| Hardware Security | Android Keystore | Secure Enclave |
| Permission Model | Runtime Permissions | Privacy Permissions |
| Security Updates | Google + OEM | Apple |

---

# Mobile Security Best Practices

Users should:

- Keep devices updated
- Install applications only from trusted sources
- Review application permissions
- Enable screen lock
- Use biometric authentication
- Enable device encryption
- Use multi-factor authentication (MFA)
- Remove unused applications
- Avoid untrusted Wi-Fi networks

---

# CEH Exam Tips

Remember:

- Android is Linux-based.
- Every application runs inside its own sandbox.
- Android applications require digital signatures.
- Google Play Protect helps identify harmful applications.
- Android Keystore protects cryptographic keys.
- SELinux provides mandatory access control.
- iOS uses Secure Boot, Code Signing, and Secure Enclave.
- Keychain securely stores passwords and cryptographic material.
- Regular security updates improve protection on both Android and iOS.

---

# Key Takeaways

- Android and iOS implement multiple security mechanisms to protect applications, devices, and user data.
- Features such as sandboxing, secure boot, code signing, hardware-backed security, encryption, and regular updates form the foundation of modern mobile platform security.
- Following security best practices and keeping devices updated significantly reduces the risk of compromise.

---

# Mobile Threats and Attack Concepts

## Overview

Mobile devices are valuable targets because they store sensitive personal and organizational data while providing access to business applications, cloud services, and financial accounts.

Understanding common mobile threats enables security professionals to implement effective preventive, detective, and responsive security controls.

---

# Common Mobile Threats

Organizations should be aware of threats such as:

- Mobile malware
- Spyware
- Ransomware
- Banking trojans
- Malicious applications
- Phishing (Smishing)
- Data leakage
- Device theft
- Insecure wireless connections
- SIM swapping
- Social engineering

---

# Mobile Malware

## Overview

Mobile malware refers to malicious software designed to compromise smartphones or tablets.

Potential impact includes:

- Data theft
- Privacy violations
- Financial loss
- Unauthorized device control

### Defensive Controls

- Install apps only from trusted sources
- Keep the OS updated
- Use Mobile Threat Defense (MTD)
- Monitor device behavior
- Educate users

---

# Spyware

## Overview

Spyware secretly collects information from a mobile device without the user's knowledge.

Potential targets include:

- Messages
- Contacts
- Call history
- Location
- Browsing activity

### Defensive Controls

- Review app permissions
- Remove unnecessary apps
- Install security updates
- Monitor unusual behavior

---

# Ransomware

## Overview

Mobile ransomware attempts to deny access to data or device functionality until a ransom is paid.

Potential impact:

- File encryption
- Device lockout
- Business disruption
- Data loss

### Defensive Controls

- Maintain backups
- Update software
- Install apps from trusted stores
- Use endpoint protection

---

# Banking Trojans

## Overview

Banking trojans target financial applications to steal sensitive information.

Potential impact:

- Credential theft
- Financial fraud
- Unauthorized transactions

### Defensive Controls

- Enable Multi-Factor Authentication (MFA)
- Use official banking applications
- Monitor financial activity
- Keep applications updated

---

# Adware

## Overview

Adware displays excessive or unwanted advertisements and may collect user information.

Potential impact:

- Reduced performance
- Privacy concerns
- Poor user experience

### Defensive Controls

- Install trusted applications
- Review permissions
- Remove suspicious software

---

# Smishing (SMS Phishing)

## Overview

Smishing is a phishing attack delivered through SMS or messaging applications.

Attackers attempt to convince users to:

- Reveal credentials
- Install malicious apps
- Visit fraudulent websites

### Defensive Controls

- Verify sender identity
- Avoid suspicious links
- Educate users
- Report phishing attempts

---

# Malicious Applications

## Overview

Malicious applications may disguise themselves as legitimate software.

Potential risks:

- Credential theft
- Data collection
- Privacy violations
- Device compromise

### Defensive Controls

- Download apps only from trusted stores
- Verify developer information
- Review requested permissions
- Remove unused applications

---

# Insecure Wi-Fi Networks

## Overview

Public or poorly secured Wi-Fi networks increase security risks for mobile users.

Potential impact:

- Data interception
- Session compromise
- Credential exposure

### Defensive Controls

- Use VPNs
- Prefer HTTPS
- Avoid sensitive transactions on public Wi-Fi
- Disable automatic Wi-Fi connections

---

# Bluetooth Threats

## Overview

Bluetooth provides short-range wireless communication between devices.

Security risks include:

- Unauthorized pairing
- Data exposure
- Device discovery abuse

### Defensive Controls

- Disable Bluetooth when unused
- Use trusted devices only
- Keep Bluetooth software updated
- Disable discoverable mode when unnecessary

---

# NFC Risks

## Overview

Near Field Communication (NFC) enables short-range contactless communication.

Potential risks:

- Unauthorized transactions
- Data exposure
- Device misuse

### Defensive Controls

- Disable NFC when unused
- Use secure payment applications
- Verify payment requests

---

# SIM Swapping

## Overview

SIM swapping occurs when an attacker fraudulently transfers a victim's mobile number to another SIM.

Potential impact:

- Account takeover
- MFA bypass
- Identity theft

### Defensive Controls

- Enable carrier security features
- Use authentication applications where possible
- Monitor unexpected service interruptions
- Contact the carrier immediately if suspicious activity occurs

---

# Rooting and Jailbreaking (Conceptual)

## Rooting (Android)

Rooting removes manufacturer restrictions and grants elevated privileges.

## Jailbreaking (iOS)

Jailbreaking removes Apple's software restrictions.

### Security Risks

- Reduced platform security
- Increased malware exposure
- Unsupported configurations
- Higher risk of compromise

Organizations generally prohibit rooted or jailbroken devices from accessing enterprise resources.

---

# Data Leakage

## Overview

Sensitive information may be exposed through:

- Lost devices
- Misconfigured applications
- Cloud synchronization
- Weak authentication
- User error

### Defensive Controls

- Device encryption
- Strong authentication
- Remote wipe capability
- Data Loss Prevention (DLP)
- User awareness training

---

# Social Engineering

Attackers frequently target users instead of technology.

Examples include:

- Fake support messages
- QR code scams
- Fraudulent applications
- Smishing
- Voice phishing (Vishing)

### Defensive Controls

- Security awareness training
- Verify requests before responding
- Install software only from trusted sources
- Report suspicious communications

---

# Blue Team Detection Opportunities

Security teams should monitor for:

- Unusual application installations
- Unexpected permission changes
- Repeated authentication failures
- Rooted or jailbroken devices
- Unusual network connections
- Device compliance failures
- Malware alerts
- Abnormal battery or CPU usage
- Unexpected outbound traffic

---

# Mobile Security Recommendations

Organizations should:

- Deploy Mobile Device Management (MDM)
- Use Mobile Threat Defense (MTD)
- Require MFA
- Enforce device encryption
- Maintain software updates
- Monitor mobile endpoints continuously
- Restrict rooted or jailbroken devices
- Provide regular security awareness training

---

# CEH Exam Tips

Remember:

- Mobile malware targets smartphones and tablets.
- Smishing is phishing delivered through SMS.
- SIM swapping can bypass SMS-based MFA.
- Rooting and jailbreaking weaken built-in security controls.
- Public Wi-Fi increases the risk of data interception.
- MDM and MTD are important enterprise mobile security controls.
- User awareness is a critical defense against mobile attacks.

---

# Key Takeaways

- Mobile devices face a wide range of threats including malware, phishing, insecure wireless networks, SIM swapping, and social engineering.
- A defense-in-depth strategy—including MDM, MTD, MFA, encryption, regular updates, and user awareness—helps protect enterprise mobile environments.
- Continuous monitoring and strong security policies reduce the likelihood and impact of mobile security incidents.

---

# Mobile Security Defense

## Overview

Securing mobile devices requires more than antivirus software or device passwords. Organizations should adopt a **defense-in-depth** strategy by combining strong authentication, device management, encryption, continuous monitoring, user awareness, and regular security updates.

Enterprise mobile security protects both organizational data and user privacy while supporting secure business operations.

---

# Defense-in-Depth

Defense-in-depth applies multiple security controls across different layers to reduce the likelihood and impact of attacks.

Typical layers include:

- Device security
- Application security
- Identity and access management
- Network security
- Data protection
- Endpoint monitoring
- User awareness

---

# Mobile Device Management (MDM)

## Overview

Mobile Device Management (MDM) enables organizations to centrally manage, monitor, and secure mobile devices.

### Common Capabilities

- Device enrollment
- Policy enforcement
- Remote configuration
- Device inventory
- Remote lock
- Remote wipe
- Compliance monitoring

### Benefits

- Centralized management
- Improved security
- Better compliance
- Reduced operational risk

---

# Enterprise Mobility Management (EMM)

Enterprise Mobility Management expands MDM by managing devices, applications, content, and user identities.

Typical components include:

- Mobile Device Management (MDM)
- Mobile Application Management (MAM)
- Mobile Content Management (MCM)
- Identity and Access Management (IAM)

---

# Unified Endpoint Management (UEM)

Unified Endpoint Management extends enterprise management to multiple endpoint types.

Supported endpoints include:

- Smartphones
- Tablets
- Laptops
- Desktops
- IoT devices

### Benefits

- Unified administration
- Consistent security policies
- Improved visibility
- Simplified endpoint management

---

# Mobile Threat Defense (MTD)

Mobile Threat Defense solutions detect and respond to threats affecting mobile devices.

### Detection Capabilities

- Malware
- Phishing
- Network attacks
- Risky applications
- Device compromise
- Configuration weaknesses

---

# Bring Your Own Device (BYOD)

## Overview

BYOD allows employees to use personal devices for business purposes.

### Security Challenges

- Personal and corporate data coexist
- Device compliance
- Data leakage
- Privacy concerns
- Application management

### Security Controls

- MDM/UEM
- Device encryption
- MFA
- Conditional access
- Compliance policies

---

# Device Encryption

Encryption protects stored information if a device is lost or stolen.

Benefits include:

- Data confidentiality
- Reduced risk of unauthorized access
- Regulatory compliance
- Improved privacy

Organizations should require encryption on all managed mobile devices.

---

# Multi-Factor Authentication (MFA)

MFA strengthens authentication by requiring two or more verification factors.

Examples:

- Password
- Fingerprint
- Face recognition
- Authentication application
- Security key

Benefits:

- Reduces account compromise
- Protects enterprise services
- Strengthens identity verification

---

# Virtual Private Network (VPN)

A VPN encrypts network traffic between the mobile device and enterprise resources.

Benefits:

- Secure remote access
- Protection on public Wi-Fi
- Confidential communication
- Reduced interception risk

---

# Secure Application Deployment

Organizations should:

- Use trusted application stores
- Verify application publishers
- Review requested permissions
- Remove unused applications
- Apply application updates promptly

Enterprise environments may use managed application deployment through MDM/UEM solutions.

---

# Patch and Update Management

Regular updates help protect mobile devices against newly discovered vulnerabilities.

Organizations should update:

- Mobile operating systems
- Business applications
- Security software
- Device firmware

Benefits include:

- Vulnerability remediation
- Improved stability
- Enhanced security

---

# Logging and SIEM Integration

Enterprise mobile environments should forward relevant security events to a SIEM platform.

Common log sources include:

- MDM/UEM
- Identity providers
- Authentication services
- VPN gateways
- Mobile Threat Defense solutions
- Enterprise applications

### Benefits

- Centralized monitoring
- Event correlation
- Faster incident detection
- Compliance reporting

---

# Zero Trust for Mobile Devices

Zero Trust assumes that no device or user is trusted automatically.

Key principles include:

- Verify identity continuously
- Validate device compliance
- Apply least privilege
- Monitor access continuously
- Restrict unnecessary permissions

---

# Incident Response

If suspicious mobile activity is detected:

1. Identify the affected device.
2. Preserve logs and evidence.
3. Isolate the device if necessary.
4. Investigate the root cause.
5. Remove malicious applications.
6. Reset credentials if required.
7. Restore the device securely.
8. Document lessons learned.

---

# User Awareness

Users should be trained to:

- Install apps only from trusted sources.
- Review application permissions.
- Avoid suspicious links and QR codes.
- Use secure authentication methods.
- Keep devices updated.
- Report lost or stolen devices immediately.

---

# Enterprise Mobile Security Checklist

Organizations should ensure:

- Device encryption is enabled.
- MFA is enforced.
- MDM/UEM is deployed.
- Mobile Threat Defense is active.
- Devices receive regular updates.
- Rooted or jailbroken devices are blocked.
- VPN is required for remote access.
- Security logs are integrated with the SIEM.
- Mobile security policies are documented.

---

# CEH Exam Tips

Remember:

- MDM centrally manages mobile devices.
- EMM expands management to applications, content, and identities.
- UEM manages all enterprise endpoints.
- MTD detects threats affecting mobile devices.
- MFA strengthens authentication.
- VPN secures communication over untrusted networks.
- Zero Trust continuously verifies users and devices.
- Device encryption protects data at rest.

---

# Key Takeaways

- Enterprise mobile security relies on layered defenses rather than a single security control.
- MDM, UEM, MTD, MFA, encryption, VPNs, SIEM integration, and user awareness are essential components of a secure mobile environment.
- Continuous monitoring, timely updates, and strong security policies significantly reduce the risk of mobile compromise.

---

# MITRE ATT&CK Mapping, Blue Team Perspective & Module Summary

## Overview

Mobile devices are frequent targets because they provide access to corporate resources, cloud services, authentication mechanisms, and sensitive personal information.

The MITRE ATT&CK Framework helps defenders understand attacker behaviors, improve detection capabilities, and strengthen incident response.

Although Android, iOS, MDM, and MFA are security technologies rather than ATT&CK techniques, many mobile attack scenarios align with ATT&CK tactics.

---

# MITRE ATT&CK Tactics Related to Mobile Security

| ATT&CK Tactic | Relevance |
|--------------|-----------|
| Initial Access | Unauthorized access through malicious applications, phishing, or compromised devices |
| Execution | Running malicious applications or unauthorized code |
| Persistence | Maintaining unauthorized access after device compromise |
| Privilege Escalation | Gaining elevated permissions on a compromised device |
| Defense Evasion | Avoiding detection by security controls |
| Credential Access | Stealing authentication credentials or tokens |
| Discovery | Enumerating device information and applications |
| Collection | Gathering sensitive user or enterprise data |
| Command and Control | Communicating with attacker-controlled infrastructure |
| Exfiltration | Transferring sensitive information outside the organization |
| Impact | Disrupting device functionality or enterprise operations |

---

# Relevant ATT&CK Techniques

| Technique | ATT&CK ID | Example Relevance |
|-----------|-----------|------------------|
| Phishing | T1566 | Delivering malicious links or applications through messages or email |
| Valid Accounts | T1078 | Use of compromised enterprise or cloud credentials |
| Data from Local System | T1005 | Accessing sensitive information stored on the device |
| System Information Discovery | T1082 | Collecting information about the mobile device |
| Application Layer Protocol | T1071 | Using legitimate network protocols for communication |
| Exfiltration Over Web Service | T1567 | Transmitting stolen data through cloud or web services |

> **Note:** MITRE ATT&CK focuses on attacker behavior. Android, iOS, MDM, UEM, and MTD are security technologies, not ATT&CK techniques.

---

# Blue Team Detection Opportunities

Security teams should monitor for:

- Unusual application installations
- Unexpected permission changes
- Repeated authentication failures
- Rooted or jailbroken devices
- Device compliance failures
- Malware detections
- Abnormal network activity
- Suspicious VPN usage
- Unusual cloud access
- Unexpected device enrollment

---

# SIEM Use Cases

SIEM platforms can generate alerts for:

- Failed authentication attempts
- Device compliance violations
- MDM policy changes
- Malware detections
- VPN anomalies
- New device enrollment
- Unusual application activity
- Privileged account usage
- Device encryption status changes

Common SIEM platforms include:

- Splunk
- Microsoft Sentinel
- IBM QRadar
- Elastic Security
- Wazuh

---

# Mobile Threat Hunting

Threat hunters should investigate:

- Unknown applications
- Unexpected device registrations
- Excessive authentication failures
- Rooted or jailbroken devices
- Abnormal outbound connections
- Suspicious cloud activity
- Device compliance drift
- Unusual application permissions
- Mobile malware alerts

---

# Security Monitoring Checklist

Regularly review:

- MDM/UEM dashboards
- Device compliance reports
- Authentication logs
- VPN logs
- Malware detections
- Application inventories
- Encryption status
- Device update status
- SIEM dashboards

---

# CEH Revision Notes

Remember:

- Android is Linux-based.
- iOS uses Secure Boot and Secure Enclave.
- MDM centrally manages mobile devices.
- EMM manages devices, applications, and content.
- UEM manages multiple endpoint types.
- MTD detects threats affecting mobile devices.
- MFA strengthens authentication.
- VPN protects communication over untrusted networks.
- Rooted or jailbroken devices increase security risk.
- User awareness remains an important defense.

---

# Interview Tips

Be prepared to explain:

- Android architecture
- iOS security architecture
- MDM vs EMM vs UEM
- Mobile Threat Defense (MTD)
- BYOD security
- Mobile malware
- Smishing
- SIM swapping
- Rooting vs Jailbreaking
- Mobile encryption
- VPN usage
- Zero Trust for mobile devices
- SIEM integration
- Enterprise mobile security

---

# Key Takeaways

- Mobile devices are high-value targets because they store sensitive information and provide access to enterprise resources.
- Strong authentication, encryption, MDM/UEM, Mobile Threat Defense, continuous monitoring, and user awareness significantly improve mobile security.
- Organizations should integrate mobile security with SIEM platforms and apply Zero Trust principles to strengthen enterprise defenses.

---

# Module Summary

Module 17 introduced mobile platform fundamentals, Android and iOS security architectures, mobile threats, enterprise mobile security controls, defensive monitoring, MITRE ATT&CK mapping, and Blue Team detection strategies.

These concepts provide a strong foundation for CEH certification, enterprise mobile security, SOC operations, and security consulting.
