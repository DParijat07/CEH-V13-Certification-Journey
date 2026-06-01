# Linux Cheat Sheet for CEH & Cybersecurity

## Overview

This cheat sheet contains essential Linux commands commonly used in cybersecurity, ethical hacking, penetration testing, system administration, and CEH practical labs.

---

# Basic Navigation

## Current Directory

```bash
pwd
```

Display current working directory.

---

## List Files

```bash
ls
```

List files and directories.

```bash
ls -l
```

Long listing format.

```bash
ls -la
```

Show hidden files.

---

## Change Directory

```bash
cd directory_name
```

Move to a directory.

```bash
cd ..
```

Move up one directory.

```bash
cd ~
```

Go to home directory.

---

# File Operations

## Create File

```bash
touch file.txt
```

---

## Create Directory

```bash
mkdir folder_name
```

Create single directory.

```bash
mkdir -p parent/child
```

Create nested directories.

---

## Copy Files

```bash
cp file1 file2
```

```bash
cp -r folder1 folder2
```

Copy directories.

---

## Move Files

```bash
mv old.txt new.txt
```

Rename file.

```bash
mv file.txt /target/path
```

Move file.

---

## Delete Files

```bash
rm file.txt
```

Delete file.

```bash
rm -r folder
```

Delete directory recursively.

---

# Viewing Files

## Display File Content

```bash
cat file.txt
```

---

## Read Large Files

```bash
less file.txt
```

```bash
more file.txt
```

---

## View Beginning

```bash
head file.txt
```

---

## View End

```bash
tail file.txt
```

```bash
tail -f logfile.log
```

Monitor logs in real time.

---

# Searching

## Find Files

```bash
find / -name filename
```

---

## Search Text

```bash
grep "password" file.txt
```

---

## Search Recursively

```bash
grep -r "admin" .
```

---

# Permissions

## View Permissions

```bash
ls -l
```

Example:

```text
-rwxr-xr-x
```

---

## Change Permissions

```bash
chmod 755 file
```

```bash
chmod +x script.sh
```

Make executable.

---

## Change Ownership

```bash
chown user:user file
```

---

# User Management

## Current User

```bash
whoami
```

---

## User Information

```bash
id
```

---

## Switch User

```bash
su username
```

---

## Run as Root

```bash
sudo command
```

---

# Process Management

## Running Processes

```bash
ps
```

```bash
ps aux
```

---

## Interactive Process Viewer

```bash
top
```

```bash
htop
```

---

## Kill Process

```bash
kill PID
```

```bash
kill -9 PID
```

---

# Networking Commands

## Show IP Address

```bash
ip a
```

---

## Routing Table

```bash
ip route
```

---

## Ping

```bash
ping google.com
```

---

## DNS Lookup

```bash
nslookup google.com
```

---

## Network Connections

```bash
netstat -tulnp
```

or

```bash
ss -tulnp
```

---

## ARP Table

```bash
arp -a
```

---

# Cybersecurity Enumeration Commands

## Host Discovery

```bash
netdiscover
```

---

## ARP Scan

```bash
arp-scan -l
```

---

## Nmap Basic Scan

```bash
nmap TARGET
```

---

## Service Detection

```bash
nmap -sV TARGET
```

---

## OS Detection

```bash
nmap -O TARGET
```

---

## Aggressive Scan

```bash
nmap -A TARGET
```

---

## Vulnerability Scan

```bash
nmap --script vuln TARGET
```

---

# System Information

## Kernel Information

```bash
uname -a
```

---

## OS Information

```bash
cat /etc/os-release
```

---

## CPU Information

```bash
lscpu
```

---

## Memory Information

```bash
free -h
```

---

## Disk Usage

```bash
df -h
```

---

## Directory Size

```bash
du -sh *
```

---

# Compression

## Zip

```bash
zip file.zip file.txt
```

---

## Unzip

```bash
unzip file.zip
```

---

## Tar

```bash
tar -cvf backup.tar folder
```

Extract:

```bash
tar -xvf backup.tar
```

---

# Package Management (Kali/Debian)

## Update Repository

```bash
sudo apt update
```

---

## Upgrade Packages

```bash
sudo apt upgrade
```

---

## Install Package

```bash
sudo apt install package-name
```

---

## Remove Package

```bash
sudo apt remove package-name
```

---

# Log Files

## Authentication Logs

```bash
/var/log/auth.log
```

---

## System Logs

```bash
/var/log/syslog
```

---

## Read Logs

```bash
tail -f /var/log/syslog
```

---

# Useful CEH Commands

## Discover Hosts

```bash
netdiscover
arp-scan -l
```

---

## Enumerate Services

```bash
nmap -sV TARGET
```

---

## Identify Vulnerabilities

```bash
nmap --script vuln TARGET
```

---

## Check Open Ports

```bash
netstat -tulnp
```

---

## Verify User

```bash
whoami
id
```

---

## Examine Processes

```bash
ps aux
top
```

---

# Important Linux Directories

| Directory | Purpose                |
| --------- | ---------------------- |
| /         | Root                   |
| /home     | User directories       |
| /root     | Root user home         |
| /etc      | Configuration files    |
| /var      | Logs and variable data |
| /tmp      | Temporary files        |
| /usr      | Programs and libraries |
| /bin      | Essential binaries     |
| /opt      | Optional software      |

---

# CEH Exam Focus Areas

✔ Linux Navigation

✔ File Management

✔ User Management

✔ Permissions

✔ Networking

✔ Enumeration

✔ Log Analysis

✔ Process Management

✔ Basic Scripting

✔ Nmap Usage

✔ Security Tool Operation

---

## Quick Daily Commands

```bash
pwd
ls -la
whoami
id
ip a
ping TARGET
netdiscover
arp-scan -l
nmap -sV TARGET
ps aux
top
df -h
free -h
```

These are the Linux commands most frequently encountered during CEH labs, TryHackMe rooms, vulnerability assessments, and entry-level SOC/VAPT work.
