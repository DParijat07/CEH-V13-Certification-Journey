# Module 20 – Cryptography

## Part 1 – Cryptography Fundamentals

---

# Overview

Cryptography is the science of protecting information by converting readable data into an unreadable format using mathematical algorithms. It ensures that only authorized users can access or modify sensitive information.

Modern cryptography is a fundamental component of cybersecurity and is used in secure communication, online banking, VPNs, HTTPS, digital signatures, cloud computing, wireless security, and identity management.

---

# What is Cryptography?

Cryptography is the practice of securing information through mathematical techniques that provide confidentiality, integrity, authentication, and non-repudiation.

It allows information to remain secure even if attackers intercept the communication.

---

# Goals of Cryptography

Modern cryptography provides several important security services.

## 1. Confidentiality

Ensures that only authorized individuals can access information.

Example:

An encrypted email cannot be read without the correct decryption key.

---

## 2. Integrity

Ensures that data has not been altered during storage or transmission.

Common technologies:

- Hash Functions
- Message Authentication Codes (MAC)
- Digital Signatures

---

## 3. Authentication

Verifies the identity of users, devices, or services.

Examples:

- Password authentication
- Digital certificates
- Multi-Factor Authentication (MFA)

---

## 4. Non-Repudiation

Prevents a sender from denying that they sent a message.

Typically achieved using:

- Digital Signatures
- PKI
- Certificates

---

# CIA Triad

Cryptography directly supports the CIA Triad.

## Confidentiality

Protects information from unauthorized disclosure.

Examples:

- AES Encryption
- VPN
- HTTPS

---

## Integrity

Protects against unauthorized modification.

Examples:

- SHA-256
- Digital Signatures

---

## Availability

Ensures authorized users can access data when needed.

Availability is supported through:

- Redundancy
- Backup
- Disaster Recovery
- High Availability

Although availability is not provided directly by encryption, cryptographic systems must be implemented without unnecessarily reducing system accessibility.

---

# Basic Cryptographic Terminology

## Plaintext

Readable, original information before encryption.

Example:

```
Password123
```

---

## Ciphertext

Encrypted data that appears unreadable.

Example:

```
4F6A92B8E51D...
```

Ciphertext cannot be interpreted without the appropriate key.

---

## Encryption

The process of converting plaintext into ciphertext.

Purpose:

- Protect confidentiality
- Prevent unauthorized access

---

## Decryption

The process of converting ciphertext back into plaintext using the appropriate key.

---

## Cipher

A mathematical algorithm used to encrypt and decrypt information.

Examples:

- AES
- RSA
- DES
- Blowfish

---

## Key

A value used by cryptographic algorithms.

Keys determine how encryption and decryption occur.

Without the correct key, encrypted data should remain unreadable.

---

# Encryption Lifecycle

The basic encryption process is:

```
Plaintext
      ↓
Encryption Algorithm
      ↓
Encryption Key
      ↓
Ciphertext
      ↓
Transmission / Storage
      ↓
Decryption Key
      ↓
Plaintext
```

---

# History of Cryptography

Cryptography has evolved over thousands of years.

Major historical developments include:

- Caesar Cipher
- Vigenère Cipher
- Enigma Machine
- DES
- RSA
- AES
- Elliptic Curve Cryptography (ECC)

Modern cryptography relies on advanced mathematical principles rather than simple substitution techniques.

---

# Classical Cryptography

Classical cryptography primarily relied on:

- Substitution ciphers
- Transposition ciphers
- Manual encryption

Examples include:

- Caesar Cipher
- Vigenère Cipher
- Playfair Cipher

These techniques are now considered insecure against modern computing power.

---

# Modern Cryptography

Modern cryptography uses complex mathematical algorithms and computational hardness to provide security.

Characteristics include:

- Strong encryption
- Large key sizes
- Public-key cryptography
- Digital signatures
- Secure key exchange
- Hash functions

---

# Security Services Provided by Cryptography

Cryptography enables:

- Confidentiality
- Integrity
- Authentication
- Non-Repudiation
- Secure Communication
- Secure Storage
- Identity Verification
- Data Protection

---

# Types of Cryptography

Modern cryptography is generally divided into:

## Symmetric Cryptography

Uses one shared secret key.

Characteristics:

- Fast
- Efficient
- Suitable for encrypting large amounts of data

Examples:

- AES
- DES
- 3DES
- Blowfish

---

## Asymmetric Cryptography

Uses two mathematically related keys.

- Public Key
- Private Key

Characteristics:

- Secure key exchange
- Digital signatures
- Authentication

Examples:

- RSA
- ECC
- ElGamal

---

## Hash Functions

Hash functions convert data into a fixed-length hash value.

Characteristics:

- One-way function
- No decryption
- Used for integrity verification

Examples:

- SHA-256
- SHA-3
- SHA-512

---

# Cryptography vs Encoding vs Hashing vs Obfuscation

## Encryption

Purpose:

Protect confidentiality.

Can be decrypted with the appropriate key.

---

## Encoding

Purpose:

Represent data in another format.

Examples:

- Base64
- URL Encoding

Encoding is **not** a security mechanism.

---

## Hashing

Purpose:

Verify integrity.

Cannot be reversed.

---

## Obfuscation

Purpose:

Make code or information difficult to understand.

Provides limited security and should not replace encryption.

---

# Real-World Applications of Cryptography

Cryptography protects:

- HTTPS websites
- Online banking
- VPNs
- Secure messaging
- Cloud storage
- Wireless networks
- Digital certificates
- Password databases
- Blockchain
- Software updates

---

# CEH Exam Tips

Remember:

- Cryptography protects confidentiality, integrity, authentication, and non-repudiation.
- Plaintext is readable data.
- Ciphertext is encrypted data.
- Encryption converts plaintext into ciphertext.
- Decryption restores ciphertext to plaintext.
- Symmetric encryption uses one key.
- Asymmetric encryption uses two keys.
- Hashing provides integrity, not confidentiality.
- Encoding is not encryption.

---

# Key Takeaways

- Cryptography is the foundation of secure digital communication.
- Modern cryptographic systems rely on mathematical algorithms and secure key management.
- Understanding cryptographic terminology and security goals is essential before learning encryption algorithms, PKI, hashing, and digital signatures.

# Module 20 – Cryptography

## Part 2 – Encryption Algorithms

---

# Overview

Encryption algorithms transform plaintext into ciphertext using mathematical operations and cryptographic keys. Modern encryption algorithms are broadly divided into **symmetric encryption** and **asymmetric encryption**.

Selecting the appropriate algorithm depends on factors such as performance, security, scalability, and use case.

---

# Symmetric Encryption

## Overview

Symmetric encryption uses **one shared secret key** for both encryption and decryption.

```
Plaintext
     ↓
Encryption
     ↓
Secret Key
     ↓
Ciphertext
     ↓
Decryption
     ↓
Secret Key
     ↓
Plaintext
```

Both sender and receiver must possess the same key.

---

## Advantages

- Very fast
- Efficient for large files
- Low computational overhead
- Suitable for disk and database encryption

---

## Disadvantages

- Secure key distribution is difficult
- Poor scalability
- Key compromise exposes all encrypted data

---

## Common Symmetric Algorithms

- DES
- 3DES
- AES
- Blowfish
- Twofish
- RC4 (legacy)

---

# Asymmetric Encryption

## Overview

Asymmetric encryption uses a **key pair**:

- Public Key
- Private Key

The public key encrypts data, while the private key decrypts it.

```
Plaintext
      ↓
Public Key
      ↓
Ciphertext
      ↓
Private Key
      ↓
Plaintext
```

---

## Advantages

- Secure key exchange
- Digital signatures
- Authentication
- Better scalability

---

## Disadvantages

- Slower than symmetric encryption
- More computationally intensive
- Not ideal for encrypting large amounts of data

---

## Common Asymmetric Algorithms

- RSA
- ECC
- ElGamal

---

# Block Cipher

A block cipher encrypts fixed-size blocks of data.

Examples:

- AES
- DES
- 3DES
- Blowfish
- Twofish

### Advantages

- High security
- Suitable for files and databases
- Widely adopted

---

# Stream Cipher

A stream cipher encrypts data one bit or one byte at a time.

Examples:

- RC4 (legacy)
- ChaCha20 (modern)

### Advantages

- Fast for streaming data
- Low latency

---

# Data Encryption Standard (DES)

## Overview

DES was developed by IBM and standardized in 1977.

### Characteristics

- Symmetric cipher
- Block size: 64 bits
- Key size: 56 bits

---

## Advantages

- Historically significant
- Simple implementation

---

## Limitations

- Small key size
- Vulnerable to brute-force attacks
- No longer considered secure

DES has been deprecated.

---

# Triple DES (3DES)

## Overview

3DES improves DES by applying DES encryption three times.

### Characteristics

- Symmetric cipher
- Larger effective key size
- More secure than DES

---

## Limitations

- Slower than AES
- Being phased out
- Not recommended for new systems

---

# Advanced Encryption Standard (AES)

## Overview

AES is the modern encryption standard adopted worldwide.

### Characteristics

- Symmetric cipher
- Block size: 128 bits
- Key sizes:
  - 128-bit
  - 192-bit
  - 256-bit

---

## Advantages

- High performance
- Strong security
- Resistant to known practical attacks
- Government-approved

---

## Common Applications

- HTTPS
- VPN
- Wi-Fi (WPA2/WPA3)
- Disk encryption
- Cloud storage
- Banking systems

AES is currently the most widely used symmetric encryption algorithm.

---

# Blowfish

## Overview

Blowfish is a symmetric block cipher designed by Bruce Schneier.

### Characteristics

- Variable key length
- Fast encryption
- Publicly available

---

## Applications

- Password protection
- File encryption
- Embedded systems

---

# Twofish

## Overview

Twofish is the successor to Blowfish.

### Characteristics

- Symmetric block cipher
- 128-bit block size
- Key sizes up to 256 bits

---

## Advantages

- High security
- Flexible implementation
- Strong performance

Although secure, AES became the official encryption standard instead.

---

# RC4

## Overview

RC4 is a stream cipher once widely used in SSL and WEP.

---

## Limitations

- Significant cryptographic weaknesses
- Predictable keystream bias
- Vulnerable to attacks

RC4 should not be used in modern systems.

---

# RSA

## Overview

RSA is one of the most widely used public-key algorithms.

### Characteristics

- Asymmetric encryption
- Public/Private key pair
- Based on integer factorization

---

## Applications

- Key exchange
- Digital signatures
- Certificate infrastructure
- Secure email

---

## Advantages

- Secure authentication
- Supports digital signatures
- Widely supported

---

## Limitations

- Computationally expensive
- Slower than AES

---

# Elliptic Curve Cryptography (ECC)

## Overview

ECC provides strong security using smaller keys than RSA.

### Advantages

- Faster computation
- Smaller keys
- Lower bandwidth
- Lower power consumption

---

## Applications

- Mobile devices
- IoT
- Smart cards
- Cryptocurrency
- Modern TLS

---

# Diffie-Hellman Key Exchange

## Overview

Diffie-Hellman enables two parties to securely establish a shared secret over an insecure network.

### Important Note

Diffie-Hellman is a **key exchange algorithm**, not an encryption algorithm.

---

## Applications

- VPN
- TLS
- SSH
- Secure communications

---

# Hybrid Encryption

Modern secure communication combines both encryption types.

Example:

```
RSA / ECC
      ↓
Secure Key Exchange
      ↓
AES Session Key
      ↓
Fast Data Encryption
```

This provides both security and performance.

Examples include:

- HTTPS
- TLS
- VPN
- SSH

---

# Symmetric vs Asymmetric Encryption

| Feature | Symmetric | Asymmetric |
|---------|-----------|------------|
| Keys | One shared key | Public & Private keys |
| Speed | Fast | Slower |
| Performance | High | Moderate |
| Scalability | Lower | Higher |
| Main Use | Data encryption | Key exchange & authentication |

---

# Block Cipher vs Stream Cipher

| Block Cipher | Stream Cipher |
|--------------|---------------|
| Encrypts blocks | Encrypts bits/bytes |
| Better for files | Better for streaming |
| Examples: AES, DES | Examples: RC4, ChaCha20 |

---

# Algorithm Comparison

| Algorithm | Type | Status |
|------------|------|--------|
| DES | Symmetric | Deprecated |
| 3DES | Symmetric | Legacy |
| AES | Symmetric | Recommended |
| Blowfish | Symmetric | Secure (legacy use) |
| Twofish | Symmetric | Secure |
| RC4 | Stream | Deprecated |
| RSA | Asymmetric | Widely used |
| ECC | Asymmetric | Recommended |
| Diffie-Hellman | Key Exchange | Widely used |

---

# CEH Exam Tips

Remember:

- AES is the current encryption standard.
- DES uses a 56-bit key and is insecure.
- 3DES is stronger than DES but slower than AES.
- RC4 is deprecated.
- RSA uses public and private keys.
- ECC offers similar security with smaller keys.
- Diffie-Hellman performs secure key exchange.
- Hybrid encryption combines asymmetric and symmetric cryptography.

---

# Key Takeaways

- Symmetric encryption provides fast and efficient protection for large amounts of data.
- Asymmetric encryption enables secure key exchange, authentication, and digital signatures.
- AES remains the preferred encryption algorithm for modern systems, while RSA and ECC are commonly used for secure communication and identity verification.

# Module 20 – Cryptography

## Part 3 – Hashing, Digital Signatures & Public Key Infrastructure (PKI)

---

# Overview

In addition to encryption, modern cryptography provides mechanisms to verify data integrity, authenticate identities, and establish trust between communicating parties.

This section covers hash functions, digital signatures, Public Key Infrastructure (PKI), digital certificates, SSL/TLS, and HTTPS.

---

# Hash Functions

## Overview

A hash function is a mathematical algorithm that converts data of any size into a fixed-length output known as a **hash**, **digest**, or **checksum**.

Unlike encryption, hashing is a **one-way process**. The original input cannot be recovered from the hash.

---

## Characteristics of a Secure Hash Function

A secure hash function should provide:

- Deterministic output (same input → same hash)
- Fixed-length output
- Fast computation
- One-way property (pre-image resistance)
- Collision resistance
- Avalanche effect (small input change → large output change)

---

## Common Uses of Hashing

- Password storage
- File integrity verification
- Digital signatures
- Certificate validation
- Malware detection
- Blockchain
- Data deduplication

---

# MD5 (Message Digest 5)

## Overview

MD5 generates a **128-bit hash value**.

Example:

```
Input:
Hello World

MD5:
b10a8db164e0754105b7a99be72e3fe5
```

### Limitations

- Vulnerable to collision attacks
- Cryptographically broken
- Not suitable for security-sensitive applications

Today, MD5 is mainly used for non-security integrity checks.

---

# SHA-1 (Secure Hash Algorithm 1)

## Overview

SHA-1 produces a **160-bit hash**.

### Limitations

- Practical collision attacks exist
- Deprecated by major vendors
- No longer recommended for digital signatures or certificates

---

# SHA-2 Family

SHA-2 is the most widely deployed secure hashing family.

Variants include:

- SHA-224
- SHA-256
- SHA-384
- SHA-512

### SHA-256

Produces a **256-bit hash** and is widely used for:

- SSL/TLS
- Digital certificates
- Blockchain
- File integrity
- Software verification

---

### SHA-512

Produces a **512-bit hash** and offers a higher security margin for long-term protection.

---

# SHA-3

SHA-3 is the newest member of the Secure Hash Algorithm family.

### Advantages

- Different internal design from SHA-2
- Resistant to known SHA-2 attack classes
- Provides an alternative standardized hash function

---

# Hash Comparison

| Algorithm | Output Size | Current Status |
|-----------|------------:|----------------|
| MD5 | 128-bit | Deprecated |
| SHA-1 | 160-bit | Deprecated |
| SHA-256 | 256-bit | Recommended |
| SHA-512 | 512-bit | Recommended |
| SHA-3 | Variable | Recommended |

---

# HMAC (Hash-Based Message Authentication Code)

## Overview

HMAC combines:

- A cryptographic hash function
- A secret key

to verify both:

- Data integrity
- Data authenticity

### Common Algorithms

- HMAC-SHA256
- HMAC-SHA512

---

# Digital Signatures

## Overview

A digital signature verifies:

- Sender identity (Authentication)
- Data integrity
- Non-repudiation

Digital signatures use **asymmetric cryptography**.

---

## Digital Signature Process

```
Message
      ↓
Hash Function
      ↓
Message Digest
      ↓
Encrypt Digest
using Sender's Private Key
      ↓
Digital Signature
```

Verification is performed using the sender's **public key**.

---

## Benefits

- Authentication
- Integrity
- Non-repudiation
- Trust

---

# Public Key Infrastructure (PKI)

## Overview

PKI is the framework used to create, distribute, manage, validate, and revoke digital certificates.

PKI enables secure communication over untrusted networks.

---

# PKI Components

A typical PKI consists of:

- Certificate Authority (CA)
- Registration Authority (RA)
- Digital Certificates
- Public Keys
- Private Keys
- Certificate Repository
- Revocation Services

---

# Certificate Authority (CA)

A Certificate Authority is a trusted entity that issues and signs digital certificates.

Responsibilities include:

- Identity verification
- Certificate issuance
- Certificate renewal
- Certificate revocation

Examples:

- DigiCert
- GlobalSign
- Let's Encrypt

---

# Registration Authority (RA)

The Registration Authority verifies the identity of certificate applicants before the CA issues a certificate.

---

# Digital Certificate

A digital certificate binds an entity's identity to its public key.

Typical certificate information includes:

- Subject
- Public Key
- Issuer
- Validity Period
- Serial Number
- Digital Signature
- Signature Algorithm

---

# Certificate Signing Request (CSR)

Before obtaining a certificate, an organization generates a CSR containing:

- Public key
- Organization details
- Domain name

The CSR is sent to the CA for certificate issuance.

---

# Certificate Revocation List (CRL)

A CRL contains certificates that are no longer trusted.

Reasons include:

- Private key compromise
- Certificate expiration
- Organization changes
- Misuse

Clients can check the CRL before trusting a certificate.

---

# Online Certificate Status Protocol (OCSP)

OCSP provides **real-time certificate validation**.

Advantages over CRL:

- Faster
- Smaller responses
- Real-time status
- Reduced bandwidth usage

---

# SSL (Secure Sockets Layer)

SSL was originally developed to secure Internet communications.

Modern versions of SSL are deprecated due to known vulnerabilities.

---

# TLS (Transport Layer Security)

TLS is the modern replacement for SSL.

TLS provides:

- Confidentiality
- Integrity
- Authentication

Current secure versions include:

- TLS 1.2
- TLS 1.3

Older versions should be disabled.

---

# HTTPS

HTTPS combines:

- HTTP
- TLS

to provide secure web communication.

```
Browser
      ↓
TLS Handshake
      ↓
Encrypted Communication
      ↓
Web Server
```

HTTPS protects:

- Login credentials
- Financial transactions
- Personal information
- Session cookies

---

# TLS Handshake (Simplified)

1. Client connects to server.
2. Server sends its digital certificate.
3. Client validates the certificate.
4. Session keys are securely established.
5. Encrypted communication begins.

---

# Code Signing

Code signing verifies:

- Software authenticity
- Publisher identity
- Software integrity

Unsigned or tampered software should not be trusted.

---

# Certificate Validation

Before trusting a certificate, clients verify:

- Issuing CA
- Validity period
- Domain name
- Digital signature
- Revocation status (CRL or OCSP)

---

# CEH Exam Tips

Remember:

- Hashing is one-way and cannot be decrypted.
- MD5 and SHA-1 are deprecated for security use.
- SHA-256 is the most commonly used secure hash algorithm.
- HMAC provides integrity and authenticity.
- Digital signatures use the sender's private key for signing and public key for verification.
- PKI manages digital certificates.
- CA issues certificates, while RA verifies identities.
- TLS replaces SSL.
- HTTPS = HTTP + TLS.

---

# Key Takeaways

- Hash functions ensure data integrity, while digital signatures provide integrity, authentication, and non-repudiation.
- PKI establishes trust through digital certificates and trusted Certificate Authorities.
- TLS and HTTPS protect modern Internet communications using encryption and certificate-based authentication.

# Module 20 – Cryptography

## Part 4 – Cryptographic Attacks and Weaknesses

---

# Overview

Even the strongest encryption algorithms can become ineffective if they are implemented incorrectly or if attackers exploit weaknesses in key management, protocols, software, or human behavior.

Understanding common cryptographic attacks helps security professionals identify vulnerabilities, improve defensive strategies, and investigate security incidents.

---

# Brute Force Attack

## Overview

A brute force attack systematically tries every possible key or password until the correct one is found.

```
Password?
 ↓
123456
 ↓
password
 ↓
admin123
 ↓
Correct Password Found
```

### Characteristics

- Guaranteed to succeed if given enough time
- Computationally expensive
- More effective against weak passwords or short encryption keys

### Defensive Controls

- Long encryption keys
- Strong password policies
- Multi-Factor Authentication (MFA)
- Account lockout policies
- Rate limiting

---

# Dictionary Attack

## Overview

A dictionary attack uses a predefined list of common passwords instead of trying every possible combination.

Common password examples:

- password123
- admin
- qwerty
- welcome123

### Defensive Controls

- Strong password policies
- Password managers
- MFA
- Password complexity requirements

---

# Rainbow Table Attack

## Overview

Rainbow tables contain precomputed hash values used to crack password hashes quickly.

Instead of calculating hashes during an attack, attackers simply look up matching hashes.

### Example

```
Password
     ↓
SHA-256
     ↓
Stored Hash
     ↓
Rainbow Table Lookup
```

### Defensive Controls

- Salting passwords
- Strong hashing algorithms
- Slow password hashing (bcrypt, scrypt, Argon2, PBKDF2)

---

# Birthday Attack

## Overview

The Birthday Attack exploits the probability of finding two inputs that produce the same hash value.

It targets **hash functions**, not encryption algorithms.

### Defensive Controls

- SHA-256
- SHA-3
- Collision-resistant algorithms

---

# Collision Attack

## Overview

A collision occurs when two different inputs generate the same hash value.

```
Input A
      ↓
SHA-1
      ↓
Hash X

Input B
      ↓
SHA-1
      ↓
Hash X
```

### Impact

- Digital signature forgery
- Integrity compromise
- Certificate manipulation

### Defensive Controls

- SHA-256
- SHA-3
- Deprecate MD5 and SHA-1

---

# Cryptanalysis

## Overview

Cryptanalysis is the study of breaking cryptographic systems without possessing the encryption key.

Attackers analyze:

- Algorithms
- Keys
- Protocols
- Mathematical weaknesses

---

# Known Plaintext Attack (KPA)

The attacker possesses:

- Plaintext
- Corresponding ciphertext

The objective is to recover the encryption key.

---

# Chosen Plaintext Attack (CPA)

The attacker chooses arbitrary plaintexts and observes the resulting ciphertext.

Used to analyze encryption algorithms.

---

# Chosen Ciphertext Attack (CCA)

The attacker submits selected ciphertexts for decryption and analyzes the responses.

Modern encryption systems are designed to resist this attack.

---

# Side-Channel Attack

## Overview

Instead of attacking the encryption algorithm directly, attackers exploit information leaked by hardware or software.

Examples:

- Timing information
- Power consumption
- Electromagnetic emissions
- CPU cache behavior

### Defensive Controls

- Constant-time algorithms
- Hardware protections
- Secure hardware modules
- Randomized execution

---

# Padding Oracle Attack

## Overview

Padding Oracle attacks target improperly implemented block cipher encryption.

Attackers observe server responses related to padding errors to gradually recover plaintext.

### Defensive Controls

- Authenticated encryption
- Proper error handling
- TLS updates

---

# SSL Strip Attack

## Overview

SSL Strip downgrades secure HTTPS connections to unencrypted HTTP.

```
Victim
      ↓
HTTP
      ↓
Attacker
      ↓
HTTPS
      ↓
Server
```

The victim believes they are communicating securely.

### Defensive Controls

- HTTPS Everywhere
- HTTP Strict Transport Security (HSTS)
- Modern browsers

---

# Heartbleed

## Overview

Heartbleed was a vulnerability in OpenSSL affecting the TLS Heartbeat extension.

### Potential Impact

Attackers could read portions of server memory containing:

- Private keys
- Passwords
- Session cookies
- Sensitive data

### Defensive Controls

- Patch OpenSSL
- Replace compromised certificates
- Rotate private keys

---

# BEAST Attack

## Overview

BEAST targeted weaknesses in TLS 1.0 using block cipher vulnerabilities.

### Defensive Controls

- TLS 1.2
- TLS 1.3
- Modern cipher suites

---

# POODLE Attack

## Overview

POODLE exploited weaknesses in SSL 3.0.

### Defensive Controls

- Disable SSL 3.0
- Use TLS 1.2 or TLS 1.3

---

# Lucky13 Attack

## Overview

Lucky13 exploited timing differences in CBC-mode encryption implementations.

### Defensive Controls

- TLS updates
- Constant-time cryptographic implementations
- AEAD cipher suites

---

# Weak Random Number Generation

## Overview

Many cryptographic systems rely on random numbers for:

- Keys
- Initialization Vectors (IVs)
- Nonces
- Session tokens

Weak randomness can compromise the entire cryptographic system.

### Defensive Controls

- Cryptographically Secure Random Number Generators (CSPRNG)
- Hardware entropy sources
- Proper seeding

---

# Weak Key Management

Even strong encryption fails if keys are poorly managed.

Common issues include:

- Hardcoded keys
- Shared keys
- Weak key storage
- Lack of rotation
- Unencrypted backups

### Defensive Controls

- Key rotation
- Hardware Security Modules (HSMs)
- Key Management Services (KMS)
- Least Privilege
- Secure backup procedures

---

# Downgrade Attacks

Attackers force communication to use older, weaker protocols or cipher suites.

Examples:

- SSL instead of TLS
- TLS 1.0 instead of TLS 1.3

### Defensive Controls

- Disable legacy protocols
- Enforce modern TLS versions
- Secure cipher suite configuration

---

# Common Cryptographic Weaknesses

Organizations should avoid:

- MD5
- SHA-1
- DES
- RC4
- Weak passwords
- Shared administrator credentials
- Poor certificate validation
- Expired certificates
- Weak random numbers
- Hardcoded secrets

---

# Security Best Practices

Organizations should:

- Use AES-256 for encryption
- Use SHA-256 or SHA-3 for hashing
- Enable MFA
- Rotate keys regularly
- Use TLS 1.2 or TLS 1.3
- Disable legacy protocols
- Secure private keys
- Validate certificates
- Patch cryptographic libraries
- Perform regular security audits

---

# CEH Exam Tips

Remember:

- Brute force attacks try every possible key.
- Dictionary attacks use common password lists.
- Rainbow tables target password hashes.
- Birthday attacks exploit hash collisions.
- Side-channel attacks target implementation weaknesses.
- Heartbleed affected OpenSSL.
- POODLE exploited SSL 3.0.
- BEAST targeted TLS 1.0.
- TLS replaces SSL.
- Strong key management is as important as strong encryption.

---

# Key Takeaways

- Cryptographic systems can fail due to weak implementation, poor key management, outdated algorithms, or vulnerable protocols.
- Modern organizations should adopt strong encryption algorithms, secure key management practices, and current TLS versions while continuously monitoring for cryptographic vulnerabilities.

# Module 20 – Cryptography

## Part 5 – Cryptographic Defense, Emerging Technologies & Module Summary

---

# Overview

Strong cryptography depends not only on secure algorithms but also on proper implementation, key management, hardware protection, and operational security.

This section covers defensive technologies, secure key management, encryption best practices, and emerging trends such as quantum-resistant cryptography.

---

# Key Management

## Overview

Key management is the process of generating, storing, distributing, rotating, backing up, and destroying cryptographic keys securely.

Even the strongest encryption algorithm becomes ineffective if the encryption keys are compromised.

---

# Key Management Lifecycle

A secure key lifecycle typically includes:

1. Key Generation
2. Key Distribution
3. Key Storage
4. Key Usage
5. Key Rotation
6. Key Backup
7. Key Revocation
8. Key Destruction

Regular rotation and secure storage reduce the impact of key compromise.

---

# Hardware Security Module (HSM)

## Overview

A Hardware Security Module (HSM) is a dedicated hardware device designed to generate, store, and protect cryptographic keys.

### Features

- Tamper-resistant hardware
- Secure key generation
- Hardware-based encryption
- Digital signature operations
- High-performance cryptographic processing

### Common Uses

- Certificate Authorities (CA)
- Banking systems
- Payment gateways
- Enterprise PKI
- Cloud key management

---

# Trusted Platform Module (TPM)

## Overview

A Trusted Platform Module (TPM) is a hardware security chip integrated into many computers.

### Functions

- Secure key storage
- Device authentication
- Secure boot support
- Disk encryption support
- Platform integrity verification

### Common Uses

- BitLocker
- Secure Boot
- Windows Hello
- Device identity

---

# Perfect Forward Secrecy (PFS)

## Overview

Perfect Forward Secrecy ensures that compromise of a long-term private key does **not** expose previously encrypted communication.

### Benefits

- Protects past sessions
- Limits damage from key compromise
- Improves long-term confidentiality

PFS is commonly implemented using **Ephemeral Diffie-Hellman (DHE/ECDHE)** in modern TLS.

---

# Disk Encryption

Disk encryption protects the entire storage device against unauthorized access.

### Examples

- BitLocker (Windows)
- FileVault (macOS)
- LUKS (Linux)
- VeraCrypt

### Benefits

- Protects lost or stolen devices
- Secures offline data
- Prevents unauthorized disk access

---

# File Encryption

Individual files can be encrypted independently of the operating system.

### Benefits

- Granular protection
- Secure file sharing
- Protection on removable media

---

# Database Encryption

Sensitive database fields can be encrypted to protect:

- Customer information
- Financial records
- Healthcare data
- Personally Identifiable Information (PII)

Encryption may occur:

- At rest
- In transit
- At the application layer

---

# Email Encryption

Email encryption protects messages from unauthorized access during transmission.

Common technologies include:

- S/MIME
- OpenPGP (GPG)

### Benefits

- Confidentiality
- Integrity
- Authentication
- Digital signatures

---

# Cloud Encryption

Cloud providers support encryption for:

- Object storage
- Virtual disks
- Databases
- Backups
- Key management

Encryption can be:

- Provider-managed
- Customer-managed
- Customer-supplied

---

# VPN Encryption

Virtual Private Networks (VPNs) create encrypted tunnels between endpoints.

Common protocols include:

- IPsec
- OpenVPN
- WireGuard
- SSL/TLS VPN

### Benefits

- Confidentiality
- Integrity
- Secure remote access

---

# Secure Key Storage Best Practices

Organizations should:

- Use HSMs or TPMs
- Avoid hardcoded keys
- Encrypt backup keys
- Rotate keys periodically
- Restrict key access
- Log key usage
- Separate duties for key management

---

# Cryptographic Best Practices

Security teams should:

- Use AES-256 for symmetric encryption
- Use RSA (2048-bit or higher) or ECC for public-key cryptography
- Use SHA-256 or SHA-3 for hashing
- Enable TLS 1.2 or TLS 1.3
- Disable SSL and deprecated TLS versions
- Implement Perfect Forward Secrecy
- Protect private keys
- Validate digital certificates
- Apply MFA
- Keep cryptographic libraries updated

---

# Quantum Cryptography (Overview)

Quantum cryptography uses principles of quantum mechanics to protect communications.

A well-known application is **Quantum Key Distribution (QKD)**.

### Advantages

- Detects eavesdropping
- High theoretical security

### Limitations

- Specialized hardware
- Limited deployment
- High cost

---

# Post-Quantum Cryptography (PQC)

## Overview

Future quantum computers may break many current public-key algorithms such as RSA and ECC.

Post-Quantum Cryptography focuses on developing algorithms resistant to attacks from both classical and quantum computers.

### Goals

- Maintain confidentiality
- Secure digital signatures
- Replace vulnerable public-key systems
- Ensure long-term cryptographic security

Research and standardization are ongoing.

---

# Common Cryptographic Mistakes

Organizations should avoid:

- Weak passwords
- Reusing encryption keys
- Hardcoded secrets
- Expired certificates
- Outdated algorithms
- Weak random number generation
- Missing certificate validation
- Storing plaintext credentials
- Poor key rotation

---

# Blue Team Responsibilities

Security teams should:

- Monitor certificate expiration
- Detect weak cipher suites
- Audit encryption configurations
- Monitor HSM and KMS activity
- Validate TLS versions
- Detect unauthorized key access
- Review certificate revocation status
- Ensure secure backups
- Investigate cryptographic alerts

---

# CEH Exam Revision

Remember:

- AES is the recommended symmetric encryption algorithm.
- RSA and ECC provide asymmetric encryption.
- Diffie-Hellman performs secure key exchange.
- SHA-256 provides secure hashing.
- Digital signatures ensure integrity, authentication, and non-repudiation.
- PKI manages digital certificates.
- TLS replaces SSL.
- HSM securely stores cryptographic keys.
- TPM secures hardware-based keys.
- Perfect Forward Secrecy protects past communication sessions.
- Post-Quantum Cryptography addresses future quantum threats.

---

# Module Summary

Cryptography is one of the most important domains in cybersecurity. It protects sensitive information through encryption, hashing, digital signatures, certificates, and secure communication protocols.

A strong cryptographic implementation requires:

- Secure algorithms
- Proper key management
- Trusted certificate infrastructure
- Current TLS configurations
- Continuous monitoring
- Secure hardware
- Regular updates and audits

Understanding cryptography enables cybersecurity professionals to secure systems, evaluate implementations, identify weaknesses, and defend modern enterprise environments.

---

# Key Takeaways

- Cryptography protects confidentiality, integrity, authentication, and non-repudiation.
- Strong algorithms alone are insufficient without proper key management and secure implementation.
- Organizations should adopt modern encryption standards, maintain secure PKI, enforce TLS 1.2/1.3, protect cryptographic keys, and prepare for future advances such as post-quantum cryptography.





