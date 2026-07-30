# CSE403 – Network Security and Cryptography
> **Course:** CSE403 – Network Security and Cryptography
> **Reference:** William Stallings (6th Edition)
> **Goal:** Build conceptual understanding of cryptography and network security with technical notes, diagrams, and implementations.

# Session 1 – Introduction to Cryptography and Network Security

## Learning Objectives

After completing this session, you should understand:

- Fundamentals of Network Security
- Cryptography fundamentals
- Security Goals
- Security Services
- Security Mechanisms
- Threats, Vulnerabilities, Risks, and Attacks
- Communication Security Model

---

# 1. Network Security

## Definition

Network Security is the implementation of security policies, protocols, cryptographic algorithms, and defensive mechanisms to protect network resources and transmitted information against unauthorized disclosure, modification, destruction, or disruption.

## Objectives

- Confidentiality
- Integrity
- Availability
- Authentication
- Non-Repudiation
- Accountability

---

# 2. Cryptography

## Definition

Cryptography is the science of securing information using mathematical algorithms and cryptographic keys over an insecure communication channel.

Cryptography is a subset of Information Security and forms the foundation of modern secure communication.

---

## Basic Communication Model

-
               Shared / Public Key

Sender
   │
Plaintext
   │
Encryption Algorithm
   │
Ciphertext
   │
──────── Internet ────────
   │
Decryption Algorithm
   │
Plaintext
   │
Receiver
```



# Core Components

| Component | Description |
|-----------|-------------|
| Plaintext | Original readable message |
| Ciphertext | Encrypted unreadable message |
| Encryption | Converts plaintext into ciphertext |
| Decryption | Recovers plaintext |
| Key | Secret/Public value controlling encryption |

---

# 3. Security Goals

## Confidentiality

Ensures information is accessible only to authorized entities.

### Mechanisms

- AES
- DES
- RSA (Key Exchange)
- TLS

### Possible Attacks

- Packet Sniffing
- Eavesdropping
- Man-in-the-Middle

---

## Integrity

Ensures data remains unchanged during storage and transmission.

### Mechanisms

- SHA-256
- SHA-512
- HMAC
- Digital Signatures

### Possible Attacks

- Data Tampering
- Replay Attack

---

## Availability

Ensures services remain accessible to legitimate users.

### Threats

- DoS
- DDoS
- Hardware Failure
- Ransomware

---

## Authentication

Verifies the identity of communicating entities.

### Mechanisms

- Password
- OTP
- Kerberos
- X.509 Certificate

---

## Non-Repudiation

Prevents an entity from denying previously performed actions.

### Mechanisms

- RSA Digital Signature
- ElGamal Signature
- Schnorr Signature

---

# 4. Security Terminology

## Asset

Anything valuable that requires protection.

Examples

- Database
- Credentials
- Server
- Source Code

---

## Threat

A potential event capable of exploiting a vulnerability.

Examples

- Malware
- Insider Threat
- Attacker
- Natural Disaster

---

## Vulnerability

A weakness in a system that can be exploited.

Examples

- Weak Password
- Buffer Overflow
- Misconfiguration
- Unpatched Software

---

## Attack

An attempt to exploit one or more vulnerabilities.

Examples

- SQL Injection
- Phishing
- Privilege Escalation
- Buffer Overflow Exploit

---

## Risk


RisK = Threat × Vulnerability × Impact
`

Higher threat and higher vulnerability generally result in higher security risk.

---

# 5. Security Service vs Security Mechanism

| Security Service | Security Mechanism |
|------------------|--------------------|
| Defines security objective | Implements the objective |
| Confidentiality | AES |
| Integrity | SHA-256 |
| Authentication | Kerberos |
| Non-Repudiation | Digital Signature |

---

# 6. Cryptographic Communication Model

``
                 Key (K)

Plaintext
     │
     ▼
Encryption
     │
     ▼
Ciphertext
     │
 Insecure Network
     │
     ▼
Decryption
     │
     ▼
Plaintext
```



7. Important Observations

- The communication channel is assumed to be **untrusted**.
- Security relies on **key secrecy**, not algorithm secrecy.
- Encryption provides confidentiality.
- Hash functions provide integrity verification.
- Authentication verifies identity.
- Digital Signatures provide authentication, integrity, and non-repudiation.



# 8. Keywords

- Cryptography
- Cryptanalysis
- Cryptology
- Plaintext
- Ciphertext
- Cipher
- Symmetric Cryptography
- Asymmetric Cryptography
- Key Space
- Entropy
- Attack Surface

---

# Summary

- Cryptography secures information using mathematical algorithms.
- Network Security protects communication over untrusted networks.
- Security Goals define *what* must be protected.
- Security Mechanisms define *how* protection is implemented.
- Modern security assumes attackers can observe the communication channel.

---

# Next Session

- Euclidean Algorithm
- Extended Euclidean Algorithm
- Modular Arithmetic
- Modular Inverse
- Mathematical Foundation of RSA
