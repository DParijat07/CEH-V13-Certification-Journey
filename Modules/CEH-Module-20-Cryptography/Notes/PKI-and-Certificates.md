# Public Key Infrastructure (PKI) and Digital Certificates

## Overview

Public Key Infrastructure (PKI) is a framework of hardware, software, policies, procedures, and trusted entities that enables secure communication through the use of public key cryptography.

PKI provides authentication, confidentiality, integrity, and non-repudiation by managing digital certificates and cryptographic keys.

PKI is the foundation of secure Internet communication, including HTTPS, VPNs, email encryption, digital signatures, and secure authentication.

---

# Why PKI is Needed

Without PKI:

- Public keys cannot be trusted.
- Attackers can impersonate legitimate systems.
- Secure communication becomes difficult.

PKI establishes trust by verifying identities and issuing digital certificates.

---

# Components of PKI

A complete PKI consists of:

- Certificate Authority (CA)
- Registration Authority (RA)
- Digital Certificates
- Public Keys
- Private Keys
- Certificate Repository
- Revocation Services
- Certificate Policies

---

# Public Key

The public key is openly shared.

It is used for:

- Encrypting data
- Verifying digital signatures

Anyone can possess the public key.

---

# Private Key

The private key is secret.

It is used for:

- Decrypting encrypted data
- Creating digital signatures

Private keys must never be shared.

---

# Certificate Authority (CA)

## Overview

A Certificate Authority is a trusted organization responsible for issuing and digitally signing certificates.

The CA verifies identities before issuing certificates.

---

## Responsibilities

- Verify identity
- Issue certificates
- Renew certificates
- Revoke certificates
- Publish revocation information

---

## Examples

- DigiCert
- GlobalSign
- Sectigo
- Let's Encrypt

---

# Registration Authority (RA)

## Overview

The Registration Authority performs identity verification on behalf of the CA.

The RA does not issue certificates.

---

## Responsibilities

- Validate applicant identity
- Process certificate requests
- Forward approved requests to the CA

---

# Digital Certificate

## Overview

A digital certificate binds an identity to a public key.

Certificates follow the **X.509** standard.

---

## Typical Certificate Fields

- Subject
- Issuer
- Public Key
- Serial Number
- Valid From
- Valid Until
- Signature Algorithm
- Digital Signature

---

# Certificate Chain of Trust

```
Root CA
     ↓
Intermediate CA
     ↓
Server Certificate
```

Trust begins at the trusted Root CA and extends through intermediate certificates to the end-entity certificate.

---

# Certificate Signing Request (CSR)

## Overview

A CSR is generated before requesting a certificate.

It contains:

- Public key
- Domain name
- Organization information
- Country
- Organization Unit

The private key is **not** included in the CSR.

---

# Certificate Revocation

Certificates may become invalid before expiration.

Common reasons:

- Private key compromise
- Organization changes
- Employee departure
- Incorrect certificate issuance

---

# Certificate Revocation List (CRL)

## Overview

A CRL is a signed list of revoked certificates published by the CA.

Clients download the CRL to determine whether a certificate is still trusted.

---

## Advantages

- Simple implementation
- Offline verification possible

---

## Limitations

- Large file sizes
- Delayed updates
- Increased bandwidth usage

---

# Online Certificate Status Protocol (OCSP)

## Overview

OCSP provides real-time certificate status checking.

Instead of downloading an entire CRL, the client queries an OCSP responder.

---

## Advantages

- Real-time validation
- Faster responses
- Lower bandwidth usage

---

## Comparison

| CRL | OCSP |
|-----|------|
| Downloads full list | Queries individual certificate |
| Larger bandwidth | Smaller bandwidth |
| Periodic updates | Real-time validation |

---

# Digital Signatures

## Overview

Digital signatures verify:

- Integrity
- Authentication
- Non-repudiation

Digital signatures use asymmetric cryptography.

---

## Signing Process

```
Message
     ↓
Hash Function
     ↓
Hash Value
     ↓
Encrypt with Private Key
     ↓
Digital Signature
```

---

## Verification Process

```
Message
     ↓
Hash Function
     ↓
Hash Value

Received Signature
     ↓
Decrypt using Public Key
     ↓
Compare Hash Values
```

Matching hashes confirm authenticity and integrity.

---

# SSL (Secure Sockets Layer)

SSL was the original protocol used to secure Internet communications.

Modern SSL versions are deprecated because of known vulnerabilities.

---

# TLS (Transport Layer Security)

TLS replaced SSL.

Current secure versions:

- TLS 1.2
- TLS 1.3

TLS provides:

- Confidentiality
- Integrity
- Authentication

---

# HTTPS

HTTPS is HTTP secured with TLS.

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
- Payment information
- Cookies
- Personal data

---

# Simplified TLS Handshake

1. Client connects.
2. Server sends certificate.
3. Client validates certificate.
4. Secure session key is established.
5. Encrypted communication begins.

---

# Certificate Validation

Clients validate certificates by checking:

- Trusted CA
- Validity period
- Domain name
- Digital signature
- Revocation status
- Certificate chain

If validation fails, browsers display security warnings.

---

# Code Signing

## Overview

Code signing verifies that software:

- Originates from a trusted publisher
- Has not been modified

Common uses:

- Operating system updates
- Applications
- Drivers
- Mobile apps

---

# Email Certificates

S/MIME certificates provide:

- Email encryption
- Digital signatures
- Sender authentication

---

# Common PKI Attacks

Attackers may target:

- Compromised private keys
- Rogue Certificate Authorities
- Expired certificates
- Weak certificate validation
- TLS downgrade attacks
- Certificate spoofing

---

# PKI Best Practices

Organizations should:

- Protect private keys with HSMs.
- Use strong key lengths.
- Rotate certificates before expiration.
- Monitor certificate expiration.
- Implement OCSP where possible.
- Use trusted Certificate Authorities.
- Disable deprecated SSL versions.
- Enable TLS 1.2 or TLS 1.3.

---

# CEH Exam Tips

Remember:

- PKI manages digital certificates.
- CA issues certificates.
- RA verifies identities.
- CSR requests a certificate.
- CRL lists revoked certificates.
- OCSP performs real-time certificate validation.
- Digital signatures provide authentication, integrity, and non-repudiation.
- TLS replaces SSL.
- HTTPS = HTTP + TLS.

---

# Key Takeaways

- Public Key Infrastructure establishes trust through digital certificates, trusted Certificate Authorities, and secure key management.
- Proper certificate validation, strong key protection, and modern TLS configurations are essential for secure communication across today's digital infrastructure.
