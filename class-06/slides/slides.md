<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 06

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/00_01.png)
<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# CCW Overview

<div>

<div>

- Career Coaching Workshops in Ops 401 <!-- .element: class="fragment" data-fragment-index="1" -->
  - &shy;<!-- .element: style="color: red;" data-fragment-index="2" -->**Class 05** - CCW 1: Resumes
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Class 10** - CCW 2: Personal Pitch
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Class 15** - CCW 3: Job Searches, Networking, and Negotiations
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Class 30** - CCW 4: Behavioral Interviews
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Class 35** - CCW 5: Technical Interview
  - &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Class 40** - CCW 6: Presentation Day

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/06_01.png)

</div>

---

<!-- .element class="title-with-text" -->
## Module 2 Labs

### Data Security

<div align="left" style="font-size: 45px">

- &shy;<!-- .element style="color: red;" -->**Class 06** - Data File Encryption and Hashing

<br>

- **Class 07** - Protecting Data at Rest

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

- &shy;<!-- .element style="color: red;" -->**Class 06** - File Encryption Script Part 1 of 3

<br>

- **Class 07** - File Encryption Script Part 2 of 3

<br>

- **Class 08** - File Encryption Script Part 3 of 3

<br>

- **Class 09** - Mock Interviews

<br>

- **Class 10** - Advanced Event Logging with Sysmon

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Ops Challenge:

## File Encryption Script

---

<!-- .element class="main-title" -->
# Review: Encryption

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/05_02.png)

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/05_03.png)

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 06 - Data File Encryption and Hashing

- Course Overview
- CCW Overview
- Warmup
- Ops Challenge
- Review
  - Encryption Basics
- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->Lecture:
  - Data File Encryption and Hashing
- Demo

---

<!-- .element class="main-title" -->
# Data Transmission Security

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/05_01.png)

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
# Data in Motion

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Data confidentiality**
  - PII, trade secrets, customer lists, key employee salaries, marketing strategies, source codes, etc. fall into the wrong hands. <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Data integrity**
  - Data remains unchanged <!-- .element: class="fragment" data-fragment-index="4" -->
  - Or if changed, you can be made aware <!-- .element: class="fragment" data-fragment-index="5" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Data source authenticity**
  - The data actually came from who it claimed to <!-- .element: class="fragment" data-fragment-index="7" -->
  - MitM attack <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/05_01.png)

---

<!-- .element class="main-title" -->
# Data Transmission Protocols

---

<!-- .element class="split-screen-with-title" -->
# TLS

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Transport Layer Security (TLS)**
  - Typically used with the HTTP application (referred to as HTTPS or HTTP Secure) <!-- .element: class="fragment" data-fragment-index="2" -->
  - Can also be used to secure other application protocols and as a virtual private networking (VPN) solution. <!-- .element: class="fragment" data-fragment-index="3" -->
  - Versions 1.3, 1.2, 1.1. 1.0 <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Downgrade attack**
  - Man-in-the-middle tries to force the use of a weak cipher suite and SSL/TLS version. <!-- .element: class="fragment" data-fragment-index="6" -->
  - TLS 1.3 is impervious to downgrade attack. <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/06_02.png)

</div>

</div>

NOTE:

- HTTP communications are not secured.
- Secure Sockets Layer (SSL) was developed by Netscape in the 1990s to address the lack of security in HTTP.
  - SSL was quickly adopted as a standard named Transport Layer Security (TLS).
  - It is typically used with the HTTP application (referred to as HTTPS or HTTP Secure) but can also be used to secure other application protocols and as a virtual private networking (VPN) solution.
  - While the acronym SSL is still used, the Transport Layer Security versions are the only ones that are safe to use.
    - A server can provide support for legacy clients, but obviously this is less secure.
    - For example, a TLS 1.2 server could be configured to allow clients to downgrade to TLS 1.1 or 1.0 or even SSL 3.0 if they do not support TLS 1.2.
- A downgrade attack is where a man-in-the-middle tries to force the use of a weak cipher suite and SSL/TLS version.
- TLS version 1.3 was approved in 2018.
  - One of the main features of TLS 1.3 is the removal of the ability to perform downgrade attacks by preventing the use of unsecure features and algorithms from previous versions.
  - There are also changes to the handshake protocol to reduce the number of messages and speed up connections.

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/06_02.png)

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
# FTPS

- Alternatively FTP can use TLS/SSL instead of SSH. <!-- .element: class="fragment" data-fragment-index="1" -->

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Explicit TLS (FTPES)**
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Upgrades an unsecure connection established over **port 21** to a secure one. This protects authentication credentials.
  - The data connection for the actual file transfers can also be encrypted. <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Implicit TLS (FTPS)**
  - Negotiate an SSL/TLS tunnel before the exchange of any FTP commands. <!-- .element: class="fragment" data-fragment-index="6" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="7" -->This mode uses the secure **port 990** for the control connection.

</div>

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/06_02.png)

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/06_02.png)

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/06_02.png)

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

<!-- .element class="main-title" -->
# MitM Attack

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-06/slides/assets/06_03.png)
Image source: Varonis

---

<!-- .element class="main-title" -->
# Demo

NOTE:

Reference [How are passwords stored in Linux (Understanding hashing with shadow utils)](https://www.slashroot.in/how-are-passwords-stored-linux-understanding-hashing-shadow-utils) for this demonstration.

Demonstrate where Linux stores its passwords.

- `/etc/passwd`
- `/etc/shadow`

Let's understand each and every field of the output of /etc/passwd, that are separated by a ":".

- `Username` - what you type when you log into the system.
- `Password` - this field is set to 'x', and the password is stored in /etc/shadow
- `UID` - User identifier assigned to each user. Used by the OS to refer to a user
- `GID` - User's group identifier number
- `GECOS` - or full name of the user. This field contains a list of comma-separated values with the following information: User's full name, Room number, work phone number, home phone number, other contact information.
- `Home directory` - Absolute path to the user's home directory. Contains the user's file and configurations.
- `Login Shell` - the absolute path to the user's login shell. The shell that is started when the user logs into the system.

Let's understand each and every field of the output of /etc/passwd, that are separated by a ":".

- `Username` - what you type when you log into the system
- `Password` - encrypted password in hash format
- `Last password change` - The date of the last password change
- `Minimum` - minimum number of days required between password changes
- `Maximum` - maximum number of days the password is valid, after that user is forced to change passwords again
- `Warn` - number of days before password is to expire that user is warned that the password must be changed
- `Inactive` - number of days after password expires that account is disabled
- `Expire` - The date of expiration of the account, expressed as the number of days since Jan 1, 1970

Demonstrate the process of putting a public key in the `.ssh/authorized_keys` file and test the SSH connection.

After this, demonstrate SCP command syntax. Students will need to perform SCP from their local box to their EC2 box for this lab.

Example syntax: `scp your_username@remotehost.edu:foobar.txt /some/local/directory`
s
