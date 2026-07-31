# Module 04 – Enumeration

---

# Overview

Enumeration is the process of actively extracting detailed information from a target system, network, or service after the target has been discovered during scanning.

Reconnaissance collects general information about a target, scanning identifies hosts and open ports, and enumeration goes deeper into the services running on those ports.

Enumeration can reveal:

- Usernames
- Groups
- Network shares
- Hostnames
- Domain information
- Operating system information
- Service versions
- DNS records
- Network resources
- Security policies
- System configurations

Enumeration is therefore an important phase between network scanning and vulnerability analysis.

---

# What is Enumeration?

## Definition

Enumeration is the process of actively gathering detailed information from a target system by interacting with its available network services, protocols, and applications.

The goal is to obtain information that can help an ethical hacker understand the target environment and identify potential security weaknesses.

---

# Objectives of Enumeration

The primary objectives are to:

- Identify users
- Identify groups
- Discover network shares
- Identify domain information
- Discover hostnames
- Identify operating systems
- Identify running services
- Identify service versions
- Discover network resources
- Identify security configurations
- Support vulnerability assessment

---

# Reconnaissance vs Scanning vs Enumeration

| Phase | Main Objective | Examples |
|---|---|---|
| Reconnaissance | Collect general target information | Domains, organizations, public information |
| Scanning | Identify hosts, ports, and services | Nmap host and port scanning |
| Enumeration | Extract detailed service information | Users, shares, DNS, SNMP, LDAP |
| Vulnerability Analysis | Identify and assess weaknesses | Nessus, OpenVAS, Nmap NSE |

---

# Enumeration Process

A typical enumeration process can be represented as:

    Reconnaissance
          ↓
    Network Scanning
          ↓
    Open Ports Identified
          ↓
    Services Identified
          ↓
    Service Enumeration
          ↓
    Information Analysis
          ↓
    Vulnerability Assessment

---

# Types of Enumeration

Common enumeration activities include:

- NetBIOS enumeration
- SMB enumeration
- SNMP enumeration
- LDAP enumeration
- Active Directory enumeration
- DNS enumeration
- SMTP enumeration
- FTP enumeration
- NFS enumeration
- RPC enumeration
- Linux enumeration
- Windows enumeration

---

# Service-Based Enumeration

Enumeration is usually performed according to the services discovered during scanning.

Example:

    Port 21
       ↓
    FTP
       ↓
    FTP Enumeration

    Port 53
       ↓
    DNS
       ↓
    DNS Enumeration

    Port 161
       ↓
    SNMP
       ↓
    SNMP Enumeration

    Port 445
       ↓
    SMB
       ↓
    SMB Enumeration

This approach makes enumeration more targeted and efficient.

---

# NetBIOS Enumeration

## Definition

NetBIOS stands for Network Basic Input/Output System.

It is a legacy networking technology commonly associated with Windows systems and network resource sharing.

NetBIOS enumeration can provide information about Windows hosts and network resources.

---

# NetBIOS Information

Enumeration may reveal:

- Computer names
- Workgroup names
- Domain names
- Logged-in users
- Network shares
- MAC addresses
- Network services

---

# NetBIOS Ports

Common NetBIOS-related ports are:

| Port | Protocol | Purpose |
|---|---|---|
| 137 | UDP | NetBIOS Name Service |
| 138 | UDP | NetBIOS Datagram Service |
| 139 | TCP | NetBIOS Session Service |

---

# NetBIOS Enumeration with Nmap

Nmap NSE scripts can be used to gather NetBIOS information.

Example:

    nmap -sU -p 137 --script nbstat <target>

The result may provide information such as:

- NetBIOS names
- Computer name
- Workgroup
- MAC address

---

# SMB Enumeration

## Definition

Server Message Block (SMB) is a network protocol used primarily in Windows environments for:

- File sharing
- Printer sharing
- Resource access
- Inter-process communication

SMB is commonly associated with TCP port 445.

---

# SMB Ports

Important SMB-related ports include:

| Port | Protocol | Purpose |
|---|---|---|
| 139 | TCP | SMB over NetBIOS |
| 445 | TCP | Direct SMB |

---

# SMB Enumeration Information

SMB enumeration may reveal:

- Shared folders
- Share names
- User accounts
- Groups
- Domain names
- Computer names
- Operating system information
- SMB versions
- Security settings

---

# SMB Shares

An SMB share allows network users or systems to access shared resources.

Examples include:

    \\server\public

    \\server\documents

    \\server\backup

Poorly configured shares may expose sensitive files or directories.

---

# SMB Enumeration with Nmap

Example:

    nmap -p 445 --script smb-enum-shares <target>

Additional SMB-related NSE scripts can be used to gather information about:

- Users
- Shares
- Security configuration
- SMB protocols
- Host information

---

# enum4linux

## Definition

enum4linux is a tool used to enumerate information from Windows and Samba systems.

Example:

    enum4linux <target>

It can collect information such as:

- Users
- Groups
- Shares
- Domain information
- Workgroup information
- Operating system information
- Password policies

---

# enum4linux-ng

enum4linux-ng is a modern implementation designed for Windows and Samba enumeration.

Example:

    enum4linux-ng <target>

It can provide structured information about:

- SMB
- Users
- Groups
- Shares
- Domains
- Policies

---

# smbclient

`smbclient` is a command-line utility used to interact with SMB shares.

Example:

    smbclient -L //<target>/

The `-L` option can be used to list available shares when the target permits the requested access.

---

# SMB Security Considerations

Organizations should:

- Disable SMBv1 where unnecessary
- Restrict TCP 445 exposure
- Use strong authentication
- Apply least privilege
- Secure shared folders
- Remove unnecessary shares
- Keep systems patched
- Monitor SMB activity

---

# SNMP Enumeration

## Definition

Simple Network Management Protocol (SNMP) is used to monitor and manage network devices and systems.

SNMP can be found on:

- Routers
- Switches
- Servers
- Printers
- Firewalls
- Network appliances

---

# SNMP Ports

Common SNMP ports include:

| Port | Protocol | Purpose |
|---|---|---|
| 161 | UDP | SNMP queries |
| 162 | UDP | SNMP traps |

---

# SNMP Information

SNMP enumeration may reveal:

- Device name
- System description
- Network interfaces
- Routing information
- Hardware information
- Software information
- System uptime
- Network configuration

---

# SNMP Community Strings

SNMPv1 and SNMPv2c commonly use community strings.

Examples of commonly encountered default community strings include:

    public

    private

Default community strings should be changed or disabled where they are not required.

---

# SNMP Enumeration with Nmap

Example:

    nmap -sU -p 161 --script snmp-info <target>

---

# snmpwalk

`snmpwalk` can query SNMP information from a device.

Example:

    snmpwalk -v2c -c <community-string> <target>

The command should only be used against systems that are explicitly authorized for testing.

---

# SNMP Security

Organizations should:

- Avoid default community strings
- Restrict SNMP access
- Use SNMPv3 where appropriate
- Enable authentication
- Enable encryption
- Restrict management interfaces
- Monitor SNMP activity

---

# LDAP Enumeration

## Definition

LDAP stands for Lightweight Directory Access Protocol.

LDAP is used to access and manage directory services and is commonly associated with enterprise identity systems.

---

# LDAP Information

Enumeration may reveal:

- Users
- Groups
- Organizational Units
- Domain information
- Computer accounts
- Directory structure

---

# LDAP Ports

Common LDAP ports are:

| Port | Protocol | Purpose |
|---|---|---|
| 389 | TCP/UDP | LDAP |
| 636 | TCP | LDAPS |

---

# Active Directory Enumeration

Active Directory is Microsoft's directory service used to manage:

- Users
- Computers
- Groups
- Authentication
- Policies
- Network resources

Enumeration can reveal relationships between these objects.

---

# Active Directory Information

An authorized assessment may identify:

- Domain names
- Domain controllers
- User accounts
- Security groups
- Group memberships
- Organizational Units
- Computer accounts
- Trust relationships
- Group Policies

---

# LDAP Enumeration with ldapsearch

`ldapsearch` is a command-line utility used to query LDAP directories.

A basic query may look like:

    ldapsearch -x -H ldap://<target> -b "<base-dn>"

The exact query depends on the directory configuration and authentication requirements.

---

# DNS Enumeration

## Definition

DNS enumeration is the process of collecting information from the Domain Name System.

DNS information can help identify:

- Hostnames
- IP addresses
- Mail servers
- Name servers
- Subdomains
- DNS records

---

# Common DNS Records

| Record | Purpose |
|---|---|
| A | Maps a hostname to an IPv4 address |
| AAAA | Maps a hostname to an IPv6 address |
| MX | Identifies mail servers |
| NS | Identifies authoritative name servers |
| CNAME | Creates an alias |
| TXT | Stores text information |
| SOA | Provides zone authority information |
| PTR | Provides reverse DNS mapping |

---

# DNS Enumeration Tools

Common DNS enumeration tools include:

- dig
- nslookup
- host
- dnsrecon
- fierce
- Nmap

---

# dig

`dig` is a DNS query utility.

Basic query:

    dig example.com

Query an MX record:

    dig example.com MX

Query NS records:

    dig example.com NS

Query TXT records:

    dig example.com TXT

---

# nslookup

`nslookup` can be used to query DNS information.

Example:

    nslookup example.com

---

# host

The `host` command can perform basic DNS lookups.

Example:

    host example.com

---

# DNS Zone Transfer

## Definition

A DNS zone transfer is a mechanism used to replicate DNS zone information between DNS servers.

Common zone transfer types include:

- AXFR
- IXFR

---

# AXFR

AXFR is a full DNS zone transfer.

A misconfigured DNS server may unintentionally allow unauthorized zone transfers.

A successful zone transfer can expose:

- Hostnames
- Subdomains
- IP addresses
- Internal naming information
- DNS records

---

# Testing DNS Zone Transfer

Example:

    dig axfr @<nameserver> <domain>

This should only be performed against an authorized DNS server.

---

# DNS Security

Organizations should:

- Restrict zone transfers
- Permit transfers only to authorized DNS servers
- Monitor DNS activity
- Protect internal DNS information
- Review DNS configurations regularly

---

# SMTP Enumeration

## Definition

Simple Mail Transfer Protocol (SMTP) is primarily used for sending email.

SMTP enumeration may provide information about:

- Mail servers
- Supported commands
- Mail domains
- Server software
- Potentially valid usernames in some configurations

---

# SMTP Ports

Common SMTP-related ports include:

| Port | Purpose |
|---|---|
| 25 | SMTP |
| 465 | SMTP over implicit TLS |
| 587 | Mail submission |

---

# SMTP Banner

An SMTP server may provide a banner when a connection is established.

Example:

    220 mail.example.com ESMTP

A banner may reveal:

- Hostname
- Mail software
- Service information

---

# SMTP Enumeration with Nmap

Example:

    nmap -p 25 --script smtp-commands <target>

---

# SMTP Security

Organizations should:

- Avoid unnecessary banner information
- Restrict unauthorized mail relay
- Use secure authentication
- Monitor SMTP activity
- Keep mail servers patched

---

# FTP Enumeration

## Definition

File Transfer Protocol (FTP) is used to transfer files between systems.

FTP commonly operates on TCP port 21.

---

# FTP Information

Enumeration may reveal:

- FTP server software
- Version information
- Anonymous access
- Available directories
- Supported commands
- Server configuration

---

# FTP Anonymous Access

Some FTP servers may permit anonymous access.

Example:

    ftp <target>

If anonymous access is intentionally enabled, the server may accept:

    anonymous

Anonymous access should be disabled when it is not required.

---

# FTP Enumeration with Nmap

Service detection:

    nmap -sV -p 21 <target>

Anonymous access check:

    nmap -p 21 --script ftp-anon <target>

---

# FTP Security

Organizations should:

- Disable anonymous access when unnecessary
- Prefer secure file-transfer protocols
- Restrict FTP exposure
- Apply access controls
- Monitor file-transfer activity

---

# NFS Enumeration

## Definition

Network File System (NFS) allows systems to share directories over a network.

NFS is commonly found in Unix and Linux environments.

---

# NFS Port

NFS commonly uses:

    TCP/UDP 2049

Additional RPC services may also be involved.

---

# NFS Enumeration

The `showmount` utility can display exported NFS directories.

Example:

    showmount -e <target>

Example result:

    Export list for target:
    /home
    /var/share

---

# NFS Security Risks

Poorly configured NFS exports may expose:

- User directories
- Configuration files
- Application data
- Sensitive files

Organizations should:

- Restrict exports
- Use appropriate permissions
- Limit trusted hosts
- Avoid unnecessary exposure

---

# RPC Enumeration

## Definition

Remote Procedure Call (RPC) allows applications to request services from another system.

RPC enumeration can identify services running on a target system.

---

# RPC Portmapper

The RPC portmapper commonly uses:

    TCP/UDP 111

It can help identify RPC services and their associated ports.

---

# rpcinfo

`rpcinfo` can query RPC services.

Example:

    rpcinfo -p <target>

Information may include:

- RPC program numbers
- Protocol
- Port
- Service version

---

# Banner Grabbing

## Definition

Banner grabbing is the process of obtaining information from a network service banner.

A banner may reveal:

- Service name
- Software name
- Version
- Operating system information

---

# Banner Grabbing with Netcat

Example:

    nc -nv <target> 80

After connecting to an HTTP service, a request may be manually sent:

    HEAD / HTTP/1.1
    Host: example.com
    Connection: close

---

# Banner Grabbing with Nmap

Example:

    nmap -sV <target>

Nmap attempts to identify services and versions associated with open ports.

---

# Importance of Banner Information

Service and version information can be compared with:

- Vendor advisories
- CVE databases
- Security bulletins
- Vulnerability scanners
- Patch information

This can help determine whether further vulnerability assessment is required.

---

# Linux Enumeration

Linux systems may expose information through network services such as:

- SSH
- DNS
- NFS
- RPC
- SNMP
- HTTP
- FTP

An authorized assessment may identify:

- Hostname
- Operating system
- Kernel information
- Running services
- NFS exports
- Network configuration
- Service versions

---

# Windows Enumeration

Windows enumeration commonly focuses on:

- SMB
- NetBIOS
- LDAP
- Active Directory
- RPC
- Users
- Groups
- Shares
- Domains
- Policies

---

# Enumeration Through Misconfiguration

Enumeration can identify security weaknesses such as:

- Anonymous access
- Open network shares
- Default SNMP community strings
- Unrestricted DNS zone transfers
- Excessive service information
- Weak service configurations
- Unnecessary exposed services

---

# Service Enumeration Methodology

A structured approach can be represented as:

    Open Port
       ↓
    Identify Service
       ↓
    Identify Version
       ↓
    Understand Service
       ↓
    Enumerate Service
       ↓
    Collect Information
       ↓
    Validate Findings
       ↓
    Assess Security Impact

---

# Enumeration and Vulnerability Assessment

Enumeration does not automatically prove that a vulnerability exists.

Example:

    Port 445 Open
          ↓
    SMB Detected
          ↓
    SMB Enumeration
          ↓
    Users / Shares / Configuration
          ↓
    Vulnerability Assessment
          ↓
    Validation

Enumeration provides the information required to perform more targeted vulnerability analysis.

---

# Information Correlation

Information collected from multiple services should be correlated.

Example:

    DNS
     ↓
    Domain Information
     ↓
    SMB
     ↓
    Hostnames and Shares
     ↓
    LDAP
     ↓
    Users and Groups
     ↓
    SNMP
     ↓
    Network Information
     ↓
    Complete Network Profile

Correlating information can reveal relationships that may not be visible from a single service.

---

# Enumeration Risks

Poorly secured services can expose:

- User information
- Hostnames
- Domain information
- Network shares
- Service versions
- Infrastructure details
- Configuration information

This information can help attackers perform more targeted attacks.

---

# Defensive Measures

Organizations should:

- Disable unnecessary services
- Restrict network access
- Use firewall controls
- Remove default configurations
- Disable anonymous access
- Secure SMB
- Restrict SNMP
- Secure LDAP
- Restrict DNS zone transfers
- Secure NFS exports
- Minimize service banners
- Apply least privilege
- Monitor suspicious enumeration activity

---

# Enumeration Detection

Security teams can monitor for:

- SMB connection attempts
- LDAP queries
- SNMP requests
- DNS zone-transfer attempts
- FTP connections
- RPC queries
- NFS requests
- Repeated service probes
- Port scanning followed by service-specific queries

Potential monitoring sources include:

- Firewalls
- IDS
- IPS
- SIEM
- Network monitoring systems
- Endpoint telemetry

---

# Enumeration Tools Summary

| Tool | Primary Use |
|---|---|
| Nmap | Network and service enumeration |
| enum4linux | Windows/Samba enumeration |
| enum4linux-ng | Modern Windows/Samba enumeration |
| smbclient | SMB share interaction |
| snmpwalk | SNMP enumeration |
| rpcinfo | RPC service enumeration |
| showmount | NFS export enumeration |
| dig | DNS enumeration |
| nslookup | DNS queries |
| host | DNS lookups |
| dnsrecon | DNS reconnaissance |
| fierce | DNS reconnaissance |
| ldapsearch | LDAP enumeration |
| Netcat | Connectivity and banner grabbing |

---

# Important Enumeration Ports

| Port | Service | Enumeration Area |
|---|---|---|
| 21 | FTP | FTP information |
| 25 | SMTP | Mail server information |
| 53 | DNS | DNS records |
| 80 | HTTP | Web service information |
| 111 | RPC | RPC services |
| 135 | MSRPC | Windows RPC |
| 137 | NetBIOS-NS | NetBIOS information |
| 139 | NetBIOS/SMB | Windows file sharing |
| 143 | IMAP | Mail service |
| 161 | SNMP | Device information |
| 389 | LDAP | Directory services |
| 443 | HTTPS | Web service |
| 445 | SMB | Windows file sharing |
| 636 | LDAPS | Secure LDAP |
| 2049 | NFS | Network file sharing |

---

# Practical Enumeration Workflow

A practical workflow may look like:

    Nmap
      ↓
    Identify Open Ports
      ↓
    Identify Services
      ↓
    Select Service-Specific Tool
      ↓
    Enumerate Users / Shares / Records
      ↓
    Correlate Information
      ↓
    Validate Findings
      ↓
    Vulnerability Assessment
      ↓
    Documentation

---

# Enumeration Checklist

Before completing enumeration, verify whether you have identified:

- [ ] Hostname
- [ ] IP address
- [ ] Operating system
- [ ] Open ports
- [ ] Running services
- [ ] Service versions
- [ ] Domain name
- [ ] Workgroup
- [ ] Users
- [ ] Groups
- [ ] Network shares
- [ ] DNS records
- [ ] SNMP information
- [ ] RPC services
- [ ] NFS exports
- [ ] FTP configuration
- [ ] SMTP information
- [ ] LDAP information
- [ ] Security misconfigurations

---

# CEH Exam Tips

Remember:

- Enumeration is an active information-gathering technique.
- Enumeration generally follows scanning.
- NetBIOS commonly uses ports 137, 138, and 139.
- SMB commonly uses TCP 445.
- SNMP commonly uses UDP 161.
- SNMP traps commonly use UDP 162.
- LDAP commonly uses TCP/UDP 389.
- LDAPS commonly uses TCP 636.
- DNS commonly uses port 53.
- FTP commonly uses TCP 21.
- SMTP commonly uses TCP 25.
- RPC portmapper commonly uses port 111.
- NFS commonly uses TCP/UDP 2049.
- enum4linux is commonly used for Windows/Samba enumeration.
- enum4linux-ng is a modern Windows/Samba enumeration tool.
- snmpwalk is used for SNMP enumeration.
- rpcinfo is used to enumerate RPC services.
- showmount can display NFS exports.
- dig, nslookup, and host are DNS query tools.
- DNS zone transfers commonly use AXFR or IXFR.
- SMB enumeration can reveal shares, users, groups, and domain information.
- SNMP enumeration can reveal network-device and system information.
- LDAP enumeration can reveal directory information.
- Banner grabbing can reveal service and version information.
- Enumeration provides information for more targeted vulnerability assessment.
- Enumeration findings should be validated before being reported as confirmed vulnerabilities.
- Enumeration should only be performed against authorized targets.

---

# Key Takeaways

- Enumeration is the process of extracting detailed information from identified network services.
- It is more targeted and detailed than basic network scanning.
- Windows environments commonly involve SMB, NetBIOS, LDAP, RPC, and Active Directory enumeration.
- Linux environments commonly involve services such as NFS, RPC, DNS, SNMP, and other network services.
- DNS enumeration can reveal domains, subdomains, mail servers, and infrastructure information.
- SMB enumeration can expose users, groups, shares, and domain information.
- SNMP can expose valuable network and device information when improperly configured.
- LDAP enumeration can reveal directory and identity information.
- Banner grabbing can help identify service software and versions.
- Tools such as Nmap, enum4linux, snmpwalk, rpcinfo, showmount, dig, and ldapsearch support service-specific enumeration.
- Misconfigured services can expose sensitive information and increase an organization's attack surface.
- Effective enumeration should be systematic, targeted, documented, and followed by vulnerability analysis.
- The objective of enumeration is to transform discovered services into actionable technical intelligence for security assessment.
