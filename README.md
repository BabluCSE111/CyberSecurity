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

# CSE403 – Cryptography and Network Security
## Module 1: Mathematical Foundations of Cryptography
### Sessions 2 & 3

---

# Learning Objectives

After completing these sessions, you should be able to:

- Understand modular arithmetic.
- Perform modular addition, subtraction, and multiplication.
- Compute the Greatest Common Divisor (GCD).
- Apply the Euclidean Algorithm.
- Understand the Extended Euclidean Algorithm (EEA).
- Find a Modular Multiplicative Inverse (MMI).
- Explain why these concepts are important in RSA cryptography.

---

# 1. Modular Arithmetic

## Definition

Modular arithmetic is a system where numbers wrap around after reaching a fixed value.

It is also called **clock arithmetic**.

Mathematically,

```
a mod n = remainder when a is divided by n
```

### Examples

| Expression | Answer |
|------------|--------|
| 17 mod 5 | 2 |
| 23 mod 7 | 2 |
| 100 mod 9 | 1 |

---

# 2. Modular Operations

## Modular Addition

```
(a + b) mod n
```

Example

```
(15 + 28) mod 9
= 43 mod 9
= 7
```

---

## Modular Subtraction

```
(a - b) mod n
```

Example

```
(20 - 8) mod 7

=12 mod7

=5
```

---

## Modular Multiplication

```
(a × b) mod n
```

Example

```
(11 × 8) mod 7

=88 mod7

=4
```

---

# 3. Greatest Common Divisor (GCD)

## Definition

The GCD is the largest positive integer that divides both numbers exactly.

### Examples

| Numbers | GCD |
|----------|-----|
| 12,18 | 6 |
| 15,25 | 5 |
| 35,64 | 1 |

If GCD = 1, the numbers are called **coprime**.

---

# 4. Euclidean Algorithm

## Definition

The Euclidean Algorithm is an efficient method to compute the GCD.

### Algorithm

1. Divide the larger number by the smaller number.
2. Replace the larger number with the remainder.
3. Repeat until the remainder becomes 0.
4. The last non-zero remainder is the GCD.

### Example

Find GCD(48,18)

```
48 = 18 × 2 + 12

18 = 12 × 1 + 6

12 = 6 × 2 + 0
```

```
GCD = 6
```

---

# Difference Between GCD and Euclidean Algorithm

| GCD | Euclidean Algorithm |
|------|----------------------|
| Final answer | Method used to find the answer |
| A number | A procedure |
| Example: GCD = 6 | Example: Repeated division steps |

Easy to remember:

```
GCD = Destination

Euclidean Algorithm = Route
```

---

# 5. Extended Euclidean Algorithm (EEA)

## Definition

The Extended Euclidean Algorithm finds

- GCD
- x
- y

such that

```
ax + by = gcd(a,b)
```

This equation is called **Bézout's Identity**.

---

# Difference Between EA and EEA

| Euclidean Algorithm | Extended Euclidean Algorithm |
|----------------------|------------------------------|
| Finds GCD only | Finds GCD and x,y coefficients |
| Used for GCD | Used for Modular Inverse |

---

# 6. Modular Multiplicative Inverse (MMI)

## Definition

A number x is called the modular inverse of a modulo n if

```
a × x ≡ 1 (mod n)
```

### Example

Find inverse of 3 mod 11.

```
3 × 4 = 12

12 mod11 =1
```

Therefore,

```
Inverse of 3 mod11 =4
```

---

# Condition for Modular Inverse

A modular inverse exists only when

```
gcd(a,n)=1
```

Examples

| Number | Inverse Exists? |
|---------|-----------------|
| 8 mod15 | Yes |
| 6 mod9 | No |

---

# Example Using Extended Euclidean Algorithm

Find inverse of 7 mod26.

Step 1

```
26 =7×3+5

7 =5×1+2

5 =2×2+1

2 =1×2+0
```

GCD =1

Step 2 (Back Substitution)

```
1 =5−2×2

2 =7−5

1 =5−(7−5)×2

1 =3×5−2×7

5 =26−3×7

1 =3×26−11×7
```

Therefore

```
x =−11
```

Convert to positive modulo

```
−11 mod26 =15
```

Hence,

```
Inverse of7 mod26 =15
```

Verification

```
7×15 =105

105 mod26 =1
```

---

# Why RSA Uses the Extended Euclidean Algorithm

RSA requires computing the private key d such that

```
d × e ≡ 1 (mod φ(n))
```

The Extended Euclidean Algorithm is used to calculate d.

---

# Concept Flow

```
Modular Arithmetic

↓

Euclidean Algorithm

↓

Find GCD

↓

Check GCD =1

↓

Numbers are Coprime

↓

Extended Euclidean Algorithm

↓

Modular Multiplicative Inverse

↓

RSA Private Key
```

---

# Important Exam Notes

- Modular arithmetic is also called clock arithmetic.
- GCD is the largest common divisor.
- Euclidean Algorithm finds the GCD.
- Extended Euclidean Algorithm finds the GCD and Bézout coefficients.
- Modular inverse exists only if GCD = 1.
- RSA uses the Extended Euclidean Algorithm to compute the private key.

---

# Practice Questions

1. Compute 37 mod 6.
2. Compute (15 + 28) mod 9.
3. Compute (11 × 8) mod 7.
4. Find GCD(81,27).
5. Find GCD(35,64).
6. Does inverse of 8 mod15 exist?
7. Find inverse of 5 mod17.
8. Why does inverse of 6 mod9 not exist?
9. Differentiate between GCD and Euclidean Algorithm.
10. Differentiate between Euclidean Algorithm and Extended Euclidean Algorithm.

---

# Session Summary

✔ Modular Arithmetic

✔ Modular Operations

✔ Greatest Common Divisor (GCD)

✔ Euclidean Algorithm

✔ Extended Euclidean Algorithm

✔ Bézout's Identity

✔ Modular Multiplicative Inverse

✔ RSA Application
# CSE403 – Session Notes

## Topic: Security Services, Security Mechanisms, Threats, Vulnerabilities, Risks & Attacks

---

# 1. Security Service

**Definition:**
A Security Service is the **goal** we want to achieve to protect information and systems.

### Types of Security Services

### Confidentiality

* Prevents unauthorized access to data.
* Goal: Only authorized users can read the information.
* Example: Online banking data protected by encryption.

### Integrity

* Prevents unauthorized modification of data.
* Goal: Data remains accurate and unchanged.
* Example: Transaction amount should not be altered.

### Authentication

* Verifies the identity of a user or system.
* Goal: Ensure the user is genuine.
* Example: Username + Password + OTP.

### Availability

* Ensures services and data are available when needed.
* Goal: Users can access the system anytime.
* Example: Banking server should remain online.

---

# 2. Security Mechanism

**Definition:**
A Security Mechanism is the **tool or technique** used to provide a Security Service.

### Examples

| Security Service | Security Mechanism                       |
| ---------------- | ---------------------------------------- |
| Confidentiality  | Encryption                               |
| Integrity        | Hashing, Digital Signature               |
| Authentication   | Password, OTP, Biometrics                |
| Availability     | Backup Server, Redundancy, Load Balancer |

---

# Difference

**Security Service = What we want (Goal)**

**Security Mechanism = How we achieve it (Tool)**

---

# 3. Vulnerability

**Definition:**
A Vulnerability is a weakness or security flaw that can be exploited.

### Examples

* Weak password
* No antivirus
* Outdated software
* Open network port
* No lock on a library door

---

# 4. Threat

**Definition:**
A Threat is any person, event, or software capable of exploiting a vulnerability and causing harm.

### Examples

* Hacker
* Virus
* Ransomware
* Insider
* Fire
* Flood

---

# 5. Attack

**Definition:**
An Attack is the actual attempt to exploit a vulnerability.

### Examples

* Password cracking
* Malware infection
* Data theft
* SQL Injection
* Phishing

---

# 6. Risk

**Definition:**
Risk is the possibility of loss or damage if a threat successfully exploits a vulnerability.

### Examples

* Financial loss
* Data loss
* Reputation damage
* Service disruption

---

# Library Analogy

No Lock
↓
**Vulnerability**

Unauthorized Person
↓
**Threat**

Steals Books
↓
**Attack**

Books Missing
↓
**Risk**

---

# Memory Trick

* **Vulnerability = Weakness**
* **Threat = Danger**
* **Attack = Action**
* **Risk = Loss / Damage**

---

# Key Takeaway

**Security Service = Goal**

**Security Mechanism = Tool**

**Weakness + Threat → Attack → Risk**
# CSE403 – Cryptography and Network Security
## Module 1: Classical Ciphers

---

# Learning Objectives

After completing this section, you should be able to:

- Understand different classical ciphers.
- Perform encryption and decryption.
- Understand substitution and transposition concepts.
- Apply mathematical formulas in classical ciphers.
- Identify the cipher from its working method.

---

# 1. Caesar / Additive Cipher

## Definition

Caesar Cipher shifts each plaintext letter by a fixed key.

### Encryption

```text
C = (P + k) mod 26
```

### Decryption

```text
P = (C - k) mod 26
```

### Key Idea

```text
Fixed Shift
```

---

# 2. Multiplicative Cipher

## Definition

Each plaintext value is multiplied by a key.

### Encryption

```text
C = (P × k) mod 26
```

### Condition

```text
gcd(k,26) = 1
```

The key must have a modular inverse.

### Decryption

```text
P = (C × k⁻¹) mod 26
```

### Key Idea

```text
Multiplication
```

---

# 3. Affine Cipher

## Definition

Affine Cipher combines multiplication and addition.

### Encryption

```text
C = (aP + b) mod 26
```

### Condition

```text
gcd(a,26) = 1
```

### Decryption

```text
P = a⁻¹(C - b) mod 26
```

### Key Idea

```text
Multiply + Add
```

---

# 4. Monoalphabetic Cipher

## Definition

Uses one fixed substitution alphabet.

### Example

```text
Plain :  ABCDEFGHIJKLMNOPQRSTUVWXYZ
Cipher:  QWERTYUIOPASDFGHJKLZXCVBNM
```

### Key Idea

```text
One Fixed Substitution
```

### Weakness

```text
Frequency Analysis
```

---

# 5. Polyalphabetic / Vigenère Cipher

## Definition

Uses multiple substitution alphabets controlled by a key.

### Encryption

```text
Cᵢ = (Pᵢ + Kᵢ) mod 26
```

### Example

```text
Plaintext : ATTACKATDAWN
Key       : LEMONLEMONLE
```

### Key Idea

```text
Multiple Alphabets
+
Repeating Key
```

### Important

The same plaintext letter can produce different ciphertext letters.

---

# 6. Playfair Cipher

## Definition

Encrypts two letters at a time using a 5×5 matrix.

### Rules

### Same Row

```text
Move Right →
```

### Same Column

```text
Move Down ↓
```

### Rectangle

```text
Swap Columns
```

### Key Idea

```text
Letter Pairs + 5×5 Matrix
```

---

# 7. Hill Cipher

## Definition

Uses matrix multiplication for encryption.

### Letter Mapping

```text
A=0, B=1, ..., Z=25
```

### Encryption

```text
C = KP mod 26
```

### Decryption

```text
P = K⁻¹C mod 26
```

### Key Idea

```text
Matrix Multiplication
```

### Important

The key matrix must have a valid modular inverse.

---

# 8. One-Time Pad (OTP)

## Definition

Uses a truly random key.

### Conditions

- Key length = Plaintext length
- Key used only once
- Key must be random

### Encryption

```text
C = P ⊕ K
```

or

```text
C = (P + K) mod 26
```

### Key Idea

```text
Random Key
+
Same Length
+
Used Once
```

### Security

```text
Perfect Secrecy
```

---

# 9. Autokey Cipher

## Definition

Uses a keyword and extends the key using plaintext.

### Encryption

```text
Cᵢ = (Pᵢ + Kᵢ) mod 26
```

### Key Idea

```text
Keyword + Plaintext
```

### Difference from Vigenère

```text
Vigenère → Repeating Key
Autokey  → Key + Plaintext
```

---

# Cipher Comparison

| Cipher | Main Method |
|----------|-------------|
| Caesar | Fixed Shift |
| Multiplicative | Multiplication |
| Affine | Multiplication + Addition |
| Monoalphabetic | Fixed Substitution |
| Vigenère | Multiple Alphabets |
| Playfair | Letter Pairs |
| Hill | Matrix Multiplication |
| OTP | Random One-Time Key |
| Autokey | Keyword + Plaintext |

---

# Important Exam Notes

- Caesar uses a fixed shift.
- Multiplicative uses modular multiplication.
- Affine combines multiplication and addition.
- Monoalphabetic uses one substitution alphabet.
- Polyalphabetic uses multiple substitution alphabets.
- Playfair encrypts pairs of letters.
- Hill cipher uses matrix multiplication.
- OTP uses a random key equal to plaintext length and uses it only once.
- Autokey extends the key using plaintext.

---

# Concept Flow

```text
Classical Ciphers
       ↓
Caesar
       ↓
Multiplicative
       ↓
Affine
       ↓
Monoalphabetic
       ↓
Polyalphabetic
       ↓
Playfair
       ↓
Hill
       ↓
OTP
       ↓
Autokey
```

---

# Session Summary

✔ Caesar / Additive Cipher

✔ Multiplicative Cipher

✔ Affine Cipher

✔ Monoalphabetic Cipher

✔ Polyalphabetic / Vigenère Cipher

✔ Playfair Cipher

✔ Hill Cipher

✔ One-Time Pad (OTP)

✔ Autokey Cipher
