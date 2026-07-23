# Module 20 – Interview Questions

## Cryptography Fundamentals

### Beginner Level

**Q1. What is cryptography?**  
Cryptography is the science of protecting information using mathematical algorithms to ensure confidentiality, integrity, authentication, and non-repudiation.

---

**Q2. What are the four primary goals of cryptography?**

- Confidentiality
- Integrity
- Authentication
- Non-Repudiation

---

**Q3. What is plaintext?**

Readable, original data before encryption.

---

**Q4. What is ciphertext?**

Encrypted data that cannot be understood without the correct decryption key.

---

**Q5. What is the difference between encryption and decryption?**

- Encryption converts plaintext into ciphertext.
- Decryption converts ciphertext back into plaintext.

---

**Q6. What is a cryptographic key?**

A secret value used by cryptographic algorithms to encrypt or decrypt data.

---

**Q7. What is a cipher?**

A mathematical algorithm used for encryption and decryption.

---

**Q8. What is the difference between encryption, encoding, and hashing?**

- Encryption protects confidentiality and is reversible with a key.
- Encoding changes data format and is reversible without a key.
- Hashing creates a one-way digest for integrity verification.

---

## Symmetric & Asymmetric Encryption

**Q9. What is symmetric encryption?**

Uses one shared secret key for both encryption and decryption.

---

**Q10. What is asymmetric encryption?**

Uses a public key and a private key.

---

**Q11. Give examples of symmetric algorithms.**

- AES
- DES
- 3DES
- Blowfish
- Twofish

---

**Q12. Give examples of asymmetric algorithms.**

- RSA
- ECC
- ElGamal

---

**Q13. What is AES?**

Advanced Encryption Standard (AES) is the current industry-standard symmetric block cipher.

---

**Q14. Why is AES preferred over DES?**

- Larger key sizes
- Better security
- Faster performance
- Resistant to brute-force attacks

---

**Q15. Why is DES considered insecure?**

DES uses a 56-bit key, making it vulnerable to brute-force attacks.

---

**Q16. What is 3DES?**

Triple DES applies the DES algorithm three times to improve security.

---

**Q17. Why is RC4 deprecated?**

Due to significant cryptographic weaknesses and keystream biases.

---

**Q18. What is RSA commonly used for?**

- Key exchange
- Digital signatures
- PKI
- Secure communication

---

**Q19. What are the advantages of ECC over RSA?**

- Smaller keys
- Faster computation
- Lower bandwidth
- Better performance on mobile devices

---

**Q20. What is Diffie-Hellman used for?**

Secure key exchange.

---

## Hashing

**Q21. What is hashing?**

A one-way mathematical function that produces a fixed-length output from input data.

---

**Q22. Can hashes be decrypted?**

No.

---

**Q23. What are common hashing algorithms?**

- SHA-256
- SHA-512
- SHA-3

---

**Q24. Why are MD5 and SHA-1 deprecated?**

They are vulnerable to collision attacks.

---

**Q25. What is HMAC?**

Hash-Based Message Authentication Code combines a secret key with a hash function to provide integrity and authenticity.

---

## PKI & Certificates

**Q26. What is PKI?**

A framework that manages public keys and digital certificates.

---

**Q27. What is a Certificate Authority (CA)?**

A trusted entity that issues and signs digital certificates.

---

**Q28. What is a Registration Authority (RA)?**

An entity that verifies identities before the CA issues certificates.

---

**Q29. What is a digital certificate?**

A document that binds an identity to a public key.

---

**Q30. What is a CSR?**

A Certificate Signing Request sent to a CA when requesting a certificate.

---

**Q31. What is a CRL?**

A Certificate Revocation List containing revoked certificates.

---

**Q32. What is OCSP?**

Online Certificate Status Protocol used for real-time certificate validation.

---

**Q33. What is a digital signature?**

A cryptographic mechanism that provides integrity, authentication, and non-repudiation.

---

## SSL/TLS

**Q34. What is SSL?**

An older protocol for secure communication that has been deprecated.

---

**Q35. What is TLS?**

Transport Layer Security, the modern replacement for SSL.

---

**Q36. What is HTTPS?**

HTTP secured with TLS.

---

**Q37. What happens during a TLS handshake?**

- Certificate exchange
- Certificate validation
- Key exchange
- Secure session establishment

---

## Cryptographic Attacks

**Q38. What is a brute-force attack?**

Trying every possible password or key until the correct one is found.

---

**Q39. What is a dictionary attack?**

Using a list of common passwords to guess credentials.

---

**Q40. What is a rainbow table attack?**

Using precomputed hashes to crack passwords.

---

**Q41. What is salting?**

Adding random data before hashing to defeat rainbow table attacks.

---

**Q42. What is a birthday attack?**

An attack exploiting hash collision probabilities.

---

**Q43. What is a collision attack?**

Finding two different inputs that produce the same hash.

---

**Q44. What is Heartbleed?**

An OpenSSL vulnerability that allowed attackers to read sensitive server memory.

---

**Q45. What is POODLE?**

An attack targeting SSL 3.0.

---

**Q46. What is BEAST?**

An attack against TLS 1.0.

---

**Q47. What is SSL Strip?**

An attack that downgrades HTTPS connections to HTTP.

---

**Q48. What is a side-channel attack?**

An attack exploiting information leakage such as timing or power consumption.

---

## SOC & Blue Team

**Q49. What should SOC analysts monitor regarding cryptography?**

- Certificate expiration
- Weak cipher suites
- TLS versions
- Certificate revocations
- Key management events
- Ransomware activity

---

**Q50. What SIEM alerts are useful?**

- Expired certificates
- Weak TLS versions
- Deprecated ciphers
- Certificate installation
- Large encrypted outbound transfers

---

## Scenario-Based Questions

**Q51. A website still supports SSL 3.0. What is the risk?**

It is vulnerable to attacks such as POODLE.

---

**Q52. Why should organizations disable TLS 1.0?**

Because it is vulnerable to known attacks such as BEAST.

---

**Q53. Why is AES commonly paired with RSA in HTTPS?**

RSA securely exchanges the session key, while AES efficiently encrypts the data.

---

**Q54. A user reports a browser certificate warning. What should you verify first?**

- Certificate validity
- Issuer
- Domain name
- Expiration
- Revocation status

---

**Q55. Why should private keys be stored in an HSM?**

To provide tamper-resistant, hardware-based protection against key theft.

---

## Rapid-Fire Revision

**Q56. Best symmetric algorithm?**  
AES

**Q57. Best public-key algorithm for constrained devices?**  
ECC

**Q58. Best secure hash?**  
SHA-256 / SHA-3

**Q59. TLS replaced?**  
SSL

**Q60. HTTPS = ?**  
HTTP + TLS

**Q61. PKI manages?**  
Certificates and public keys

**Q62. CA does?**  
Issues certificates

**Q63. RA does?**  
Verifies identity

**Q64. Diffie-Hellman provides?**  
Secure key exchange

**Q65. Digital signatures provide?**  
Authentication, integrity, and non-repudiation

**Q66. Heartbleed affected?**  
OpenSSL

**Q67. POODLE targeted?**  
SSL 3.0

**Q68. BEAST targeted?**  
TLS 1.0

**Q69. Rainbow tables attack?**  
Password hashes

**Q70. Salting prevents?**  
Rainbow table attacks

---

# Final Revision Checklist

Before your CEH exam, ensure you can explain:

- Cryptography fundamentals
- CIA Triad
- Encryption vs Hashing vs Encoding
- Symmetric vs Asymmetric encryption
- AES, DES, RSA, ECC
- Hash functions (SHA family)
- Digital signatures
- PKI components
- Certificates
- TLS/HTTPS
- Cryptographic attacks
- Key management
- HSM & TPM
- Perfect Forward Secrecy (PFS)
- Post-Quantum Cryptography basics
- SOC monitoring and SIEM use cases

---

# Key Takeaways

- Cryptography is a core pillar of cybersecurity, enabling secure communication, identity verification, and data protection.
- Mastering encryption algorithms, hashing, PKI, TLS, and common cryptographic attacks is essential for CEH, SOC Analyst, Security Engineer, and Penetration Tester roles.
