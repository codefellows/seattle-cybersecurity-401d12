<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 09

NOTE:

This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 09 - Public Key Infrastructure (PKI)

- Course Overview <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - DLP and Data Classification
- Lecture
  - Public Key Infrastructure (PKI)
- Demo

---

<!-- .element class="split-screen-with-title" -->
## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- **Module 1** - Governance, Risk and Compliance (GRC)

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Module 2** - Data Security

- **Module 3** - Security Operations

- **Module 4** - Cloud Security

- **Module 5** - Midterm Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/00_01.png)
<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)

</div>

</div>

---
<!-- .element class="title-with-text" -->
## Module 2 Labs

### Data Security

<div align="left" style="font-size: 45px">

- **Class 06** - Data File Encryption and Hashing

<br>

- **Class 07** - Protecting Data at Rest

<br>

- **Class 08** - Data Loss Prevention (DLP) and Classification

<br>

- &shy;<!-- .element style="color: red;" -->**Class 09** - Public Key Infrastructure (PKI)

<br>

- **Class 10** - CCW 2: Personal Pitch

</div>

---

<!-- .element class="split-screen-with-title" -->
## Module 2 Challenges

<div>

<div align="left" style="font-size: 38px">

- **Class 06** - File Encryption Script Part 1 of 3

<br>

- **Class 07** - File Encryption Script Part 2 of 3

<br>

- **Class 08** - File Encryption Script Part 3 of 3

<br>

- &shy;<!-- .element style="color: red;" -->**Class 09** - Mock Interviews

<br>

- **Class 10** - Advanced Event Logging with Sysmon

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Ops Challenge

---

<!-- .element class="main-title" -->
# Review:

## Encryption & DLP

---

<!-- .element class="image-and-title" -->
# Encryption

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/05_02.png)

NOTE:

Data encryption uses a special program to scramble the data on your computer, and an encryption key to revert it to its prior, readable state. You can use it to reliably protect the files and folders on your computer in Windows 10.

---

<!-- .element class="image-and-title" -->
# Hashing

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/05_03.png)

---

<!-- .element class="split-screen-with-title" -->
# Encoding

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Encoding**
  - The process of putting a sequence of characters into a specialized format <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Decoding**
  - The process of converting an encoded format back into the original sequence of characters <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/09_01.png)

</div>

</div>

NOTE:

- Encoding and decoding are used in data communications and storage not for transporting sensitive information.

---

<!-- .element class="image-and-title" -->
# Detection Scenarios

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/07_15.png)

---

<!-- .element class="image-and-title" -->
# DLP Data Flows

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/07_14.png)
Source: PurpleSec

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 09 - Public Key Infrastructure (PKI)

- Course Overview
- Warmup
- Ops Challenge
- Review
  - DLP and Data Classification
- Lecture <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
  - Public Key Infrastructure (PKI)
- Demo

---

<!-- .element class="split-screen-with-title" -->

# Today's Topics

<div>

<div>

- Symmetric key cryptography <!-- .element: class="fragment" data-fragment-index="1" -->
- Asymmetric key cryptography <!-- .element: class="fragment" data-fragment-index="2" -->
  - Public key cryptography <!-- .element: class="fragment" data-fragment-index="3" -->
  - Public key infrastructure (PKI) <!-- .element: class="fragment" data-fragment-index="4" -->
    - Certificates <!-- .element: class="fragment" data-fragment-index="5" -->
    - HTTPS <!-- .element: class="fragment" data-fragment-index="6" -->
    - Pretty Good Privacy (PGP) <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/09_02.png) <!-- .element: class="fragment" height="550" width="100" -->

</div>

</div>

---

<!-- .element class="main-title" -->
# Public Key Infrastructure

---

<!-- .element class="split-screen-with-title" -->
# Symmetric Encryption

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->Same secret key is used for **BOTH** encryption and decryption
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Fast**—suitable for bulk encryption of large amounts of data
- Problem storing and distributing key securely <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Confidentiality only**— sender and recipient know the same key

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/09_03.png)

</div>

NOTE:

- Note that symmetric encryption is mostly used for privacy (confidentiality). Test that the students can explain to you why it cannot be used for authentication, integrity, or non-repudiation.

- Types
  - Symmetric
  - Advantage: Faster
  - Examples: AES-128, AES-192, and AES-256

---

<!-- .element class="text-only" -->
# Symmetric Algorithms

- Modern, secure symmetric algorithms <!-- .element: class="fragment" data-fragment-index="1" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**AES** (Advanced Encryption Standard, also known as Rijndael) is the most popular and widely used symmetric encryption algorithm
- Insecure symmetric algorithms <!-- .element: class="fragment" data-fragment-index="3" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**DES**: 56-bit key size, practically broken, can be brute-forced
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**3DES**: (Triple DES) 64-bit cipher, considered broken
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**RC2**: 64-bit cipher, considered broken
  - &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**RC4**: stream cipher, broken, practical attacks demonstrated
  - &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**Blowfish**: old 64-bit cipher, broken, practical attacks demonstrated
  - &shy;<!-- .element: class="fragment" data-fragment-index="9" -->**GOST**: Russian 64-bit block cipher, disputable security, considered risky

---

<!-- .element class="text-only" -->
# Asymmetric Encryption

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Public/private key pair**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->If the **PUBLIC** key encrypts, **only** the **PRIVATE** key can decrypt
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->If the **PRIVATE** key encrypts, **only** the **PUBLIC** key can decrypt
  - Private key cannot be derived from the public key <!-- .element: class="fragment" data-fragment-index="4" -->
  - Private key must be kept secret <!-- .element: class="fragment" data-fragment-index="5" -->
  - Public key is easy to distribute (anyone can have it) <!-- .element: class="fragment" data-fragment-index="6" -->
- Message size is limited to key size so not suitable for large amounts of data <!-- .element: class="fragment" data-fragment-index="7" -->
- Used for small amounts of authentication data <!-- .element: class="fragment" data-fragment-index="8" -->

NOTE:

- Asymmetric ciphers are mainly used for authentication and non-repudiation.
- Another important use is key exchange.
- A symmetric encryption key is encrypted by the client and sent to the server.
- The server decrypts the key and that secret key is then used to encrypt messages sent between server and client.

- Asymmetric
  - Advantage: Non-repudiation
  - The sender and receiver vouch for who they are with their own private keys
  - Examples: RSA, DSA, and PKCS

---
<!-- .element class="image-and-title -->
# Asymmetric Encryption

<br>

NOTE:

DO:
Draw an asymmetric encryption scenario between two parties (Alice and Bob)

---

<!-- .element class="text-only" -->
# Asymmetric Algorithms

- Asymmetric key cryptosystems provide: <!-- .element: class="fragment" data-fragment-index="1" -->
  - Key-pair generation <!-- .element: class="fragment" data-fragment-index="2" -->
  - Encryption algorithms <!-- .element: class="fragment" data-fragment-index="3" -->
  - Digital signature algorithms <!-- .element: class="fragment" data-fragment-index="4" -->
  - Key exchange algorithms <!-- .element: class="fragment" data-fragment-index="5" -->
- In public key cryptosystems, a message encrypted by the public key is later decrypted by the private key <!-- .element: class="fragment" data-fragment-index="6" -->

---

<!-- .element class="split-screen-with-title" -->
# Public Key Cryptography Algorithms

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**RSA algorithm (Rivest, Shamir, Adleman)**
  - Basis of many public key cryptography schemes <!-- .element: class="fragment" data-fragment-index="2" -->
  - Easy to calculate with the public key, but difficult to reverse without the private key <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Elliptic Curve Cryptography (ECC)**
  - Concerns about RSA being vulnerable to cryptanalysis <!-- .element: class="fragment" data-fragment-index="5" -->
  - Can use smaller keys to obtain same security <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/09_04.png)

</div>

</div>

NOTE:

There's not much point trying to describe ECC without mentioning RSA.

- What is RSA?
  - RSA (Rivest–Shamir–Adleman) is a public-key cryptosystem used for secure data transmission
  - The acronym RSA comes from the surnames of Ron Rivest, Adi Shamir, and Leonard Adleman, who publicly described the algorithm in 1977.
- In a public-key cryptosystem, the encryption key is public and distinct from the decryption key, which is kept secret (private).
- RSA is a relatively slow algorithm and not ideal for large sets of data.

---

<!-- .element class="text-only" -->
# Public Key Infrastructure

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Public Key Infrastructure (PKI)** is a technology for authenticating users and devices in the digital world.
  - One or more trusted parties digitally sign documents certifying that a particular cryptographic key belongs to a particular user or device. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Key used as an identity for the user in digital networks. <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Advantage of PKI:**
  - Scalable data and identity security <!-- .element: class="fragment" data-fragment-index="5" -->
  - Credibility of keys validated by third party <!-- .element: class="fragment" data-fragment-index="6" -->
    - Identity of the public key owner validated <!-- .element: class="fragment" data-fragment-index="7" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**Basic functions of PKI:**
  - Establish the identity of endpoints on a network <!-- .element: class="fragment" data-fragment-index="9" -->
  - Encrypt the flow of data via the network's communication channels <!-- .element: class="fragment" data-fragment-index="10" -->

NOTE:

- Why use Public key infrastructure (PKI) (ref SSH.com)
  - Today’s security professional, particularly at the entry level, needs to have a firm grasp of how and why PKI is used in various systems today.
  - Secure websites
    - Prevents man-in-the-middle attack
    - “Lock” icon in browser - standard user experience
    - Authenticating users and computers
    - Email signing and encryption for confidential message transmission

---

<!-- .element class="split-screen-with-title" -->
<div>

<div>

# Public Key Infrastructure

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is PKI used for?**
  - Secure Browsing (via SSL/TLS) <!-- .element: class="fragment" data-fragment-index="2" -->
  - Securing Email (signing and encrypting messages) <!-- .element: class="fragment" data-fragment-index="3" -->
  - Secure Code-signing <!-- .element: class="fragment" data-fragment-index="4" -->
  - Network Security <!-- .element: class="fragment" data-fragment-index="5" -->
  - File Security (via Encrypted File Systems) <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/09_02.png) <!-- .element: class="fragment" height="700" width="500" -->

</div>

NOTE:

- What is PKI?
  - “Public Key Infrastructure (PKI) is a technology for authenticating users and devices in the digital world.
  - The basic idea is to have one or more trusted parties digitally sign documents certifying that a particular cryptographic key belongs to a particular user or device.
  - The key can then be used as an identity for the user in digital networks.” (ref SSH.com)
- Security functional purpose of PKI
  - Identification
  - Authentication
  - Non-repudiation
  - Confidentiality
- Vocabulary
- CA = Certificate Authority

---

<!-- .element class="text-only" -->
# Public and Private Key Usage

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Public Key Cryptography**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->When you want others to send you confidential messages, you give them your **PUBLIC** key to use to encrypt the message
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->When you want to authenticate yourself to others, you create a signature and sign it by encrypting the signature with your **PRIVATE** key
- But how does someone trust the public key? <!-- .element: class="fragment" data-fragment-index="4" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Public Key Infrastructure (PKI)** validates the identity of the owner of a public key
  - Public key is wrapped in a digital certificate signed by a certificate authority (CA) <!-- .element: class="fragment" data-fragment-index="6" -->
  - Sender and recipient must both trust the CA <!-- .element: class="fragment" data-fragment-index="7" -->

NOTE:
This is a quick recap of the last topic in the previous lesson. Emphasize the use of public and private keys before attempting to move on.

---

<!-- .element class="split-screen-with-title" -->
# Certificate Authorities

<div>

<div>

- Private CAs versus third-party CAs <!-- .element: class="fragment" data-fragment-index="1" -->
- Define services offered <!-- .element: class="fragment" data-fragment-index="2" -->
- Ensure validity of certificates and users <!-- .element: class="fragment" data-fragment-index="3" -->
- Establish trustworthy working procedures <!-- .element: class="fragment" data-fragment-index="4" -->
- Manage servers and keys <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/09_05.png)

</div>

</div>

---

<!-- .element class="title" -->
# Certificate Issuing Process

NOTE:

DO:

- Diagram the certificate issuing process
- Recommendation: recreate on a whiteboard, in real time during lecture, the diagram referenced here
  - Ask CA for certificate
  - Create key pair and send public key to CA
  - Verification process
  - CA digitally signs certificate and sent back to you

---

<!-- .element class="main-title" -->
# Public Key Infrastructure

---

<!-- .element class="text-only" -->
# Public Key Infrastructure

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**How is PKI used?**
  - HTTPS <!-- .element: class="fragment" data-fragment-index="2" -->
    - Defends against MitM and session hijacking <!-- .element: class="fragment" data-fragment-index="3" -->
    - Preferred over HTTP (cleartext) <!-- .element: class="fragment" data-fragment-index="4" -->
    - Why no HTTPS <!-- .element: class="fragment" data-fragment-index="5" -->
  - Authenticating users and computers with SSH <!-- .element: class="fragment" data-fragment-index="6" -->
  - Email signing and encryption using Pretty Good Privacy (PGP) <!-- .element: class="fragment" data-fragment-index="7" -->

NOTE:

- How is PKI used?
  - Secure websites with HTTPS
- Discuss why is HTTPS so important to have on all public-facing web servers
  - HTTP is cleartext data transmission between you and the server
  - Glaring reminder that the internet was not designed for security purposes
- HTTPS is easy to implement so why not?
  - Increase end-user confidence in web server security = better experience on your website
  - Good for defending against MITM and session hijacking although not a perfect defense
- Why don’t all sites use HTTPS?
  - Show students the Why No HTTPS site
  - Example: Navigate to Boeing.com (or any site without HTTPS but obviously should have it)
  - The lack of HTTPS can lead to negative press about your brand
  - If a company fails to implement a simple protocol like HTTPS, this does not inspire public confidence in the org’s security policies and capabilities
  - Do your company a favor and champion HTTPS
- How to protect yourself
  - HTTPSONLY browser addon
- How to install HTTPS on a web site you develop
  - Google Developer Article - How to Set up HTTPS
- Certificates
  - Windows Server supports CA and certificate assignment
  - OpenSSL
- Authenticating users and computers with SSH (ref. AWS SSH)

---

<!-- .element class="title" -->
# Public Key Infrastructure

NOTE:

DO:

- Diagram PKI infrastructure, including the role the CA plays

---
<!-- .element class="split-screen-with-title" -->
# Pretty Good Privacy (PGP)

<div>

<div>

- Email signing and encryption using Pretty Good Privacy (PGP) <!-- .element: class="fragment" data-fragment-index="1" -->
- OpenPGP is the most current version <!-- .element: class="fragment" data-fragment-index="2" -->
- Original PGP developed in the 90s <!-- .element: class="fragment" data-fragment-index="3" -->
  - Backwards compatibility means possibility of downgrade attack <!-- .element: class="fragment" data-fragment-index="4" -->
  - Original PGP considered an insecure encryption method <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/09_06.png)

</div>

</div>

NOTE:

- Email signing and encryption using Pretty Good Privacy (PGP)
  - OpenPGP is the most current version
    - Original PGP developed in the 90s
  - Backwards compatibility means possibility of downgrade attack
  - PGP is largely considered an insecure encryption method today but sees widespread use
- Example use case for PKI certificates
  - Your organization is subject to export compliance regulation by the US government. The compliance officer must submit export compliance reports regularly to DECCS, but her computer is prompting for a certificate to validate her identity. Research DECCS policy and diagram the process.

---
<!-- .element class="title" -->
# What's the deal here?

NOTE:

The infamous NSA whistleblower, Edward Snowden, used the public key encryption tool GNU Privacy Guard when originally working with Glenn Greenwald in 2013 to discuss the leak of thousands of NSA documents: Sadly, Greenwald was still confused. This is a notorious problem with public key encryption.

Watch this news clip up to the first couple minutes where Glen mentions the video, then watch the video itself (relevant parts)

---

<!-- .element class="split-screen-with-title" -->
# GPG4Win

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Gpg4win** (GNU Privacy Guard for Windows) is encryption software for files and emails.
  - Securely transport emails and files with the help of encryption and digital signatures <!-- .element: class="fragment" data-fragment-index="2" -->
  - Includes Kleopatra, a certificate manager <!-- .element: class="fragment" data-fragment-index="3" -->
  - GnuPG is the backend that performs encryption processes <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/09_07.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# GPG, GPA

<div>

<div>

- GPG is the Gnu Privacy Guard tool for Linux <!-- .element: class="fragment" data-fragment-index="1" -->
- GPA (GNU Privacy Assistant) provides a GUI for key management in Linux <!-- .element: class="fragment" data-fragment-index="2" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-09/slides/assets/09_08.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Demo

NOTE:

DO:

Reference the Complete PGP Encryption Tutorial with Gpg4win & GnuPG by Hackersploit.

Demo: OpenPGP
- Demonstrate OpenPGP deployment and basic operation.

Demo: OpenSSL
- Demonstrate OpenSSL deployment and basic operation.
