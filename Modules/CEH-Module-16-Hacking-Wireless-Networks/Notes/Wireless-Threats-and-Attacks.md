# Wireless Threats and Attacks

## Overview

Wireless networks provide flexibility and mobility but also introduce security risks because communication occurs over radio frequencies. Since wireless signals extend beyond physical boundaries, organizations must implement strong security controls to protect against unauthorized access, interception, and service disruption.

This document provides a defensive overview of common wireless threats, their potential impact, and recommended security controls.

---

# Common Wireless Threats

Organizations may encounter threats such as:

- Unauthorized wireless access
- Rogue wireless devices
- Credential theft
- Traffic interception
- Device impersonation
- Network disruption
- Social engineering
- Weak security configurations

---

# Rogue Access Point (Rogue AP)

## Overview

A Rogue Access Point is an unauthorized wireless access point connected to an organization's network.

It may be installed intentionally or unintentionally without approval from the IT or security team.

### Risks

- Unauthorized network access
- Policy violations
- Data exposure
- Bypass of security controls

### Defensive Controls

- Wireless IDS/IPS (WIDS/WIPS)
- Network Access Control (NAC)
- Wireless site surveys
- Asset inventory management
- Continuous monitoring

---

# Evil Twin Network

## Overview

An Evil Twin is a fraudulent wireless network that imitates a legitimate Wi-Fi network to deceive users into connecting.

### Potential Impact

- Credential theft
- Traffic interception
- User deception
- Session compromise

### Defensive Controls

- WPA3 Enterprise
- Certificate validation
- Disable automatic Wi-Fi connections
- User awareness training
- Wireless monitoring

---

# Packet Sniffing

## Overview

Packet sniffing is the process of capturing and analyzing network traffic.

Authorized packet analysis is commonly used for:

- Network troubleshooting
- Performance monitoring
- Incident response
- Security investigations

If wireless traffic is not properly encrypted, attackers may attempt to observe sensitive information.

### Defensive Controls

- WPA3 encryption
- HTTPS
- VPN usage
- Secure application protocols
- Strong authentication

---

# MAC Address Spoofing

## Overview

Each network interface has a unique MAC (Media Access Control) address.

An attacker may attempt to impersonate another device by presenting a different MAC address.

### Risks

- Device impersonation
- Weak MAC filter bypass
- Unauthorized access attempts

### Defensive Controls

- IEEE 802.1X authentication
- Network Access Control (NAC)
- Device certificates
- Continuous monitoring

---

# Replay Attacks

## Overview

Replay attacks involve retransmitting previously captured communications in an attempt to achieve an unauthorized outcome.

### Potential Impact

- Unauthorized actions
- Session misuse
- Authentication abuse

### Defensive Controls

- WPA3
- Session validation
- Nonce-based protocols
- Timestamp verification
- Modern encryption protocols

---

# Deauthentication Attacks (Conceptual)

## Overview

Wireless networks exchange management frames to maintain communication between clients and access points.

If these management frames are not protected, attackers may attempt to force clients to disconnect.

### Potential Impact

- Temporary service interruption
- User inconvenience
- Increased social engineering opportunities

### Defensive Controls

- Protected Management Frames (PMF)
- WPA3
- Wireless IDS/IPS
- Continuous monitoring

---

# Wireless Denial of Service (DoS)

## Overview

Wireless DoS attacks attempt to reduce or interrupt the availability of wireless communication.

### Potential Impact

- Network instability
- Slow performance
- Client disconnections
- Business disruption

### Defensive Controls

- RF monitoring
- Redundant Access Points
- WIDS/WIPS
- Proper channel planning

---

# Radio Frequency (RF) Jamming

## Overview

RF jamming occurs when radio interference disrupts legitimate wireless communication.

### Potential Impact

- Signal degradation
- Communication failures
- Reduced network availability

### Defensive Controls

- RF spectrum analysis
- Wireless monitoring
- Channel optimization
- Physical security

---

# Weak Wireless Passwords

Weak passwords significantly reduce wireless security.

Examples of poor practices include:

- Default passwords
- Short passwords
- Dictionary words
- Password reuse
- Shared credentials

### Best Practices

- Long passphrases
- Complex passwords
- Unique credentials
- Password management policies
- Multi-factor authentication where applicable

---

# Social Engineering Against Wi-Fi Users

Attackers may target users instead of technology.

Examples include:

- Fake captive portals
- Fraudulent hotspot names
- Phishing pages
- Fake technical support requests

### Defensive Controls

- Security awareness training
- Verify SSIDs before connecting
- Use VPNs on public Wi-Fi
- Validate certificates
- Report suspicious wireless networks

---

# Blue Team Detection Opportunities

Security teams should monitor for:

- Unknown Access Points
- Unauthorized SSIDs
- Authentication failures
- Unexpected client disconnections
- New wireless devices
- Excessive management frames
- RF interference
- Configuration changes
- Abnormal wireless traffic

---

# Security Recommendations

Organizations should:

- Deploy WPA3
- Enable Protected Management Frames
- Use IEEE 802.1X authentication
- Implement Network Access Control
- Monitor wireless infrastructure continuously
- Conduct regular wireless security assessments
- Train users to recognize suspicious Wi-Fi networks
- Keep wireless firmware updated

---

# CEH Exam Tips

Remember:

- Rogue APs are unauthorized access points.
- Evil Twin networks imitate legitimate Wi-Fi networks.
- Packet sniffing may be legitimate for monitoring or malicious if unauthorized.
- MAC filtering alone is not a sufficient security control.
- Protected Management Frames (PMF) improve management frame security.
- WPA3 provides stronger protection than previous Wi-Fi standards.
- User awareness is an essential layer of wireless security.

---

# Key Takeaways

- Wireless networks are exposed to unique threats because communication occurs over radio frequencies.
- Common risks include Rogue APs, Evil Twin networks, packet sniffing, MAC spoofing, replay attacks, wireless DoS, RF jamming, weak passwords, and social engineering.
- Organizations should adopt a defense-in-depth strategy that combines WPA3, IEEE 802.1X, PMF, WIDS/WIPS, continuous monitoring, and user awareness to protect wireless environments.
