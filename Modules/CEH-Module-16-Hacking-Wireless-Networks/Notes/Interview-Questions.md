# Interview Questions – Hacking Wireless Networks

## Overview

This document contains commonly asked interview questions related to wireless networking and Wi-Fi security. The questions progress from fundamental concepts to enterprise security, defensive practices, and scenario-based discussions.

---

# Basic Questions (1–20)

### 1. What is a Wireless Local Area Network (WLAN)?

A WLAN is a network that connects devices using radio frequency (RF) signals instead of physical cables.

---

### 2. What is Wi-Fi?

Wi-Fi is a wireless networking technology based on the IEEE 802.11 family of standards.

---

### 3. What is IEEE 802.11?

It is the standard that defines wireless LAN communication, including the Physical (PHY) and MAC layers.

---

### 4. What is an SSID?

SSID (Service Set Identifier) is the name of a wireless network.

---

### 5. What is a BSSID?

BSSID (Basic Service Set Identifier) uniquely identifies an Access Point and is usually its MAC address.

---

### 6. What is the difference between SSID and BSSID?

- **SSID:** Network name
- **BSSID:** Unique identifier of an Access Point

---

### 7. What is an Access Point (AP)?

A device that provides wireless connectivity between clients and a wired network.

---

### 8. What is Infrastructure Mode?

A wireless network where devices communicate through an Access Point.

---

### 9. What is Ad Hoc Mode?

A peer-to-peer wireless network where devices communicate directly without an Access Point.

---

### 10. What are the common Wi-Fi frequency bands?

- 2.4 GHz
- 5 GHz
- 6 GHz

---

### 11. What are the advantages of 2.4 GHz?

- Longer range
- Better wall penetration

---

### 12. What are the advantages of 5 GHz?

- Higher throughput
- Less interference
- More available channels

---

### 13. What is Wi-Fi 6?

Wi-Fi 6 is based on IEEE 802.11ax and improves performance, efficiency, and capacity.

---

### 14. What is Wi-Fi 7?

Wi-Fi 7 is based on IEEE 802.11be and provides Extremely High Throughput (EHT) with lower latency.

---

### 15. What is authentication?

Authentication verifies the identity of a user or device before granting access.

---

### 16. What is authorization?

Authorization determines what resources an authenticated user or device may access.

---

### 17. What is WPA2?

A wireless security standard that uses AES encryption and CCMP.

---

### 18. What is WPA3?

The latest Wi-Fi security standard with stronger authentication and enhanced protection against modern attacks.

---

### 19. Why should WEP not be used?

WEP is deprecated because it uses weak encryption and has known security vulnerabilities.

---

### 20. What is AES?

AES (Advanced Encryption Standard) is the recommended encryption algorithm for modern wireless networks.

---

# Intermediate Questions (21–45)

21. What is the difference between WPA2 and WPA3?
22. What is IEEE 802.1X?
23. What is a RADIUS server?
24. What is Authentication, Authorization, and Accounting (AAA)?
25. What is WPA Personal?
26. What is WPA Enterprise?
27. What is CCMP?
28. What is GCMP?
29. What are Protected Management Frames (PMF)?
30. What is a Rogue Access Point?
31. What is an Evil Twin network?
32. What is packet sniffing?
33. What is MAC address spoofing?
34. What is a replay attack?
35. What is wireless Denial of Service (DoS)?
36. What is RF jamming?
37. What is Wireless IDS (WIDS)?
38. What is Wireless IPS (WIPS)?
39. What is Network Access Control (NAC)?
40. Why is network segmentation important?
41. Why should firmware be updated regularly?
42. How does WPA3 improve wireless security?
43. What logs should be monitored in a wireless network?
44. How does a SIEM improve wireless security?
45. What are the key components of a secure enterprise Wi-Fi deployment?

---

# Advanced Questions (46–60)

46. Explain a defense-in-depth strategy for wireless security.
47. How would you detect a Rogue Access Point?
48. How would you secure a corporate wireless network?
49. How would you protect users on public Wi-Fi?
50. Why is Zero Trust important for wireless networks?
51. How would you monitor wireless authentication activity?
52. What indicators might suggest suspicious wireless behavior?
53. How does IEEE 802.1X improve enterprise security?
54. Why should organizations retire WEP and TKIP?
55. How would you investigate repeated authentication failures?
56. How can network segmentation reduce business risk?
57. What role does RADIUS play in enterprise Wi-Fi?
58. Why are Protected Management Frames important?
59. How would you improve wireless security for remote offices?
60. What wireless security controls would you recommend for an enterprise?

---

# Scenario-Based Questions (61–75)

61. Employees report frequent wireless disconnections. How would you investigate?
62. A new SSID appears inside the office. What should you do?
63. Multiple users cannot authenticate to enterprise Wi-Fi. Where would you begin troubleshooting?
64. SIEM reports repeated authentication failures. What are your next steps?
65. A wireless controller firmware vulnerability is announced. How should the organization respond?
66. Users complain about poor wireless performance. What factors would you examine?
67. A suspected Rogue AP is detected. How would you handle the incident?
68. Guest users require Internet access while protecting internal systems. How would you design the network?
69. A company plans to migrate from WPA2 to WPA3. What considerations are important?
70. RF interference is affecting wireless communication. How would you identify and mitigate the issue?
71. How would you respond to a suspected wireless security incident?
72. What wireless events would you forward to a SIEM platform?
73. How would you implement Zero Trust principles for Wi-Fi?
74. How would you educate employees about wireless security?
75. What wireless security improvements would you recommend during an annual security assessment?

---

# Quick Revision

Remember:

- IEEE 802.11 defines Wi-Fi standards.
- WPA3 is the preferred security standard.
- WPA2 remains common but should be upgraded.
- WEP and TKIP are deprecated.
- IEEE 802.1X supports enterprise authentication.
- RADIUS provides Authentication, Authorization, and Accounting (AAA).
- WIDS detects suspicious wireless activity.
- WIPS helps prevent or contain wireless threats.
- NAC controls device and user access.
- SIEM centralizes wireless security monitoring.
- Network segmentation limits lateral movement.
- User awareness is an important layer of defense.

---

# Interview Tips

- Explain concepts clearly before discussing implementation.
- Emphasize modern best practices such as WPA3, IEEE 802.1X, NAC, and Zero Trust.
- Highlight the importance of continuous monitoring, SIEM integration, and defense-in-depth.
- Focus on prevention, detection, and response rather than offensive techniques.
- Use practical examples from labs, home labs, or enterprise environments where appropriate.
