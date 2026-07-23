# Encryption Algorithms

## Overview

Encryption algorithms convert plaintext into ciphertext using mathematical operations and cryptographic keys. Modern cryptography primarily uses two categories of encryption:

- Symmetric Encryption
- Asymmetric Encryption

Each serves different purposes and is often combined to provide both performance and security.

---

# Symmetric Encryption

## Overview

Symmetric encryption uses a **single shared secret key** for both encryption and decryption.

```
Plaintext
      ↓
Encryption
      ↓
Secret Key
      ↓
Ciphertext
      ↓
Secret Key
      ↓
Decryption
      ↓
Plaintext
```

Both communicating parties must securely share the same key.

---

## Advantages

- Very fast
- Efficient for large data
- Low CPU usage
- Suitable for storage encryption

---

## Disadvantages

- Secure key distribution is difficult
- Poor scalability
- Compromise of the key compromises all protected data

---

## Common Uses

- Full disk encryption
- Database encryption
- VPN tunnels
- Cloud storage
- File encryption

---

# Asymmetric Encryption

## Overview

Asymmetric encryption uses a **key pair**:

- Public Key
- Private Key

```
Public Key
      ↓
Encryption
      ↓
Ciphertext
      ↓
Private Key
      ↓
Decryption
```

The public key is shared openly, while the private key must remain secret.

---

## Advantages

- Secure key exchange
- Authentication
- Digital signatures
- Better scalability

---

## Disadvantages

- Slower than symmetric encryption
- Higher computational cost
- Not suitable for encrypting large files directly

---

## Common Uses

- HTTPS
- TLS
- SSH
- Email encryption
- Digital certificates

---

# Block Cipher

A block cipher encrypts fixed-size blocks of plaintext.

Examples:

- AES
- DES
- 3DES
- Blowfish
- Twofish

### Advantages

- Strong security
- Efficient for large files
- Widely supported

---

# Stream Cipher

A stream cipher encrypts data one bit or one byte at a time.

Examples:

- RC4 (legacy)
- ChaCha20 (modern)

### Advantages

- Low latency
- Efficient for real-time communication

---

# Data Encryption Standard (DES)

## Overview

DES was standardized in 1977 and was one of the first widely adopted encryption algorithms.

### Specifications

- Type: Symmetric Block Cipher
- Block Size: 64 bits
- Key Size: 56 bits

---

## Advantages

- Historically important
- Simple design

---

## Limitations

- Small key size
- Vulnerable to brute-force attacks
- Deprecated

DES should not be used in modern environments.

---

# Triple DES (3DES)

## Overview

3DES improves DES by applying DES encryption three times.

### Advantages

- More secure than DES
- Backward compatibility with DES

---

## Limitations

- Slower than AES
- Being phased out
- Not recommended for new deployments

---

# Advanced Encryption Standard (AES)

## Overview

AES is the current industry-standard symmetric encryption algorithm.

### Specifications

- Type: Symmetric Block Cipher
- Block Size: 128 bits
- Key Sizes:
  - 128-bit
  - 192-bit
  - 256-bit

---

## Advantages

- High performance
- Strong security
- Resistant to practical attacks
- Government-approved

---

## Common Applications

- HTTPS
- VPNs
- WPA2/WPA3 Wi-Fi
- Cloud encryption
- BitLocker
- FileVault

AES is the preferred encryption algorithm for modern systems.

---

# Blowfish

## Overview

Blowfish is a symmetric block cipher designed by Bruce Schneier.

### Features

- Variable key length
- Fast encryption
- Free for public use

---

## Applications

- Password managers
- File encryption
- Embedded systems

---

# Twofish

## Overview

Twofish is the successor to Blowfish and was a finalist in the AES competition.

### Features

- Block Size: 128 bits
- Key Sizes: Up to 256 bits
- High security
- Flexible implementation

Although highly secure, AES became the official standard.

---

# RC4

## Overview

RC4 is a stream cipher formerly used in SSL and WEP.

### Limitations

- Keystream bias
- Practical attacks
- Deprecated

Modern systems should not use RC4.

---

# RSA

## Overview

RSA is the most widely used public-key encryption algorithm.

### Features

- Public/Private key pair
- Based on integer factorization
- Supports encryption and digital signatures

---

## Common Uses

- TLS
- Digital certificates
- Secure email
- PKI

---

## Advantages

- Strong authentication
- Mature ecosystem
- Broad compatibility

---

## Limitations

- Slower than symmetric algorithms
- Larger key sizes required

---

# Elliptic Curve Cryptography (ECC)

## Overview

ECC provides equivalent security to RSA while using much smaller keys.

### Advantages

- Faster operations
- Lower bandwidth
- Lower memory usage
- Ideal for mobile and IoT devices

---

## Common Uses

- TLS
- Mobile security
- Cryptocurrencies
- Smart cards

---

# Diffie-Hellman Key Exchange

## Overview

Diffie-Hellman allows two parties to establish a shared secret over an insecure channel.

### Important Note

Diffie-Hellman is a **key exchange protocol**, not an encryption algorithm.

---

## Applications

- TLS
- SSH
- VPNs
- Secure messaging

---

# Hybrid Encryption

Modern secure communication combines asymmetric and symmetric encryption.

Example workflow:

```
RSA / ECC
      ↓
Exchange AES Session Key
      ↓
AES Encrypts Data
```

### Benefits

- Secure key exchange
- Fast encryption
- Efficient communication

Hybrid encryption is used in:

- HTTPS
- TLS
- SSH
- VPNs

---

# Algorithm Comparison

| Algorithm | Type | Status | Common Use |
|-----------|------|--------|------------|
| DES | Symmetric | Deprecated | Legacy systems |
| 3DES | Symmetric | Legacy | Backward compatibility |
| AES | Symmetric | Recommended | General encryption |
| Blowfish | Symmetric | Secure | File encryption |
| Twofish | Symmetric | Secure | Specialized applications |
| RC4 | Stream | Deprecated | Legacy protocols |
| RSA | Asymmetric | Recommended | PKI, TLS |
| ECC | Asymmetric | Recommended | Mobile, IoT, TLS |
| Diffie-Hellman | Key Exchange | Recommended | Secure session establishment |

---

# Symmetric vs Asymmetric Encryption

| Feature | Symmetric | Asymmetric |
|----------|-----------|------------|
| Keys | One shared key | Public & Private keys |
| Speed | Fast | Slower |
| Performance | High | Moderate |
| Scalability | Lower | Higher |
| Primary Use | Data encryption | Key exchange, authentication |

---

# Best Practices

Organizations should:

- Use AES-256 for sensitive data.
- Use RSA (2048-bit+) or ECC for public-key operations.
- Disable DES, 3DES, and RC4 where possible.
- Use hybrid encryption for secure communications.
- Rotate cryptographic keys regularly.
- Protect private keys with HSMs or secure key management systems.

---

# CEH Exam Tips

Remember:

- AES is the recommended symmetric encryption standard.
- DES is obsolete due to its short key length.
- 3DES is stronger than DES but slower than AES.
- RC4 is deprecated.
- RSA uses a public/private key pair.
- ECC provides similar security with smaller keys.
- Diffie-Hellman is used for key exchange.
- HTTPS and TLS rely on hybrid encryption.

---

# Key Takeaways

- Symmetric encryption offers high performance for protecting large volumes of data, while asymmetric encryption enables secure key exchange, authentication, and digital signatures.
- Modern secure communication relies on hybrid encryption, combining the strengths of both approaches to achieve confidentiality, integrity, and scalability.
