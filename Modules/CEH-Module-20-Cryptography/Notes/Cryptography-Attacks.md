# Cryptographic Attacks

## Overview

Cryptographic attacks target encryption algorithms, cryptographic protocols, keys, or implementations with the goal of compromising the confidentiality, integrity, or authenticity of protected data.

In practice, attackers often exploit weak implementations, poor key management, outdated algorithms, or human error rather than breaking strong encryption algorithms directly.

Understanding these attacks helps cybersecurity professionals secure systems, investigate incidents, and implement effective defensive controls.

---

# Password-Based Attacks

## Brute Force Attack

### Overview

A brute force attack attempts every possible password or cryptographic key until the correct one is found.

```
Password?
      ↓
123456
      ↓
admin123
      ↓
welcome1
      ↓
Correct Password
```

### Characteristics

- Guaranteed success if enough time is available
- Very resource intensive
- More effective against weak passwords and short keys

### Defensive Controls

- Long passwords
- Strong key lengths
- MFA
- Account lockout
- Rate limiting

---

## Dictionary Attack

### Overview

A dictionary attack uses a predefined list of commonly used passwords instead of trying every possible combination.

Examples:

- password
- admin
- qwerty
- welcome123

### Defensive Controls

- Strong password policies
- Password managers
- MFA
- Password complexity enforcement

---

# Hash-Based Attacks

## Rainbow Table Attack

### Overview

Rainbow tables contain precomputed hashes that allow attackers to quickly identify weak passwords.

```
Password
      ↓
Hash
      ↓
Rainbow Table Lookup
```

### Defensive Controls

- Salting
- bcrypt
- scrypt
- Argon2
- PBKDF2

---

## Birthday Attack

### Overview

A Birthday Attack exploits the probability of two different inputs producing the same hash value.

It primarily targets **hash functions**.

### Defensive Controls

- SHA-256
- SHA-3
- Collision-resistant hash algorithms

---

## Collision Attack

### Overview

A collision attack finds two different inputs that generate the same hash.

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
- Avoid MD5 and SHA-1

---

# Cryptanalysis

## Overview

Cryptanalysis attempts to defeat cryptographic systems without knowing the secret key by exploiting mathematical or implementation weaknesses.

---

## Known Plaintext Attack (KPA)

The attacker possesses:

- Plaintext
- Matching ciphertext

Objective:

Recover the encryption key or derive useful information.

---

## Chosen Plaintext Attack (CPA)

The attacker selects arbitrary plaintext and observes the resulting ciphertext.

Used to analyze encryption algorithms.

---

## Chosen Ciphertext Attack (CCA)

The attacker submits chosen ciphertexts for decryption and studies the responses.

Modern cryptographic systems are designed to resist CCA.

---

# Side-Channel Attacks

## Overview

Side-channel attacks exploit information leaked during cryptographic operations rather than weaknesses in the algorithm itself.

Examples include:

- Execution time
- Power consumption
- Electromagnetic emissions
- CPU cache behavior

### Defensive Controls

- Constant-time implementations
- Hardware protections
- HSMs
- Secure coding practices

---

# Padding Oracle Attack

## Overview

Padding Oracle attacks target improperly implemented block cipher encryption.

Attackers analyze server responses to padding errors to recover plaintext.

### Defensive Controls

- Authenticated encryption (AEAD)
- Proper error handling
- Updated TLS implementations

---

# Protocol-Based Attacks

## SSL Strip

### Overview

SSL Strip downgrades secure HTTPS traffic to insecure HTTP.

```
Victim
      ↓ HTTP
Attacker
      ↓ HTTPS
Server
```

### Defensive Controls

- HTTPS Everywhere
- HSTS
- Browser security features

---

## Heartbleed

### Overview

Heartbleed was a critical vulnerability in OpenSSL's TLS Heartbeat extension.

### Impact

Attackers could retrieve sensitive server memory, including:

- Private keys
- Session cookies
- Passwords
- User data

### Defensive Controls

- Patch OpenSSL
- Replace affected certificates
- Rotate compromised keys

---

## BEAST Attack

### Overview

BEAST exploited weaknesses in TLS 1.0 using block cipher vulnerabilities.

### Defensive Controls

- TLS 1.2
- TLS 1.3
- Modern cipher suites

---

## POODLE Attack

### Overview

POODLE exploited vulnerabilities in SSL 3.0.

### Defensive Controls

- Disable SSL 3.0
- Use TLS 1.2 or TLS 1.3

---

## Lucky13

### Overview

Lucky13 exploited timing differences in CBC-mode encryption.

### Defensive Controls

- Constant-time cryptographic implementations
- AEAD cipher suites
- Updated TLS versions

---

# Random Number Weaknesses

## Weak Random Number Generation

Cryptographic systems rely on randomness for:

- Encryption keys
- Session keys
- Initialization Vectors (IVs)
- Nonces

Weak randomness can make encryption predictable.

### Defensive Controls

- Cryptographically Secure Random Number Generators (CSPRNG)
- Hardware entropy sources
- Secure seeding

---

# Key Management Weaknesses

Poor key management often defeats strong encryption.

Common issues include:

- Hardcoded keys
- Shared administrator keys
- Weak storage
- Lack of rotation
- Unencrypted backups

### Defensive Controls

- Hardware Security Modules (HSM)
- Key Management Services (KMS)
- Regular key rotation
- Secure backup procedures
- Least Privilege

---

# Downgrade Attacks

Attackers force communication to use weaker cryptographic protocols.

Examples:

- SSL instead of TLS
- TLS 1.0 instead of TLS 1.3

### Defensive Controls

- Disable legacy protocols
- Enforce modern TLS versions
- Restrict weak cipher suites

---

# Common Cryptographic Weaknesses

Avoid:

- DES
- RC4
- MD5
- SHA-1
- Weak passwords
- Hardcoded secrets
- Expired certificates
- Missing certificate validation
- Weak key lengths

---

# Blue Team Detection

Security teams should monitor for:

- Repeated failed authentication attempts
- Certificate validation failures
- Expired certificates
- Weak cipher suite usage
- Deprecated TLS versions
- Unusual key access
- Excessive password hash cracking attempts
- Unexpected cryptographic library errors

---

# Best Practices

Organizations should:

- Use AES-256 for encryption.
- Use SHA-256 or SHA-3 for hashing.
- Implement MFA.
- Rotate cryptographic keys.
- Protect private keys with HSMs.
- Disable deprecated algorithms and protocols.
- Monitor certificate expiration.
- Keep cryptographic libraries up to date.

---

# CEH Exam Tips

Remember:

- Brute force tries every possibility.
- Dictionary attacks use common passwords.
- Rainbow tables target password hashes.
- Birthday attacks exploit hash collisions.
- Side-channel attacks exploit implementation weaknesses.
- Heartbleed affected OpenSSL.
- POODLE targeted SSL 3.0.
- BEAST targeted TLS 1.0.
- TLS replaces SSL.
- Strong key management is as important as strong encryption.

---

# Key Takeaways

- Strong cryptography depends on secure algorithms, correct implementation, robust key management, and current protocols.
- Most real-world cryptographic compromises result from weak passwords, poor key protection, outdated software, or implementation flaws rather than attacks against modern algorithms themselves.
