# Cryptography Fundamentals

## Overview

Cryptography is the science of protecting information by transforming readable data into an unreadable format using mathematical algorithms and cryptographic keys. It enables secure communication over untrusted networks and protects sensitive information from unauthorized access.

Cryptography is a foundational component of cybersecurity and is widely used in secure web browsing, online banking, VPNs, cloud computing, wireless security, email protection, and digital identity systems.

---

# What is Cryptography?

Cryptography is the practice of securing information using mathematical techniques that provide:

- Confidentiality
- Integrity
- Authentication
- Non-Repudiation

It ensures that even if attackers intercept the data, they cannot understand or modify it without the appropriate cryptographic keys.

---

# Objectives of Cryptography

Modern cryptography provides four primary security services.

## Confidentiality

Ensures that information is accessible only to authorized users.

Examples:

- AES Encryption
- VPN tunnels
- HTTPS

---

## Integrity

Ensures that information has not been modified without authorization.

Technologies include:

- SHA-256
- HMAC
- Digital Signatures

---

## Authentication

Verifies the identity of users, systems, or services.

Examples:

- Passwords
- Digital Certificates
- Multi-Factor Authentication (MFA)

---

## Non-Repudiation

Prevents a sender from denying that they transmitted a message.

Achieved through:

- Digital Signatures
- Public Key Infrastructure (PKI)

---

# CIA Triad and Cryptography

Cryptography supports the CIA Triad.

| Principle | Cryptographic Support |
|-----------|-----------------------|
| Confidentiality | Encryption |
| Integrity | Hashing, HMAC, Digital Signatures |
| Availability | Indirect support through secure implementation |

---

# Basic Terminology

## Plaintext

Original readable information before encryption.

Example:

```
Hello World
```

---

## Ciphertext

Encrypted information that cannot be understood without the correct decryption key.

Example:

```
A84F91C7D23B...
```

---

## Encryption

The process of converting plaintext into ciphertext using an encryption algorithm and key.

---

## Decryption

The process of converting ciphertext back into plaintext using the appropriate key.

---

## Cipher

A mathematical algorithm used to encrypt and decrypt data.

Examples:

- AES
- RSA
- DES
- Blowfish

---

## Cryptographic Key

A secret value used by cryptographic algorithms during encryption and decryption.

The security of encrypted data largely depends on protecting the key.

---

# Encryption Lifecycle

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

Major milestones include:

- Caesar Cipher
- Vigenère Cipher
- Enigma Machine
- DES
- RSA
- AES
- Elliptic Curve Cryptography (ECC)

Modern cryptography relies on mathematical complexity rather than simple substitution techniques.

---

# Classical Cryptography

Classical cryptography relied on manual encryption methods.

Examples:

- Caesar Cipher
- Playfair Cipher
- Vigenère Cipher
- Rail Fence Cipher

These methods are now considered insecure.

---

# Modern Cryptography

Modern cryptography uses advanced mathematical algorithms and secure key management.

Characteristics include:

- Large key sizes
- Computational security
- Public-key cryptography
- Digital signatures
- Secure hashing
- Key exchange protocols

---

# Types of Cryptography

Modern cryptography consists of three primary categories.

## Symmetric Cryptography

Uses a single shared secret key.

Examples:

- AES
- DES
- Blowfish

Advantages:

- Fast
- Efficient
- Suitable for large amounts of data

---

## Asymmetric Cryptography

Uses a public key and a private key.

Examples:

- RSA
- ECC
- ElGamal

Advantages:

- Secure key exchange
- Digital signatures
- Authentication

---

## Hash Functions

Generate a fixed-length hash value from input data.

Examples:

- SHA-256
- SHA-512
- SHA-3

Used for:

- Integrity verification
- Password storage
- Digital signatures

---

# Encryption vs Encoding vs Hashing

| Feature | Encryption | Encoding | Hashing |
|----------|------------|----------|---------|
| Reversible | Yes | Yes | No |
| Uses Key | Yes | No | No |
| Security Purpose | Yes | No | Integrity |
| Example | AES | Base64 | SHA-256 |

---

# Common Cryptographic Algorithms

## Symmetric

- AES
- DES
- 3DES
- Blowfish
- Twofish

---

## Asymmetric

- RSA
- ECC
- Diffie-Hellman (Key Exchange)

---

## Hashing

- SHA-256
- SHA-512
- SHA-3

---

# Real-World Applications

Cryptography protects:

- HTTPS websites
- VPNs
- Wi-Fi networks
- Cloud storage
- Banking transactions
- Email communication
- Mobile applications
- Blockchain systems
- Password databases
- Software updates

---

# Common Security Mistakes

Organizations should avoid:

- Weak passwords
- Outdated algorithms
- Hardcoded keys
- Unencrypted storage
- Weak key management
- Expired certificates
- Missing MFA

---

# Best Practices

Use:

- AES-256 for encryption
- SHA-256 or SHA-3 for hashing
- TLS 1.2 or TLS 1.3
- RSA (2048-bit or higher) or ECC
- Strong key management
- Multi-Factor Authentication
- Secure certificate management

---

# CEH Exam Tips

Remember:

- Encryption protects confidentiality.
- Hashing protects integrity.
- Digital signatures provide authentication and non-repudiation.
- AES is the recommended symmetric encryption algorithm.
- RSA and ECC are common asymmetric algorithms.
- TLS replaces SSL.
- Encoding is not encryption.

---

# Key Takeaways

- Cryptography is essential for protecting digital information through encryption, hashing, authentication, and secure key management.
- Modern cybersecurity relies on strong cryptographic algorithms, secure implementation, and proper operational practices to ensure confidentiality, integrity, authentication, and non-repudiation.
