<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 05

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 05 - Career Coaching Workshop 1

- CCW1 <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Review
  - Systems Hardening
- Lecture
  - Encryption Basics
- Ops Challenge Demo

---

<!-- .element class="split-screen-with-title" -->
## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Module 1** - Strategic Policy Development

- **Module 2** - Cloud Security Principles and Frameworks

- **Module 3** - Cyber Risk Analysis

- **Module 4** - Systems Hardening

- **Module 5** - Midterm Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-05/slides/assets/00_01.png)
<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)

</div>

</div>

---

<!-- .element class="title-with-text" -->
## Module 1 Labs

### Strategic Policy Development

<div align="left" style="font-size: 45px">

- **Class 01** - Strategic Policy Development

<br>

- **Class 02** - Cloud Security Principles and Frameworks

<br>

- **Class 03** - Cyber Risk Analysis

<br>

- **Class 04** - Systems Hardening with CIS Standards

<br>

- &shy;<!-- .element style="color: red;" -->**Class 05** - Career Coaching Workshop

</div>

---

<!-- .element class="split-screen-with-title" -->

## Module 1 Challenges

<div>

<div align="left" style="font-size: 38px">

- **Class 01** - N/A

<br>

- **Class 02** - Uptime Sensor Tool (Part 1 of 2)

<br>

- **Class 03** - Uptime Sensor Tool (Part 2 of 2)

<br>

- **Class 04** - Mock Interviews

<br>

- &shy;<!-- .element style="color: red;" -->**Class 05** - File Encryption

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-05/slides/assets/00_02.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="main-title" -->
# Review: CIS

---

<!-- .element class="split-screen-with-title" -->
# Security Controls

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->The **Center for Internet Security (CIS)** is a non-profit organization that creates secure configuration benchmarks for computer systems.
- CIS Controls are 20 categories of best practices to improve cyber defenses. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Focus security resources based on proven best practices, not on any one vendor's solution <!-- .element: class="fragment" data-fragment-index="3" -->
  - Organize an effective cybersecurity program according to Implementation Groups <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-05/slides/assets/04_02.png)
Source: CIS

</div>

</div>

NOTE:

- What is CIS?
  - The Center for Internet Security (CIS) is a non-profit org that creates secure configuration benchmarks for computer systems.
- What are CIS Controls?
  - CIS Controls are 20 categories of best practices to improve cyber defenses.
- Why use CIS Controls?
  - "Leverage the battle-tested expertise of the global IT community to defend against cyber attacks
  - Focus security resources based on proven best practices, not on any one vendor’s solution

---

<!-- .element class="split-screen-with-title" -->
# Security Controls

<div>

<div>

- CIS benchmarks are a set of configuration standards and best practices designed to help organizations ‘harden' the security of their digital assets <!-- .element: class="fragment" data-fragment-index="1" -->
  - Configuration of existing assets <!-- .element: class="fragment" data-fragment-index="2" -->
  - Developed by industry expert consensus <!-- .element: class="fragment" data-fragment-index="3" -->
- CIS benchmark levels <!-- .element: class="fragment" data-fragment-index="4" -->
  - Level 1 - Less strict <!-- .element: class="fragment" data-fragment-index="5" -->
  - Level 2 - More strict <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-05/slides/assets/04_02.png)
Source: CIS

</div>

NOTE:

- What are CIS Benchmarks?
  - CIS benchmarks are a set of configuration standards and best practices designed to help organizations ‘harden’ the security of their digital assets
  - "Relate specifically to the configuration of existing assets, excluding security defenses like firewalls and EDRs"
  - "Developed by consensus between experts that include SMEs, security vendors, the CIS benchmarking team, and even the global security community via the CIS Workbench"
  - "While not a regulatory requirement, most prominent compliance frameworks point to CIS benchmarks as the industry standard"
- CIS benchmarks contain two levels
  - "Level 1 is designed to rapidly minimize the attack surface of an organization without hindering usability or business functionality. These standards can be considered the minimum level of security and compliance that all organizations should aim to meet or exceed."
  - "Level 2 is a more stringent set of standards designed to maximize an organization’s security posture through ‘defense in depth’. These standards are intended for environments where security is essential, and are more costly and labor intensive to implement."

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 05 - Career Coaching Workshop 1

- CCW1
- Review
  - Systems Hardening
- Lecture <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
  - Encryption Basics
- Ops Challenge Demo

---

<!-- .element class="title-and-subtitle" -->
# Encryption

## Securing Secrets

---

<!-- .element class="split-screen-with-title" -->
# Data States

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Data at rest**
  - The data is in some sort of persistent storage media. <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Data in transit (or data in motion)**
  - The data is being transmitted over a network. <!-- .element: class="fragment" data-fragment-index="4" -->
  - Examples <!-- .element: class="fragment" data-fragment-index="5" -->
    - Website traffic <!-- .element: class="fragment" data-fragment-index="6" -->
    - Remote access traffic <!-- .element: class="fragment" data-fragment-index="7" -->
    - Data being synchronized between cloud repositories <!-- .element: class="fragment" data-fragment-index="8" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="9" -->**Data in use (or data in processing)**
  - Data is present in volatile memory <!-- .element: class="fragment" data-fragment-index="10" -->
    - RAM <!-- .element: class="fragment" data-fragment-index="11" -->
    - CPU registers and caches <!-- .element: class="fragment" data-fragment-index="12" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-05/slides/assets/05_01.png)

</div>

</div>

---

<!-- .element class="text-only" -->
# Encryption

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Encryption** is the act of transforming plaintext into ciphertext.
  - Ensures data confidentiality. <!-- .element: class="fragment" data-fragment-index="2" -->
- Encryption uses a cipher, or mathematical algorithm, to transform readable plaintext into unreadable ciphertext. <!-- .element: class="fragment" data-fragment-index="3" -->

</div>

NOTE:

- Encryption
  - Encryption is the act of transforming plaintext into ciphertext.
  - Encryption uses a cipher, or mathematical algorithm, to transform readable plaintext into unreadable ciphertext.

---

<!-- .element class="image-and-title" -->
# Encryption

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-05/slides/assets/05_02.png)

NOTE:
Data encryption uses a special program to scramble the data on your computer, and an encryption key to revert it to its prior, readable state. You can use it to reliably protect the files and folders on your computer in Windows 10.

---

<!-- .element class="text-only" -->
# Ciphertext

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Ciphertext** is the altered form of a plaintext message, so as to be unreadable for anyone except the intended recipients.
  - Something that has been turned into a secret. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Ensures data confidentiality. <!-- .element: class="fragment" data-fragment-index="3" -->
- Plaintext is human readable. <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

---

<!-- .element class="text-only" -->
# Decryption

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Decryption** is the reverse process from encryption.
  - Converts a ciphertext message back into plaintext through <!-- .element: class="fragment" data-fragment-index="2" -->
  - Uses a cryptographic algorithm and the appropriate key that was used to do the original encryption. <!-- .element: class="fragment" data-fragment-index="3" -->

</div>

NOTE:

- Decryption
  - Decryption is the act of transforming ciphertext back to its original plaintext.

---

<!-- .element class="text-only" -->
# Hashing

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Hashing** is a process that generates a unique hash value for a given data.
  - Can target a file or a string, for example. <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->A **hash value** is a unique value that corresponds to the content of the file.
  - Message Digest 5 (MD5) <!-- .element: class="fragment" data-fragment-index="4" -->
  - Secure Hashing Algorithm 1 (SHA-1) <!-- .element: class="fragment" data-fragment-index="5" -->
  - SHA-2 <!-- .element: class="fragment" data-fragment-index="6" -->
  - NTLM <!-- .element: class="fragment" data-fragment-index="7" -->
  - LANMAN <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

NOTE:

- Hash value
  - Hashing is the simplest type of cryptographic operation.
  - A cryptographic hashing algorithm produces a fixed length string from an input plaintext that can be of any length.
  - The output can be referred to as a checksum, message digest, or hash. The function is designed so that it is impossible to recover the plaintext data from the digest (one-way) and so that different inputs are unlikely to produce the same output (a collision).
  - Common hashing algorithms include:
    - Secure Hash Algorithm (SHA) is considered the strongest algorithm and appears in different variants, the most popular being SHA-256.
    - Message Digest Algorithm #5 (MD5) produces a 128-bit digest and is generally not considered as secure as SHA-256.
  - Note that a hash value cannot be decrypted. Rather, it can be "cracked" using such techniques as a rainbow table.

---

<!-- .element class="image-and-title" -->
# Hashing

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-05/slides/assets/05_03.png)

---

<!-- .element class="image-and-title" -->
# Hashing

<br>

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->Hashing is **NOT** encryption!

![Image](/ops-401-cybersecurity-guide/curriculum/class-05/slides/assets/05_04.png) <!-- .element: class="fragment" data-fragment-index="2" class="small" -->
Source: Julien Piatek <!-- .element: class="fragment" data-fragment-index="3" -->

---

<!-- .element class="image-and-title" -->
# Hashing

<br>

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->Hashes can be **“cracked”** to reveal original data.

![Image](/ops-401-cybersecurity-guide/curriculum/class-05/slides/assets/05_05.png) <!-- .element: class="fragment" data-fragment-index="2" -->
Source: Techsolvency.com <!-- .element: class="fragment" data-fragment-index="3" -->

---

<!-- .element class="main-title" -->
# Demo

NOTE:

DO:

- Pull up the Ops Challenge and step through it with students. Show them how to get started on each one.
  - In Win 10 show how to encrypt a single file with 7-ZIP
  - Encrypt a single file using a PowerShell script.
- Instructions for the commands are on the next two slides

**PowerShell Encrypting**

```powershell
# Encrypt a file
(Get-Item –Path "C:\Users\administrator\Desktop\filename").Encrypt()

# Decrypt a file
(Get-Item –Path "C:\Users\administrator\Desktop\filename").Decrypt()

# Generate an encrypted string from a plaintext string
"P@ssword1" | ConvertTo-SecureString -AsPlainText -Force | ConvertFrom-SecureString
```

**PowerShell Hashing**

```powershell
# Generate a hash without specifying the algorithm
Get-FileHash "C:\Users\administrator\Desktop\filename"

# Specify SHA256 algorithm explicitly
Get-FileHash "C:\Users\administrator\Desktop\filename" -Algorithm SHA256

# Specify MD5
Get-FileHash "C:\Users\administrator\Desktop\filename" -Algorithm MD5
```
