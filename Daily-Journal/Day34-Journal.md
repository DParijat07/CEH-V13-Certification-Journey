## Day 34 (29/06/2026)

* **Practical Lab:** Basic Penetration Testing 1 (VulnHub)

### Activities Performed

* Downloaded the **Basic Penetration Testing 1** vulnerable machine from VulnHub.
* Imported the VM into VMware Workstation.
* Configured the target machine and Kali Linux on the **NAT** network.
* Performed host discovery using **Netdiscover**.
* Verified connectivity using **Ping**.
* Conducted aggressive service enumeration using **Nmap (-A)**.
* Identified the following open services:

  * FTP (ProFTPD 1.3.3c)
  * SSH (OpenSSH)
  * HTTP (Apache 2.4.18)
* Researched the detected ProFTPD version and identified the backdoored ProFTPD vulnerability.
* Used the Metasploit Framework to exploit the vulnerable FTP service.
* Enumerated compatible payloads and selected the **cmd/unix/reverse_perl** payload.
* Successfully obtained a **remote root command shell**.
* Performed post-exploitation enumeration:

  * Explored the Linux filesystem.
  * Enumerated users and directories.
  * Investigated the **marlinspike** user's home directory.
  * Located WordPress files and ProFTPD source code archives.
  * Extracted the password hash from **/etc/shadow**.
* Learned the structure of Linux password hashes.
* Practiced the workflow for offline password auditing using **John the Ripper** and **Hashcat**.

### Key Skills Learned

* Host discovery

* Network scanning

* Service enumeration

* Vulnerability analysis

* Metasploit exploitation

* Payload selection

* Remote shell access

* Linux post-exploitation

* User and filesystem enumeration

* Password hash extraction

* Offline password auditing concepts

* **TryHackMe Streak Maintained:** Yes (Day 34)

* **GitHub Documentation:** Planned after completing the full machine walkthrough and documentation.

### Reflection

Today's lab significantly improved my practical penetration testing workflow. I gained hands-on experience in reconnaissance, exploitation, post-exploitation, and password auditing, reinforcing the importance of systematic enumeration before exploiting vulnerabilities.
