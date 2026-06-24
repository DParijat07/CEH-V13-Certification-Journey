# Class 08 - Man-in-the-Middle (MITM) Attack & WiFi Hacking Basics

**Date:** 24/06/2026
**Training:** IEMLabs CEH Training

---

## Overview

This session introduced the concept of **Man-in-the-Middle (MITM) attacks**, where an attacker intercepts communication between two parties. An introductory overview of the **Ettercap** tool was provided, focusing on its role in network sniffing and traffic interception. The practical learning component included studying the **WiFi Hacking 101** room on TryHackMe to understand wireless networking fundamentals and WiFi security concepts.

---

# Man-in-the-Middle (MITM) Attack

## Definition

A Man-in-the-Middle attack occurs when an attacker secretly positions themselves between two communicating systems to intercept, monitor, or manipulate traffic.

### Communication Flow

```text
Victim ↔ Attacker ↔ Server
```

---

## Objectives of MITM Attacks

* Intercept network traffic
* Capture credentials
* Monitor user activity
* Manipulate transmitted data
* Redirect users to malicious destinations

---

## Common MITM Techniques

### ARP Spoofing

* Exploits the Address Resolution Protocol (ARP).
* Sends forged ARP messages on a local network.
* Associates the attacker's MAC address with legitimate IP addresses.
* Causes traffic to pass through the attacker's system.

### DNS Spoofing

* Manipulates DNS responses.
* Redirects victims to fraudulent websites.
* Often used for phishing attacks.

### SSL Stripping

* Downgrades encrypted HTTPS connections to HTTP.
* Allows attackers to inspect unencrypted traffic.

---

## Risks Associated with MITM Attacks

* Credential theft
* Session hijacking
* Data manipulation
* Privacy violations
* Financial fraud

---

## Mitigation Strategies

### User Side

* Use HTTPS websites.
* Verify SSL certificates.
* Avoid sensitive activities on public WiFi.
* Use VPN services.

### Organizational Side

* Network segmentation
* IDS/IPS deployment
* Secure DNS configurations
* Strong authentication controls

---

# Introduction to Ettercap

## What is Ettercap?

Ettercap is a network security tool commonly used for:

* Network sniffing
* ARP poisoning
* MITM demonstrations
* Protocol analysis

---

## Key Features

### Host Discovery

Identifies active hosts on a network.

### ARP Poisoning

Performs ARP spoofing to intercept traffic.

### Packet Sniffing

Captures and analyzes network packets.

### Traffic Monitoring

Observes communication between network devices.

---

## General Workflow

```text
Host Discovery
      ↓
Target Selection
      ↓
ARP Poisoning
      ↓
Traffic Interception
      ↓
Packet Analysis
```

---

# TryHackMe - WiFi Hacking 101

## Objective

Learn the fundamentals of wireless networking and WiFi security.

---

## Wireless Networking Concepts

### Access Point (AP)

A device that provides wireless connectivity to clients.

### Client

Any device connected to a wireless network.

### SSID

Service Set Identifier (WiFi network name).

Examples:

```text
Home_WiFi
Office_Network
```

### BSSID

The MAC address of the wireless access point.

### Channel

The radio frequency channel used for wireless communication.

---

## WiFi Authentication Types

### Open Network

* No authentication required.
* Least secure.

### WPA/WPA2 Personal

* Uses a Pre-Shared Key (PSK).
* Commonly used in home networks.

### WPA3

* Improved authentication mechanisms.
* Enhanced wireless security.

---

## WPA Handshake

The authentication process between a client and an access point.

```text
Client ↔ Access Point
```

Used to establish secure communication.

---

# Key Takeaways

* Learned the fundamentals of Man-in-the-Middle attacks.
* Understood how ARP spoofing enables traffic interception.
* Received an introduction to the Ettercap tool.
* Studied wireless networking fundamentals.
* Learned important WiFi security concepts.
* Explored authentication methods such as WPA, WPA2, and WPA3.
* Completed the TryHackMe WiFi Hacking 101 learning room.

---

# Skills Gained

* Understanding of MITM attack concepts
* Knowledge of ARP spoofing fundamentals
* Basic familiarity with Ettercap
* Wireless networking awareness
* WiFi security fundamentals
* Network attack and defense concepts

---

## References

* CEHv13 Module: Sniffing
* CEHv13 Module: Wireless Network Security
* TryHackMe: WiFi Hacking 101
* IEMLabs CEH Training - Class 08
