<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 07

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 07 - Protecting Data at Rest

- Course Overview <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - Data File Encryption and Hashing
- Lecture
  - Protecting Data at Rest
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/00_01.png)
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

- &shy;<!-- .element style="color: red;" -->**Class 07** - Protecting Data at Rest

<br>

- **Class 08** - Data Loss Prevention (DLP) and Classification

<br>

- **Class 09** - Public Key Infrastructure (PKI)

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

- &shy;<!-- .element style="color: red;" -->**Class 07** - File Encryption Script Part 2 of 3

<br>

- **Class 08** - File Encryption Script Part 3 of 3

<br>

- **Class 09** - Mock Interviews

<br>

- **Class 10** - Advanced Event Logging with Sysmon

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Review:

## Lab & Ops Challenge

NOTE:

DO: Review previous day's lab and ops challenge

---

<!-- .element class="main-title" -->
# Ops Challenge:

## File Encryption Script

---

<!-- .element class="main-title" -->
# Review:

## Data Transmission Security

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/05_01.png)

</div>

</div>

NOTE:

- What are the three types of data states?
  - "Data at rest—this state means that the data is in some sort of persistent storage media.
- Data in transit (or data in motion) is the state when data is transmitted over a network
  - Examples of types of data that may be in transit include website traffic, remote access traffic, data being synchronized between cloud repositories, and more.
  - In this state, data can be protected by a transport encryption protocol, such as TLS or IPSec.
- Data in use (or data in processing) is the state when data is present in volatile memory, such as system RAM or CPU registers and cache."

---

<!-- .element class="split-screen-with-title" -->
# FTP vs SFTP

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**File Transfer Protocol (FTP)** facilitates the transfer of files between hosts.
  - Uses TCP/IP. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Username/password credentials sent in plain text. <!-- .element: class="fragment" data-fragment-index="3" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->Connection established on **TCP port 21**.
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Secure File Transfer Protocol (SFTP)** facilitates the secure transfer of files between hosts.
  - Uses SSH. <!-- .element: class="fragment" data-fragment-index="6" -->
  - Credentials encrypted. <!-- .element: class="fragment" data-fragment-index="7" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="8" -->Connection established on **TCP port 22**.

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/06_02.png)

</div>

NOTE:

- File Transfer Protocol (FTP) facilitates the transfer of files between hosts.
  - Uses TCP/IP.
  - Credentials sent in cleartext.
  - Connection established on TCP port 21.
- Secure File Transfer Protocol (SFTP) facilitates the secure transfer of files between hosts.
  - Uses SSH.
  - Credentials encrypted.
  - Connection established on TCP port 22.

---

<!-- .element class="split-screen-with-title" -->
# SCP

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Secure Copy Protocol (SCP)** is a network protocol which supports file transfers between hosts on a network using SSH for data transfer.
  - Uses the same mechanisms as SSH for authentication. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Ensures the authenticity and confidentiality of the data in transit. <!-- .element: class="fragment" data-fragment-index="3" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/06_02.png)

</div>

</div>

&shy;<!-- .element: class="fragment" data-fragment-index="4" -->**SCP Syntax**

```bash
scp file.txt username@10.10.0.2:/remote/directory/newfilename.txt
```
<!-- .element: class="fragment" data-fragment-index="5" -->

---

<!-- .element class="split-screen-with-title" -->
# Secure Email Protocols

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Email**
  - Secure SMTP (SMTPS) <!-- .element: class="fragment" data-fragment-index="2" -->
    - Uses implicit TLS <!-- .element: class="fragment" data-fragment-index="3" -->
  - Secure POP (POP3S) <!-- .element: class="fragment" data-fragment-index="4" -->
    - Secured version of POP <!-- .element: class="fragment" data-fragment-index="5" -->
    - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->Uses **TCP port 995**
  - Secure IMAP (IMAPS) <!-- .element: class="fragment" data-fragment-index="7" -->
    - IMAP4 supports permanent connections to server <!-- .element: class="fragment" data-fragment-index="8" -->
    - Multiple concurrent connections <!-- .element: class="fragment" data-fragment-index="9" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/06_02.png)

</div>

</div>

NOTE:

- What other data-in-motion security protocols are there?
  - IPsec
  - SSL, TLS
  - Email
    - Secure SMTP (SMTPS)
      - Uses implicit TLS
    - Secure POP (POP3S)
      - Secured version of POP
      - Uses TCP port 995
    - Secure IMAP (IMAPS)
      - IMAP4 supports permanent connections to server
      - Multiple concurrent connections

---

<!-- .element class="split-screen-with-title" -->
# MitM Attack

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is a man-in-the-middle (MitM) attack?**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->A **MitM** or **on-path attack** is where the attacker secretly intercepts and possibly alters the data being exchanged between the two legitimate parties.
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**How is a Man-in-the-Middle attack performed?**
  - Sniffing <!-- .element: class="fragment" data-fragment-index="4" -->
  - Packet capture <!-- .element: class="fragment" data-fragment-index="5" -->
  - Packet alteration <!-- .element: class="fragment" data-fragment-index="6" -->
  - MAC cloning <!-- .element: class="fragment" data-fragment-index="7" -->
- Examples: Wi-Fi eavesdropping, email hijacking, IP spoofing <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/06_02.png)

</div>

NOTE:

- What is a man-in-the-middle (MitM) attack?
  - A MitM or on-path attack is where the threat actor gains a position between two hosts, and transparently captures, monitors, and relays all communication between the hosts.
- How is a Man-in-the-Middle attack performed?
  - Sniffing
  - Packet capture
  - Packet alteration
  - MAC cloning
  - Examples: Wi-Fi eavesdropping, email hijacking, IP spoofing

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 07 - Protecting Data at Rest

- Course Overview
- Warmup
- Ops Challenge
- Review
  - Data File Encryption and Hashing
- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->Lecture:
  - Protecting Data at Rest
- Demo

---

<!-- .element class="main-title" -->
# Protecting Data at Rest

---

<!-- .element class="split-screen-with-title" -->
# Cryptographic Ciphers

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Ciphers**: Algorithms used for encryption or decryption
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Classical Ciphers**
    - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Substitution Cipher**: Plaintext substituted for ciphertext
    - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Transposition Cipher**: Plaintext rearranged to form ciphertext
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Key-based**
    - Symmetric key algorithm <!-- .element: class="fragment" data-fragment-index="6" -->
    - Asymmetric key algorithm <!-- .element: class="fragment" data-fragment-index="7" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**Input-based**
    - Block cipher <!-- .element: class="fragment" data-fragment-index="9" -->
    - Stream cipher <!-- .element: class="fragment" data-fragment-index="10" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/07_01.png)

</div>

NOTE:

IMPORTANT, students MUST memorize the difference between Symmetric key and Asymmetric key algorithm.

---

<!-- .element class="split-screen-with-title" -->
# Symmetric vs. Asymmetric

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Symmetric Encryption**
  - Two main types <!-- .element: class="fragment" data-fragment-index="2" -->
    - Stream Cipher <!-- .element: class="fragment" data-fragment-index="3" -->
    - Block Cipher <!-- .element: class="fragment" data-fragment-index="4" -->
  - Uses a single key to both encrypt and decrypt data <!-- .element: class="fragment" data-fragment-index="5" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Asymmetric Encryption**
  - Often called Public-Key Cryptography <!-- .element: class="fragment" data-fragment-index="7" -->
  - Widely used in certificate based authentication or PKI (Public Key Infrastructure) <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/07_02.png)

</div>

</div>

NOTE:

- Key-based
  - Symmetric key algorithm
    - Uses only one key for both encryption and decryption.
  - Asymmetric key algorithm
    - Requires two keys, one for encryption and one for decryption.
- Input-based
  - Block cipher
  - Stream Cipher

---

<!-- .element class="split-screen-with-title" -->
# Stream Ciphers

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Stream Cipher**
  - Start with a secret key or “seed” <!-- .element: class="fragment" data-fragment-index="2" -->
  - Converts text one byte at a time  <!-- .element: class="fragment" data-fragment-index="3" -->
  - Faster than block cipher <!-- .element: class="fragment" data-fragment-index="4" -->
  - Difficult to truly generate “random” key stream. <!-- .element: class="fragment" data-fragment-index="5" -->
  - Examples: <!-- .element: class="fragment" data-fragment-index="6" -->
    - German Enigma machine <!-- .element: class="fragment" data-fragment-index="7" -->
    - RC-4 <!-- .element: class="fragment" data-fragment-index="8" -->
    - Most Pre-WWII ciphers were stream ciphers. <!-- .element: class="fragment" data-fragment-index="9" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/07_03.png)

Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Enigma_04.jpg)

</div>

</div>

NOTE:

- Stream cipher
  - Start with a secret key
  - Converts the plain text to cipher text by converting one byte at a time
  - Combines the stream with plaintext to produce ciphertext
  - More complex than block cipher
  - Uses 8 bits at a time
  - Easier to reverse the encrypted text to plain text
  - Examples:
    - RC-4
    - A5
    - German Enigma Machine
  - Pros
    - Fast and simple implementation
    - Efficient transmission means
    - Best used on small data sets

---

<!-- .element class="split-screen-with-title" -->
# Block Ciphers

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Block Cipher**
  - Groups data into blocks instead of bits. <!-- .element: class="fragment" data-fragment-index="2" -->
    - Typical block sizes are 64, 128 and 256 bits. <!-- .element: class="fragment" data-fragment-index="3" -->
  - Whenever text smaller than the block size is encrypted “padding” must be added to the data. <!-- .element: class="fragment" data-fragment-index="4" -->
  - Usage <!-- .element: class="fragment" data-fragment-index="5" -->
    - AES 256 is a 256 bit block cipher. <!-- .element: class="fragment" data-fragment-index="6" -->
      - Widely used globally. <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/07_04.png)

</div>

NOTE:

- Block cipher
  - Groups data into blocks instead of bits
  - Simpler than stream cipher
  - Uses 64 bits or more at a time
  - Difficult to reverse the encrypted text to plain text
  - More complex implementation
  - Best used on larger data sets
  - Examples
    - Lucifer/DES
    - Rijindael/AES
    - Blowfish

---

<!-- .element class="split-screen-with-title" -->
# Ransomware

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Ransomware**
  - A type of malware that when executed, encrypts sectors of the targeted file server or hard disk <!-- .element: class="fragment" data-fragment-index="2" -->
  - Attacker demands a ransom payment to provide the decryption key <!-- .element: class="fragment" data-fragment-index="3" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Delivery Methods**
    - Phishing Emails <!-- .element: class="fragment" data-fragment-index="5" -->
    - Drive-By Downloads <!-- .element: class="fragment" data-fragment-index="6" -->
    - Malvertising  <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

### Ransomware Gangs by Affiliation

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/07_05.png)
Source: KrebsOnSecurity.com

</div>

</div>

NOTE:

- Why is ransomware so prolific?
  - Easy way for cyber-criminals to profit
- What is ransomware?
  - Type of malware that upon execution will encrypt sectors of the targeted file server or hard disk
  - Key belongs only to the ransomware creator
- How to defend against it?
  - US Dept. of the Treasury released a statement on Oct 1 2020
  - Payments to nation state actors may incur legal liability on the ransomware victim
  - Increase data availability by securely backing up important data to an outside location
- How is ransomware created?
  - Ref. to today's Ops Challenge

---

<!-- .element class="split-screen-with-title" -->
# Rootkit

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->A **rootkit** is a set of software designed to access areas of a computer that are restricted.
  - Aims to maintain persistent control over the system while hiding its presence
  - Types: <!-- .element: class="fragment" data-fragment-index="2" -->
    - Hardware or firmware rootkit <!-- .element: class="fragment" data-fragment-index="3" -->
    - Bootloader rootkit <!-- .element: class="fragment" data-fragment-index="4" -->
    - Memory rootkit <!-- .element: class="fragment" data-fragment-index="5" -->
    - Application rootkit <!-- .element: class="fragment" data-fragment-index="6" -->
    - Kernel mode rootkits <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/07_06.png)
Source: pandasecurity.com

</div>

NOTE:

- What are rootkits?
  - Rootkits are a collection of software put in place by an attacker that is designed to obscure system compromise
  - Types:
    - Hypervisor: these rootkits modify the boot sequence of the host system to load a VM as the host OS
    - Hardware (firmware): hide in hardware devices or firmware
    - Boot loader: replace the boot loader with one controlled by the attacker
    - Application: directed to replace valid application files with Trojan binaries. Work inside an application and change the application's behavior, user rights and actions.
    - Kernel: attacks the boot sectors and kernel level of the OS itself, replacing kernel code with back-door code.
      - These are the most dangerous ones
    - Library: use system-level calls to hide their existence
  - Examples:
    - Horsepill
    - Grayfish
    - Sirefef
    - Azazel
    - ZeroAccess

---

<!-- .element class="split-screen-with-title" -->
# Hardware Root of Trust

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->A **hardware root of trust** is a security concept that establishes a secure and trusted foundation within a system's hardware.
  - Purpose is to ensure the integrity, authenticity, and confidentiality of system processes and data <!-- .element: class="fragment" data-fragment-index="2" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Components**
    - Trusted Platform Module (TPM) <!-- .element: class="fragment" data-fragment-index="4" -->
    - Secure Boot <!-- .element: class="fragment" data-fragment-index="5" -->
    - Hardware Security Module (HSM) <!-- .element: class="fragment" data-fragment-index="6" -->
    - Processor Features <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/07_07.png)

</div>

</div>

NOTE:

- Components:
  - Trusted Platform Module (TPM): A hardware chip that provides cryptographic functions and secure storage for keys and data.
  - Secure Boot: A mechanism that ensures only authorized and digitally signed firmware and operating system components are loaded during the boot process.
  - Hardware Security Module (HSM): A dedicated hardware device that provides secure key storage and cryptographic operations.
  - Processor Features: Some modern processors have security features like Intel's Software Guard Extensions (SGX) and ARM's TrustZone to create isolated, secure execution environments.
- Boot Process:
  - During boot-up, the hardware root of trust verifies the integrity of firmware, boot loaders, and the operating system.
  - It checks cryptographic signatures and certificates to ensure that only trusted code is executed.
- Security Benefits:
  - Tamper Resistance: Hardware-based security is difficult to tamper with or compromise physically.
  - Trustworthiness: It provides a strong foundation of trust for system operations.
  - Protection Against Malware: Helps prevent malware attacks by ensuring the integrity of the boot process.

---

<!-- .element class="text-only" -->
# Boot Integrity

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Unified extensible firmware interface (UEFI)**
  - Replaced the older BIOS firmware interface <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Secure Boot**
  - Uses digital signatures to verify the integrity and authenticity of the firmware and OS software <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Measured Boot**
  - Relies on the TPM to ensure that the boot process has not been tampered with and that only trusted software is running on the system <!-- .element: class="fragment" data-fragment-index="6" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Attestation**
  - Used to verify and authenticate the integrity and security of a system or device <!-- .element: class="fragment" data-fragment-index="8" -->

NOTE:

- We assume that students know what UEFI is from A+. If not, consider explaining the difference between BIOS and UEFI, though BIOS motherboards are increasingly scarce.
- Explain how UEFI is accessed and configured.
- Make sure students can distinguish secure boot from measured boot.
- Secure boot is about provisioning certificates for trusted operating systems and blocking unauthorized OSes.
- Measured boot stores and compares hashes of critical boot files to detect unauthorized processes.
- Attestation is the process of sending a signed boot log or report to a remote server.

---

<!-- .element class="split-screen-with-title" -->
# Drive Encryption

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Full disk encryption (FDE)**
  - Encrypts the entire drive, including the OS, system files, and user data. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Data is unreadable without the appropriate key or passphrase. <!-- .element: class="fragment" data-fragment-index="3" -->
  - Provides a strong defense against data breaches, theft, and physical access attacks. <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Self-encrypting drives (SED)**
  - Data/media encryption key (DEK/MEK) <!-- .element: class="fragment" data-fragment-index="6" -->
  - Authentication key (AK) or key encrypting key (KEK) <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/07_07.png)

</div>

NOTE:

- Why is encrypting data at rest helpful?
  - Protects data confidentiality in event of data theft
  - Great for defending sensitive data
  - Many organizations require all hard disks to be encrypted

- What does encrypting data at rest do?
  - Scrambles data, increasing confidentiality

- What is full disk encryption (FDE)?
  - Encryption of all data stored on a disk.
  - Objective is to maintain data confidentiality.

---

<!-- .element class="split-screen-with-title" -->
# FDE Tools in Windows

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**BitLocker**
  - A full disk encryption feature included in several editions of Windows <!-- .element: class="fragment" data-fragment-index="2" -->
  - Uses AES encryption algorithm with 128-bit or 256-bit encryption keys <!-- .element: class="fragment" data-fragment-index="3" -->
  - Supports FDE on Windows systems <!-- .element: class="fragment" data-fragment-index="4" -->
  - Requires user passphrase or PIN during pre-boot <!-- .element: class="fragment" data-fragment-index="5" -->
  - Preinstalled on Windows 10 Pro <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/07_08.png)

</div>

</div>

NOTE:

- What is BitLocker? Ref. BitLocker
  - "BitLocker Drive Encryption is a data protection feature that integrates with the operating system and addresses the threats of data theft or exposure from lost, stolen, or inappropriately decommissioned computers.
  - BitLocker provides the most protection when used with a Trusted Platform Module (TPM) version 1.2 or later. The TPM is a hardware component installed in many newer computers by the computer manufacturers.
  - It works with BitLocker to help protect user data and to ensure that a computer has not been tampered with while the system was offline."
- Show screenshot of TPM chip setting in BIOS

---

<!-- .element class="split-screen-with-title" -->
# Encryption in Linux

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Linux Unified Key Setup (LUKS)**
  - A full disk encryption specification for Linux-based operating systems. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Encrypts entire disk partitions or devices <!-- .element: class="fragment" data-fragment-index="3" -->
  - Uses AES (128-bit or 256-bit) <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**eCryptfs**
  - A Linux stacked file system (not a FDE solution) <!-- .element: class="fragment" data-fragment-index="4" -->
  - Encrypts individual files and directories <!-- .element: class="fragment" data-fragment-index="5" -->
  - Offers granular encryption control <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-07/slides/assets/07_09.png)

</div>

</div>

NOTE:

- What is LUKS?
  - Pull up official LUKS Gitlab
  - Linux Unified Key Setup is a disk encryption specification created in 2004 intended for Linux OS.
  - Provides a common standard for Linux hard disk encryption
  - Benefits
    - Compatibility via standardization
    - Secure against low entropy attacks
    - Support for multiple keys
    - Effective passphrase revocation
    - Free
    - Platform independent standard applied, making LUKS useful on different programs
    - Uses enhanced version of cryptsetup with dm-crypt on the backend for disk encryption

- What is eCryptfs?
  - Linux stacked file system, NOT a FDE solution
  - Useful for non-FDE encryption needs over entire directories in Linux
  - Capable of creating encrypted directory and mounting it on any directory
  - Stores cryptographic metadata on file headers

---

<!-- .element class="main-title" -->
# Administrative Controls

---

<!-- .element class="text-only" -->
# Third-party Risk Management

- Process of identifying, assessing, and mitigating the potential risks and vulnerabilities associated with outsourcing or relying on external parties. <!-- .element: class="fragment" data-fragment-index="1" -->
- Goal is to protect the organization's interests, data, reputation, and assets. <!-- .element: class="fragment" data-fragment-index="2" -->
- Organizations often use standard agreements and practices to manage these risks: <!-- .element: class="fragment" data-fragment-index="3" -->
- Commonly used agreements: <!-- .element: class="fragment" data-fragment-index="4" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" --> **Master Service Agreement (MSA)**
    - An umbrella contract for the work a vendor does with an organization. <!-- .element: class="fragment" data-fragment-index="6" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Service Level Agreement (SLA)**
    - A written contract that specifies the conditions of service that will be provided by the vendor. <!-- .element: class="fragment" data-fragment-index="8" -->

NOTE:

Note that there are two main scenarios for evaluating this risk.

- Most businesses will just focus on using reputable suppliers and being extremely careful about the use of second-hand equipment.
- Military and secret service type organizations may perform their own audits of suppliers.
- Common Agreements:
  - MSA: An umbrella contract for the work that a vendor does within an organization, often includes detailed security and privacy requirements.
  - SLA: Written contracts that specify the conditions of service that will be provided by the vendor and the remedies available to the customer if the vendor fails to meet the SLA
- Remind students about the controversy over Huawei's smartphones and network infrastructure appliances (pcworld.com/article/3252255/cia-fbi-nsa-officials-avoid-huawei-phones.html).

---

<!-- .element class="text-only" -->
# Organizational Security Agreements

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Memorandum of understanding (MOU)**
  - A letter written to document aspects of the relationship <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Business partnership agreement (BPA)**
  - Establish a formal partner relationship <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Non-disclosure agreement (NDA)**
  - Govern use and storage of shared confidential and private information <!-- .element: class="fragment" data-fragment-index="6" -->

NOTE:

We don't try to go into any detail here—just make sure students know the basic purpose of each agreement type.

---

<!-- .element class="main-title" -->
# Demo

NOTE:

DO:

- Show where to access BitLocker in Windows 10
  - On Windows, BitLocker is built in tool for full disk encryption (FDE)
  - Prerequisites
    - Physical TPM chip on motherboard
    - Windows 10 Professional only
  - Demonstrate BitLocker
    - On a computer with multiple hard drives, encrypt a spare drive
    - Save the key off to a different storage device (Warn students about the importance of not losing this key)
    - When complete, physically remove the drive and attempt to read drive from a different computer.
    - Open the drive using your secret key.
- Demo 2 LUKS
  - Show how to install LUKS which can encrypt and decrypt a drive in a Ubuntu Linux VM
- Demo 3 eCryptfs
  - Show how to install and operate eCryptfs
