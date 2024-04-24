<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 08

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 08 - DLP and Data Classification

- Course Overview <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - Protecting Data at Rest
- Lecture
  - DLP and Data Classification
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/00_01.png)
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

- &shy;<!-- .element style="color: red;" -->**Class 08** - Data Loss Prevention (DLP) and Classification

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

- **Class 07** - File Encryption Script Part 2 of 3

<br>

- &shy;<!-- .element style="color: red;" -->**Class 08** - File Encryption Script Part 3 of 3

<br>

- **Class 09** - Mock Interviews

<br>

- **Class 10** - Advanced Event Logging with Sysmon

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/00_02.png)

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
# Review:

# Protecting Data at Rest

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/05_01.png)

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_06.png)
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_07.png)

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_08.png)

</div>

</div>

NOTE:

- What is BitLocker? Ref. BitLocker
  - "BitLocker Drive Encryption is a data protection feature that integrates with the operating system and addresses the threats of data theft or exposure from lost, stolen, or inappropriately decommissioned computers.
  - BitLocker provides the most protection when used with a Trusted Platform Module (TPM) version 1.2 or later. The TPM is a hardware component installed in many newer computers by the computer manufacturers.
  - It works with BitLocker to help protect user data and to ensure that a computer has not been tampered with while the system was offline."
- Show screenshot of TPM chip setting in BIOS

---

<!-- .element class="text-only" -->
# But What About...

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Encryption** can be used to
  - Protect confidentiality of data at rest <!-- .element: class="fragment" data-fragment-index="2" -->
  - Protect confidentiality data in motion <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->How do we monitor **WHAT** data gets transmitted?
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Data exfiltration**
    - Corporate espionage <!-- .element: class="fragment" data-fragment-index="6" -->
    - Trade secrets <!-- .element: class="fragment" data-fragment-index="7" -->
  - Need a solution <!-- .element: class="fragment" data-fragment-index="8" -->

NOTE:

- Why use DLP?
  - PII/compliance requirements
  - Protecting intellectual property
  - Data visibility/monitoring

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 08 - DLP and Data Classification

- Course Overview
- Warmup
- Ops Challenge
- Review
  - Protecting Data at Rest
- Lecture <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
  - DLP and Data Classification
- Demo

---

<!-- .element class="title-and-subtitle" -->
# Data Classification

## Unlocking the Data Puzzle

---

<!-- .element class="split-screen-with-title" -->
# Privacy and Sensitive Data Concepts

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Security**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->Confidentiality, integrity, and availability **(CIA)** attributes
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Privacy**
  - Personal data about data subjects <!-- .element: class="fragment" data-fragment-index="4" -->
  - Compliance with regulations <!-- .element: class="fragment" data-fragment-index="5" -->
  - Rights of data subjects <!-- .element: class="fragment" data-fragment-index="6" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Information life cycle management**
  - Creation/collection (classification) <!-- .element: class="fragment" data-fragment-index="8" -->
  - Distribution/use <!-- .element: class="fragment" data-fragment-index="9" -->
  - Retention <!-- .element: class="fragment" data-fragment-index="10" -->
  - Disposal <!-- .element: class="fragment" data-fragment-index="11" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_09.png)

</div>

</div>

NOTE:
Do not overlook the importance of availability.

Make sure students can distinguish security requirements from privacy requirements.

---

<!-- .element class="split-screen-with-title" -->
# Data Roles and Responsibilities

<div>

<div>

- Oversight and management of information assets within the organization <!-- .element: class="fragment" data-fragment-index="1" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Data owner**
  - Ultimate responsibility <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Data steward**
  - Data quality and oversight <!-- .element: class="fragment" data-fragment-index="5" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Data custodian**
  - Information systems management <!-- .element: class="fragment" data-fragment-index="7" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**Data privacy officer (DPO)**
  - Oversight of PII assets <!-- .element: class="fragment" data-fragment-index="9" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_09.png)

</div>

NOTE:

- Data owner: Ultimately responsible
- Data steward: responsible for data quality and oversight
- Data custodian: information systems management
- Data privacy officer: oversees PII assets

---

<!-- .element class="split-screen-with-title" -->
# Data Classifications

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Public (unclassified)**
  - No confidentiality, but integrity and availability are important <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Confidential (secret)**
  - Subject to administrative and/or technical access controls <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Critical (top-secret)**

</div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Proprietary**
  - Owned information of commercial value <!-- .element: class="fragment" data-fragment-index="7" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**Private/personal data**
  - Data that can identify an individual <!-- .element: class="fragment" data-fragment-index="9" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="10" -->**Sensitive**
  - Special categories of personal data, such as beliefs, ethnic origin, or sexual orientation <!-- .element: class="fragment" data-fragment-index="11" -->

</div>

</div>

NOTE:
Discuss the difficulty of applying classifications in a consistent way. It is best not to create too many categories.

---

<!-- .element class="split-screen-with-title" -->
# Data Types

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Personally identifiable information (PII)**
  - Data that can be used to identify, contact, or locate an individual <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Customer data**
  - Personal information about the customer's employees <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Health information**
  - Medical and insurance records <!-- .element: class="fragment" data-fragment-index="6" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Financial information**
  - Data held about financial accounts, information such as payroll and tax returns <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="9" -->**Government data**
  - Legislative requirements <!-- .element: class="fragment" data-fragment-index="10" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_09.png)

</div>

</div>

NOTE:
You should not need to spend too long on this—just make sure students are aware of these categories.

---

<!-- .element class="text-only" -->
# Privacy Notices and Data Retention

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Legislation and regulations**
  - General Data Protection Regulation (GDPR) <!-- .element: class="fragment" data-fragment-index="2" -->
  - Rights of data subjects <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Privacy notices**
  - Purpose of collecting personal information <!-- .element: class="fragment" data-fragment-index="5" -->
  - Consent to declared uses and storage <!-- .element: class="fragment" data-fragment-index="6" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="9" -->**Data retention**
  - Keeping data securely to comply with policy/regulation/legislation <!-- .element: class="fragment" data-fragment-index="10" -->
  - Audit requirements versus privacy requirements <!-- .element: class="fragment" data-fragment-index="11" -->

---

<!-- .element class="split-screen-with-title" -->
# Data Sovereignty and Geographical Considerations

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Data sovereignty**
  - Jurisdiction that enforces personal data processing and storage regulations <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Geographical considerations**
  - Select storage locations to mitigate sovereignty issues <!-- .element: class="fragment" data-fragment-index="4" -->
  - Define access controls on the basis of client location <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_10.png)
Source: PNC

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Privacy Breaches and Data Breaches

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Definition of a breach event**
  - Data breach versus privacy breach <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Organizational consequences**
  - Reputation damage <!-- .element: class="fragment" data-fragment-index="4" -->
  - Identity theft <!-- .element: class="fragment" data-fragment-index="5" -->
  - Fines <!-- .element: class="fragment" data-fragment-index="6" -->
  - IP theft <!-- .element: class="fragment" data-fragment-index="7" -->
- Notifications of breaches <!-- .element: class="fragment" data-fragment-index="8" -->
- Escalation <!-- .element: class="fragment" data-fragment-index="9" -->
- Public notification and disclosure <!-- .element: class="fragment" data-fragment-index="10" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_10.png)

</div>

</div>

NOTE:
Note that the definition of a breach can be quite narrow. It is important to review legislation and determine precise compliance requirements.

---

<!-- .element class="text-only" -->
# Data Sharing and Privacy Terms of Agreement

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Service Level Agreement (SLA)**
  - Require access controls and risk assessment to protect data <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Interconnection Security Agreement (ISA)**
  - Requirements to interconnect federal systems with third-party systems <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Non-disclosure agreement (NDA)**
  - Legal basis for protecting information assets <!-- .element: class="fragment" data-fragment-index="6" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Data sharing and use agreement**
  - Specify terms for the way a dataset can be analyzed <!-- .element: class="fragment" data-fragment-index="8" -->
  - Proscribe use of re-identification techniques <!-- .element: class="fragment" data-fragment-index="9" -->

---

<!-- .element class="main-title" -->
# Data Loss Prevention

---

<!-- .element class="split-screen-with-title" -->
# Why DLP?

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Key drivers of DLP adoption**
  - Growth of CISO role <!-- .element: class="fragment" data-fragment-index="2" -->
  - Compliance <!-- .element: class="fragment" data-fragment-index="3" -->
  - Complexity of technologies/mobile devices <!-- .element: class="fragment" data-fragment-index="4" -->
  - Data breaches <!-- .element: class="fragment" data-fragment-index="5" -->
  - Stolen data sold on dark web <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

NOTE:

- Why use DLP?
  - PII/compliance requirements
  - Protecting intellectual property
  - Data visibility/monitoring

- What is DLP?
  - Data loss prevention is a data security control designed to monitor and control the movement of data by classification type
  - Differentiate
    - Program (policy)
    - Product (tool)
- What are the different types of DLP?
  - Endpoint
  - Network
  - Edge system (E.G. firewall)
  - Cloud
  - E.G O365 DLP

---

<!-- .element class="split-screen-with-title" -->
# Data Exfiltration

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Data exfiltration methods**
  - Removable media <!-- .element: class="fragment" data-fragment-index="2" -->
  - Transferring over the network <!-- .element: class="fragment" data-fragment-index="3" -->
  - Phone or video calls <!-- .element: class="fragment" data-fragment-index="4" -->
  - Taking a picture or video of text data <!-- .element: class="fragment" data-fragment-index="5" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Ordinary countermeasures**
  - Encrypt all sensitive data at rest <!-- .element: class="fragment" data-fragment-index="7" -->
  - Maintain offsite backups of data <!-- .element: class="fragment" data-fragment-index="8" -->
  - Implementing access controls <!-- .element: class="fragment" data-fragment-index="9" -->
  - End user training <!-- .element: class="fragment" data-fragment-index="10" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_11.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Data Loss Prevention

<div>

<div>

- DLP products scan files for matched strings and prevent unauthorized copying or transfer <!-- .element: class="fragment" data-fragment-index="1" -->
  - Policy server <!-- .element: class="fragment" data-fragment-index="2" -->
  - Endpoint agents <!-- .element: class="fragment" data-fragment-index="3" -->
  - Network agents <!-- .element: class="fragment" data-fragment-index="4" -->
- Cloud-based DLP <!-- .element: class="fragment" data-fragment-index="5" -->
- Remediation <!-- .element: class="fragment" data-fragment-index="6" -->
  - Alert only <!-- .element: class="fragment" data-fragment-index="7" -->
  - Block <!-- .element: class="fragment" data-fragment-index="8" -->
  - Quarantine <!-- .element: class="fragment" data-fragment-index="9" -->
  - Tombstone <!-- .element: class="fragment" data-fragment-index="10" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_12.png)

</div>

</div>

NOTE:
Refer students to a vendor site for more information about specific DLP product features and implementation guidelines.

---

<!-- .element class="image-and-title" -->
# DLP Data Flows

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_13.png)
Source: PurpleSec

---

<!-- .element class="image-and-title" -->
# Detection Scenarios

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_14.png)
Source: ThingLink

NOTE:
There was once a young Shepherd Boy who tended his sheep at the foot of a mountain near a dark forest. It was rather lonely for him all day, so he thought upon a plan by which he could get a little company and some excitement. He rushed down towards the village calling out “Wolf, Wolf,” and the villagers came out to meet him, and some of them stopped with him for a considerable time. This pleased the boy so much that a few days afterwards he tried the same trick, and again the villagers came to his help. But shortly after this a Wolf actually did come out from the forest, and began to worry the sheep, and the boy of course cried out “Wolf, Wolf,” still louder than before. But this time the villagers, who had been fooled twice before, thought the boy was again deceiving them, and nobody stirred to come to his help. So the Wolf made a good meal off the boy's flock, and when the boy complained, the wise man of the village said:

“A liar will not be believed, even when he speaks the truth.”

Source

---

<!-- .element class="split-screen-with-title" -->
# Detection Scenarios

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**True positive**
  - Optimal outcome <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**False positive**
  - Annoying false alarm <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**True negative**
  - Optimal <!-- .element: class="fragment" data-fragment-index="6" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**False negative**
  - Most dangerous scenario <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_15.png)

</div>

---

<!-- .element class="text-only" -->
# DLP Concepts

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Detection**
  - Positive match - Data scanned meets policy <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Data Type**
  - What data classification is associated (and therefore, compliance) <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Pattern**
  - Text patterns the DLP system is looking for <!-- .element: class="fragment" data-fragment-index="6" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Policy**
- &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**Confidence level**
  - How confident is the pattern detection rule that the detection is a true positive <!-- .element: class="fragment" data-fragment-index="9" -->

---

<!-- .element class="text-only" -->
# DLP Mechanics

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->Example pattern: **American Bank Association (ABA) Routing Number**
  - Formatted: <!-- .element: class="fragment" data-fragment-index="2" -->
    - Four digits beginning with 0, 1, 2, 3, 6, 7, or 8 <!-- .element: class="fragment" data-fragment-index="3" -->
    - A hyphen <!-- .element: class="fragment" data-fragment-index="4" -->
    - Four digits <!-- .element: class="fragment" data-fragment-index="5" -->
    - A hyphen <!-- .element: class="fragment" data-fragment-index="6" -->
    - A digit <!-- .element: class="fragment" data-fragment-index="7" -->
  - Unformatted: <!-- .element: class="fragment" data-fragment-index="8" -->
    - Nine consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8 <!-- .element: class="fragment" data-fragment-index="9" -->

</div>

---

<!-- .element class="image-and-title" -->
# DLP Mechanics

![Image](/ops-401-cybersecurity-guide/curriculum/class-08/slides/assets/07_16.png)
Source: The Balance

---

<!-- .element class="main-title" -->
# Demo

NOTE:

DO:

- Demonstrate how to install a data loss prevention solution spanning two systems
- Choices for free DLP software
  - OpenDLP
  - MYDLP by Comodo
  - Implement a detection rule
