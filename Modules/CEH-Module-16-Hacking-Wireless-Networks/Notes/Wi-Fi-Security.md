# Wi-Fi Security

## Overview

Wi-Fi security protects wireless networks from unauthorized access, data interception, and other wireless threats. Modern Wi-Fi security relies on **authentication, authorization, encryption, and access control** to ensure the confidentiality, integrity, and availability of wireless communications.

Organizations should adopt current security standards and retire legacy protocols to minimize risk.

---

# Authentication vs Authorization

## Authentication

Authentication verifies the identity of a user or device before granting network access.

Examples include:

- Passwords
- Digital certificates
- Enterprise credentials

---

## Authorization

Authorization determines the level of access an authenticated user or device receives.

Examples:

- Guest Wi-Fi
- Employee network
- Administrator network

---

# Open Authentication

Open Authentication allows devices to connect without identity verification.

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

WPA was introduced to improve security over the deprecated WEP protocol.

Features:

- Improved authentication
- Dynamic key generation
- Better encryption than WEP

Although more secure than WEP, WPA has largely been replaced by WPA2 and WPA3.

---

# WPA2

WPA2 became the industry standard for many years.

Features:

- AES encryption
- CCMP protocol
- Strong authentication
- Improved confidentiality and integrity

WPA2 is still widely used but should be upgraded to WPA3 whenever possible.

---

# WPA3

WPA3 is the latest Wi-Fi security standard.

Advantages include:

- Stronger authentication
- Enhanced encryption
- Better protection against password guessing
- Improved security for public Wi-Fi
- Forward secrecy
- Increased resilience against modern attacks

WPA3 is recommended for all new wireless deployments.

---

# Personal vs Enterprise Security

## WPA Personal (WPA-PSK)

Characteristics:

- Shared password
- Easy deployment
- Suitable for homes and small offices

Advantages:

- Simple configuration
- Low administrative overhead

Limitations:

- Shared credentials
- Password reuse risks
- Limited user accountability

---

## WPA Enterprise

Characteristics:

- Individual user authentication
- IEEE 802.1X support
- Centralized authentication

Advantages:

- Better auditing
- Improved user management
- Higher security
- Scalable for organizations

Common environments:

- Enterprises
- Universities
- Government agencies
- Hospitals

---

# IEEE 802.1X

IEEE 802.1X is a network access control standard used in enterprise wireless networks.

Benefits:

- User authentication
- Device authentication
- Centralized access control
- Strong identity verification

---

# RADIUS

A **Remote Authentication Dial-In User Service (RADIUS)** server provides:

- Authentication
- Authorization
- Accounting (AAA)

Advantages:

- Centralized user management
- Detailed logging
- Policy enforcement
- Improved accountability

---

# Wireless Encryption

Encryption protects wireless data while it travels through the air.

Modern Wi-Fi primarily relies on **AES-based encryption**.

---

# WEP (Wired Equivalent Privacy)

Characteristics:

- Legacy protocol
- Weak encryption
- Deprecated

WEP should never be used in production environments.

---

# TKIP (Temporal Key Integrity Protocol)

Characteristics:

- Transitional technology
- More secure than WEP
- Deprecated

TKIP should be replaced with modern encryption methods.

---

# AES (Advanced Encryption Standard)

AES is the recommended encryption algorithm for modern wireless networks.

Benefits:

- Strong encryption
- High performance
- Industry standard
- Widely supported

---

# CCMP (Counter Mode with CBC-MAC Protocol)

CCMP is the encryption protocol used with AES in WPA2.

Provides:

- Confidentiality
- Integrity
- Authentication
- Replay protection

---

# GCMP (Galois/Counter Mode Protocol)

GCMP is commonly used with WPA3.

Advantages:

- High performance
- Improved efficiency
- Strong security

---

# Protected Management Frames (PMF)

Protected Management Frames (PMF) secure Wi-Fi management traffic.

Benefits:

- Protects management frames
- Reduces spoofing risks
- Improves network resilience

PMF is mandatory for WPA3-certified devices.

---

# Strong Password Policy

Wireless networks should use:

- Long passphrases
- Complex passwords
- Unique credentials
- Regular password updates
- Multi-factor authentication where appropriate

---

# Enterprise Security Best Practices

Organizations should:

- Deploy WPA3 whenever possible
- Implement IEEE 802.1X
- Use RADIUS authentication
- Disable WEP and TKIP
- Enable Protected Management Frames
- Keep firmware updated
- Monitor authentication logs
- Perform regular security assessments

---

# CEH Exam Tips

Remember:

- WEP is insecure and deprecated.
- TKIP is a legacy protocol.
- AES is the recommended encryption algorithm.
- CCMP is associated with WPA2.
- GCMP is commonly associated with WPA3.
- WPA3 provides stronger protection than WPA2.
- IEEE 802.1X is used for enterprise authentication.
- RADIUS provides Authentication, Authorization, and Accounting (AAA).
- Protected Management Frames (PMF) help secure Wi-Fi management traffic.

---

# Key Takeaways

- Modern Wi-Fi security combines strong authentication, robust encryption, and centralized access control.
- WPA3, AES, IEEE 802.1X, and RADIUS represent current best practices for enterprise wireless security.
- Legacy technologies such as WEP and TKIP should be avoided due to well-known security weaknesses.
