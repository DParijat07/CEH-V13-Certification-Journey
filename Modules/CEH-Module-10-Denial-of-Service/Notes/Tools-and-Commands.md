# Tools-and-Commands.md

# CEH v13 – Module 10

# DoS & DDoS Detection Tools and Useful Commands

---

# Overview

This document lists common tools used by cybersecurity professionals to **monitor, detect, analyze, and investigate** Denial of Service (DoS) and Distributed Denial of Service (DDoS) attacks.

> **Note:** These tools are intended for defensive security, network monitoring, and incident response.

---

# 1. Wireshark

## Purpose

Network packet analyzer used to capture and inspect network traffic.

## Common Uses

* Detect SYN Flood attacks
* Analyze ICMP Floods
* Inspect UDP traffic
* Identify abnormal packet patterns
* Investigate suspicious connections

## Useful Display Filters

### TCP Traffic

```text
tcp
```

### UDP Traffic

```text
udp
```

### ICMP Traffic

```text
icmp
```

### HTTP Traffic

```text
http
```

### TCP SYN Packets

```text
tcp.flags.syn == 1 && tcp.flags.ack == 0
```

### DNS Traffic

```text
dns
```

---

# 2. tcpdump

## Purpose

Command-line packet capture utility.

## Capture All Packets

```bash
sudo tcpdump
```

## Capture on Interface

```bash
sudo tcpdump -i eth0
```

## Capture TCP Traffic

```bash
sudo tcpdump tcp
```

## Capture UDP Traffic

```bash
sudo tcpdump udp
```

## Capture ICMP

```bash
sudo tcpdump icmp
```

## Save Capture

```bash
sudo tcpdump -w capture.pcap
```

---

# 3. Netstat

## Purpose

Display active network connections.

## Show Listening Ports

```bash
netstat -tuln
```

## Show Active Connections

```bash
netstat -an
```

## Display Statistics

```bash
netstat -s
```

---

# 4. ss

## Purpose

Modern replacement for Netstat.

## Show TCP Connections

```bash
ss -t
```

## Show UDP Connections

```bash
ss -u
```

## Show Listening Services

```bash
ss -l
```

## Show All Connections

```bash
ss -a
```

---

# 5. Ping

## Purpose

Test network connectivity using ICMP.

## Basic Usage

```bash
ping google.com
```

## Send Limited Packets

```bash
ping -c 4 google.com
```

---

# 6. traceroute

## Purpose

Trace packet path between source and destination.

## Linux

```bash
traceroute google.com
```

## Windows

```cmd
tracert google.com
```

---

# 7. Nmap

## Purpose

Network discovery and service enumeration.

## Host Discovery

```bash
nmap -sn 192.168.1.0/24
```

## Service Detection

```bash
nmap -sV target_ip
```

## TCP SYN Scan

```bash
nmap -sS target_ip
```

## OS Detection

```bash
nmap -O target_ip
```

---

# 8. htop / top

## Purpose

Monitor system resources during an attack.

Monitor:

* CPU Usage
* Memory Usage
* Running Processes
* Load Average

## Commands

```bash
top
```

```bash
htop
```

---

# 9. Journalctl

## Purpose

View Linux system logs.

## Recent Logs

```bash
journalctl
```

## Follow Logs

```bash
journalctl -f
```

---

# 10. dmesg

## Purpose

Display kernel messages.

Useful for investigating:

* Network driver issues
* Kernel warnings
* Hardware events

```bash
dmesg
```

---

# 11. Firewall Commands

## UFW

Check Status

```bash
sudo ufw status
```

Enable Firewall

```bash
sudo ufw enable
```

---

## iptables

View Rules

```bash
sudo iptables -L
```

---

# 12. Windows Commands

## View Network Connections

```cmd
netstat -ano
```

## Ping

```cmd
ping google.com
```

## Trace Route

```cmd
tracert google.com
```

## Display Network Configuration

```cmd
ipconfig
```

---

# Common Indicators During a DoS Attack

* Large number of SYN packets
* Thousands of identical requests
* High bandwidth usage
* Numerous half-open TCP connections
* Excessive ICMP traffic
* High CPU utilization
* Slow response time

---

# Defensive Monitoring Tools

| Tool             | Purpose                     |
| ---------------- | --------------------------- |
| Wireshark        | Packet Analysis             |
| tcpdump          | Packet Capture              |
| Zeek             | Network Monitoring          |
| Snort            | IDS                         |
| Suricata         | IDS/IPS                     |
| NetFlow Analyzer | Traffic Analysis            |
| Security Onion   | Network Security Monitoring |
| SIEM             | Log Correlation             |
| Grafana          | Dashboard & Monitoring      |
| Prometheus       | Metrics Collection          |

---

# Commands to Remember for CEH

| Command                  | Purpose                     |
| ------------------------ | --------------------------- |
| `ping`                   | Connectivity Test           |
| `traceroute` / `tracert` | Path Discovery              |
| `tcpdump`                | Packet Capture              |
| `netstat`                | Network Connections         |
| `ss`                     | Active Sockets              |
| `top`                    | CPU Monitoring              |
| `htop`                   | Resource Monitoring         |
| `ipconfig`               | Windows Network Info        |
| `ifconfig` / `ip a`      | Linux Network Configuration |
| `nmap -sV`               | Service Detection           |

---

# Key Takeaways

* **Wireshark** is the preferred GUI tool for packet analysis.
* **tcpdump** is ideal for command-line packet captures.
* **Netstat** and **ss** help identify active and suspicious network connections.
* **Nmap** supports reconnaissance and service enumeration.
* Continuous monitoring of CPU, memory, bandwidth, and connection counts is essential for detecting potential DoS attacks.
* Combining packet analysis, system monitoring, and log analysis provides better visibility into attack activity.
