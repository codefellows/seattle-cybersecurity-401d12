<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 10

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 10 - Career Coaching Workshop 2

- CCW2 <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Review
  - Public Key Infrastructure (PKI)
- Lecture
  - Advanced Logging with Sysmon
- Ops Challenge Demo

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/00_01.png)
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

- **Class 09** - Public Key Infrastructure (PKI)

<br>

- &shy;<!-- .element style="color: red;" -->**Class 10** - CCW 2: Personal Pitch

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

- **Class 09** - Mock Interviews

<br>

- &shy;<!-- .element style="color: red;" -->**Class 10** - Advanced Event Logging with Sysmon

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Review:

# Public Key Infrastructure

---

<!-- .element class="title" -->
# What's the deal here?

NOTE:

DO:

- Diagram the certificate issuing process
- Recommendation: recreate on a whiteboard, in real time during lecture, the diagram referenced here
  - Ask CA for certificate
  - Create key pair and send public key to CA
  - Verification process
  - CA digitally signs certificate and sent back to you

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
# Public Key Infrastructure

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is PKI used for?**
  - Secure Browsing (via SSL/TLS) <!-- .element: class="fragment" data-fragment-index="2" -->
  - Securing Email (signing and encrypting messages) <!-- .element: class="fragment" data-fragment-index="3" -->
  - Secure Code-signing <!-- .element: class="fragment" data-fragment-index="4" -->
  - Network Security <!-- .element: class="fragment" data-fragment-index="5" -->
  - File Security (via Encrypted File Systems) <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/09_02.png) <!-- .element: class="fragment" height="700" width="500" -->

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

<!-- .element class="main-title" -->
# Incident Response

---

<!-- .element class="image-and-title" -->
# Incident Response Process

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/10_01.png)

NOTE:
Incident response is discussed in Network+ now, but make sure you allow time to recap on the basic processes.

Note that there are several different models for this process, some of which conflate the tasks into fewer steps.

---

<!-- .element class="split-screen-with-title" -->
# Cyber Incident Response Team

<div>

<div>

- Reporting, categorizing, and prioritizing (triage) <!-- .element: class="fragment" data-fragment-index="1" -->
- CIRT/CERT/CSIRT/SOC <!-- .element: class="fragment" data-fragment-index="2" -->
- Management/decision-making authority <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Incident analysts**
  - 24/7 availability <!-- .element: class="fragment" data-fragment-index="5" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Roles beyond technical response**
  - Legal <!-- .element: class="fragment" data-fragment-index="7" -->
  - Human Resources (HR) <!-- .element: class="fragment" data-fragment-index="8" -->
  - Marketing <!-- .element: class="fragment" data-fragment-index="9" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/10_02.png)
Image credit: John Mattern/Feature Photo Service for IBM.

</div>

---

<!-- .element class="text-only" -->
# Incident Identification

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Precursors and detection channels**
  - Security mechanisms (IDS, log analysis, alerts) <!-- .element: class="fragment" data-fragment-index="2" -->
  - Manual inspections <!-- .element: class="fragment" data-fragment-index="3" -->
  - Notification procedures <!-- .element: class="fragment" data-fragment-index="4" -->
  - Public reporting <!-- .element: class="fragment" data-fragment-index="5" -->
  - Confidential reporting/whistleblowing <!-- .element: class="fragment" data-fragment-index="6" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**First responder**
  - Member of CIRT taking charge of a reported incident <!-- .element: class="fragment" data-fragment-index="8" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="9" -->**Analysis and incident identification**
  - Classify and prioritize <!-- .element: class="fragment" data-fragment-index="10" -->
  - Downgrade low priority alerts to log-only <!-- .element: class="fragment" data-fragment-index="11" -->

NOTE:

Make sure students understand the "day-to-day" of incident identification and alerting.

---

<!-- .element class="text-only" -->
# Security and Information Event Management (SIEM)

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Correlation**
  - Static rules and logical expressions <!-- .element: class="fragment" data-fragment-index="2" -->
  - Threat intelligence feeds <!-- .element: class="fragment" data-fragment-index="3" -->
  - AI-assisted analysis <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Retention**
  - Preserve evidence of attack <!-- .element: class="fragment" data-fragment-index="6" -->
  - Facilitate threat hunting and retrospective incident identification <!-- .element: class="fragment" data-fragment-index="7" -->

---

<!-- .element class="title-and-subtitle" -->
# Advanced Event Logging

## Empowering Security

---

<!-- .element class="split-screen-with-title" -->
# Logging Platforms

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Syslog**
  - Standard protocol used for logging and collecting logs across various devices and platforms<!-- .element: class="fragment" data-fragment-index="2" -->
  - Messages include: <!-- .element: class="fragment" data-fragment-index="3" -->
    - Timestamp <!-- .element: class="fragment" data-fragment-index="4" -->
    - Hostname <!-- .element: class="fragment" data-fragment-index="5" -->
    - Application <!-- .element: class="fragment" data-fragment-index="6" -->
    - Severity level <!-- .element: class="fragment" data-fragment-index="7" -->
    - Actual log message <!-- .element: class="fragment" data-fragment-index="8" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="9" -->**Rsyslog and syslog-ng**
- &shy;<!-- .element: class="fragment" data-fragment-index="10" -->**journalctl**
  - Binary logging <!-- .element: class="fragment" data-fragment-index="11" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="12" -->**Nxlog**
  - Log normalization tool <!-- .element: class="fragment" data-fragment-index="13" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/10_03.png)

</div>

</div>

NOTE:

Focus on syslog, but make sure students recognize the difference in the alternative platforms.

---

<!-- .element class="split-screen-with-title" -->
# About Syslog

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Syslog**
  - Uses UDP ports 514 and 601 <!-- .element: class="fragment" data-fragment-index="2" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Severity levels**
    - Level 0 = Emergency <!-- .element: class="fragment" data-fragment-index="4" -->
    - Level 1 = Alert <!-- .element: class="fragment" data-fragment-index="5" -->
    - Level 2 = Critical <!-- .element: class="fragment" data-fragment-index="6" -->
    - Level 3 = Error <!-- .element: class="fragment" data-fragment-index="7" -->
    - Level 4 = Warning <!-- .element: class="fragment" data-fragment-index="8" -->
    - Level 5 = Notice <!-- .element: class="fragment" data-fragment-index="9" -->
    - Level 6 = Informational <!-- .element: class="fragment" data-fragment-index="10" -->
    - Level 7 = Debugging <!-- .element: class="fragment" data-fragment-index="11" -->
- Syslog servers collect and archive syslog data <!-- .element: class="fragment" data-fragment-index="12" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/10_04.png)
Source: ITT Systems

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Network, OS, and Security Log Files

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**System and security logs**
  - Application <!-- .element: class="fragment" data-fragment-index="2" -->
  - Security/audit <!-- .element: class="fragment" data-fragment-index="3" -->
  - System <!-- .element: class="fragment" data-fragment-index="4" -->
  - Setup <!-- .element: class="fragment" data-fragment-index="5" -->
  - Forwarded events <!-- .element: class="fragment" data-fragment-index="6" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Network logs**
  - Traffic and access data from network appliances <!-- .element: class="fragment" data-fragment-index="8" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="9" -->**Authentication logs**
  - Security log or RADIUS/TACACS+ application logs <!-- .element: class="fragment" data-fragment-index="10" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="11" -->**Vulnerability scan output**

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/10_04.png)

NOTE:
Emphasize that relying on the default logging options is unlikely to be sufficient. Audit logs in particular require careful tuning to provide an effective audit trail and enforce accountability and non-repudiation.

We do mention it elsewhere, but you may want to remind students that sysmon is very widely used for Windows security logging (github.com/SwiftOnSecurity/sysmon-config).

---

<!-- .element class="text-only" -->

# The Problem...

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Windows event logging isn't greatest for detecting security problems**
  - Must correlate multiple different logs <!-- .element: class="fragment" data-fragment-index="2" -->
  - Example: What is the parent process? <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Executive questions to ask**
  - What are we logging? <!-- .element: class="fragment" data-fragment-index="5" -->
  - What level of detail? <!-- .element: class="fragment" data-fragment-index="6" -->
  - Why are we capturing logs this way? <!-- .element: class="fragment" data-fragment-index="7" -->
  - How are we parsing them? <!-- .element: class="fragment" data-fragment-index="8" -->

---

<!-- .element class="split-screen-with-title" -->
# Solution: Sysmon

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**System Monitor (Sysmon)**
  - A Windows utility provided by Microsoft that monitors and logs system activity to help detect and investigate malicious activities. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Runs as a background service <!-- .element: class="fragment" data-fragment-index="3" -->
  - Gathers detailed information: <!-- .element: class="fragment" data-fragment-index="4" -->
    - Process creations <!-- .element: class="fragment" data-fragment-index="5" -->
    - Network connections <!-- .element: class="fragment" data-fragment-index="6" -->
    - Changes to file creation time <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/10_05.png)
Source: BHIS

</div>

</div>

---

<!-- .element class="image-and-text" -->
# Sysmon Config File

- The Sysmon config file tells Sysmon what information it should write to logs. <!-- .element: class="fragment" data-fragment-index="1" -->

Example: <!-- .element: class="fragment" data-fragment-index="2" -->
<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/10_06.png) <!-- .element: class="fragment" data-fragment-index="3" -->

<br>

Source: BHIS <!-- .element: class="fragment" data-fragment-index="4" -->

---

<!-- .element class="split-screen-with-title" -->
# Sysmon Config File

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Event IDs** indicate what type of Sysmon log is generated.
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**EVENT ID 1**: PROCESS CREATION
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**EVENT ID 2**: PROCESS CHANGED A FILE CREATION TIME
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**EVENT ID 3**: NETWORK CONNECTIONS
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**EVENT IDS 4, 5**: SYSMON SERVICE CHANGES
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**EVENT ID 6**: DRIVER LOADED
  - &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**EVENT ID 7**: IMAGE LOADED

</div>

<div>

Here's an example of a network connection: <!-- .element: class="fragment" data-fragment-index="8" -->
![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/10_07.png)
Source: BHIS

</div>

</div>

---

<!-- .element class="image-and-title" -->
# Reverse TCP Attack

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Reverse TCP** (often called reverse shell)
  - An attack whereby the attacker is a TCP server issuing commands to the client.
  - This is backwards from a normal shell which is a forward TCP connection. <!-- .element: class="fragment" data-fragment-index="2" -->
  - In a normal shell, the client issues commands to the server. <!-- .element: class="fragment" data-fragment-index="3" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-10/slides/assets/10_08.png)
Source: Researchgate

---

<!-- .element class="main-title" -->
# Demo

NOTE:

DO:

- Demo 1 Sysmon
  - Demonstrate:
    - Where are Sysmon logs stored?
    - What do Sysmon logs look like?
    - Identify Event ID.
    - How can an Event ID help you identify whether the log relates to an attack?
    - What does Process Creation mean?
  - Select a Sysmon log that correlates to a reverse TCP attack and work through the data in the log. Here's an example if you need it.

```
Network connection detected:
RuleName: Usermode
UtcTime: 2021-04-09 22:00:59.184
ProcessGuid: {20dd5f60-ce9a-6070-6928-000000000d00}
ProcessId: 6300
Image: C:\Users\administrator\Downloads\msf.exe
User: CORP\Administrator
Protocol: tcp
Initiated: true
SourceIsIpv6: false
SourceIp: 10.0.0.52
SourceHostname: DESKTOP-62LU9FS.globex.com
SourcePort: 56584
SourcePortName: -
DestinationIsIpv6: false
DestinationIp: 10.0.0.155
DestinationHostname: -
DestinationPort: 3000
DestinationPortName: -
```
