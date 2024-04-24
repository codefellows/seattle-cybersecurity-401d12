<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 01

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 01 - Strategic Policy Development

- Course Goals<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Course Overview
- Lecture Structure
  - Warmup
  - Review
  - Ops Challenge
  - Lecture
    - Strategic Policy Development
  - Demo

---
<!-- .element class="title-and-subtitle" -->
# Course Goals

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->Provide comprehensive knowledge and skills in cybersecurity.
- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="2" -->Develop a solid foundation in key cybersecurity domains and principles.
- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="3" -->Foster an understanding of security technologies, best practices, and industry standards.
- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="4" -->Cultivate critical thinking and problem-solving abilities in the context of cybersecurity.
- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="5" -->Develop ethical and professional conduct in the field of cybersecurity.
- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="6" -->Gain effective communication and collaboration skills for cybersecurity professionals.

NOTE:
Review the Course Goals with students

---
<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 01 - Strategic Policy Development

- Course Goals
- Course Overview <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Lecture Structure
  - Warmup
  - Review
  - Ops Challenge
    - No Ops Challenge today
  - Lecture
    - Strategic Policy Development
  - Demo

---

<!-- .element class="split-screen-with-title" -->

## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Module 1** - Governance, Risk and Compliance (GRC)

- **Module 2** - Data Security

- **Module 3** - Security Operations

- **Module 4** - Cloud Security

- **Module 5** - Midterm Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-01/slides/assets/00_01.png)
<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)
</div>

</div>

---

<!-- .element class="split-screen-with-title" -->

## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- **Module 6** - Threat Modeling & Analysis

- **Module 7** - Threat Hunting

- **Module 8** - Web Application Security

- **Module 9** - Penetration Testing

- **Module 10** - Final Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-01/slides/assets/00_01.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-with-text" -->

## Module 1 Labs

### Strategic Policy Development

<div align="left" style="font-size: 45px">

- &shy;<!-- .element style="color: red;" -->**Class 01** - Strategic Policy Development

<br>

- **Class 02** - Cloud Security Principles and Frameworks

<br>

- **Class 03** - Cyber Risk Analysis

<br>

- **Class 04** - Systems Hardening with CIS Standards

<br>

- **Class 05** - Career Coaching Workshop

</div>

---

<!-- .element class="split-screen-with-title" -->

## Module 1 Challenges

<div>

<div align="left" style="font-size: 38px">

- &shy;<!-- .element style="color: red;" -->**Class 01** - N/A

<br>

- **Class 02** - Uptime Sensor Tool (Part 1 of 2)

<br>

- **Class 03** - Uptime Sensor Tool (Part 2 of 2)

<br>

- **Class 04** - Mock Interviews

<br>

- **Class 05** - File Encryption

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-01/slides/assets/00_02.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-and-subtitle" -->
# Strategic Policy Development

## Policy Power-Up

NOTE:
Introduce this week's module which is center around GRC

- What is GRC?
  - Stands for Governance, Risk, and Compliance
  - High level strategy for managing the organization's governance, risk management, and compliance with regulations.
  - This is typically something your CSO and management team will oversee, while you operate the day to day systems at the entry level.

- Why do we need to know about compliance regulations and auditing?
  - Often a business driver towards improved cyber policy and posture
  - Cyber (formerly known as "infosec") has its roots in federal systems security, an economic sector laden with regulations
  - Standards such as those established by NIST provide useful frameworks for professionals to work in

---

<!-- .element class="split-screen-with-title" -->
# Strategic Policy Development

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Information Assurance**
  - <!-- .element: class="fragment" data-fragment-index="2" -->A comprehensive approach to managing and protecting an organization's assets.
  - <!-- .element: class="fragment" data-fragment-index="3" -->Provide for the restoration of systems by incorporating
    - <!-- .element: class="fragment" data-fragment-index="4" -->Protection
    - <!-- .element: class="fragment" data-fragment-index="5" -->Detection
    - <!-- .element: class="fragment" data-fragment-index="6" -->Reaction

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-01/slides/assets/01_01.png)
Source: LibreTexts

</div>

</div>

NOTE:

- What is information assurance?
  - Measures that protect and defend information and information systems by ensuring their availability, integrity, authentication, confidentiality, and non-repudiation.
  - These measures include providing for restoration of information systems by incorporating protection, detection, and reaction capabilities.

---

<!-- .element class="split-screen-with-title" -->
# Strategic Policy Development

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**The CIA Triad**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Confidentiality**
    - Unauthorized users are not able to gain access <!-- .element: class="fragment" data-fragment-index="3" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Integrity**
    - No unauthorized changes to information or systems <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-01/slides/assets/01_03.png)
Source: LibreTexts

</div>

</div>

NOTE:

- Confidentiality
  - ISC2 Definition: Preserving authorized restrictions on information access and disclosure, including means for protecting personal privacy and proprietary information.
  - Examples:
    - Principle of least privilege
    - Encryption
    - Firewalls
    - Access Control Lists (ACLs)
  - Integrity
    - ISC2 Definition: Guarding against improper information modification or destruction and includes ensuring information non-repudiation and authenticity.
    - Examples
      - Hash validation
      - Certificates

---

<!-- .element class="split-screen-with-title" -->
# Strategic Policy Development

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Availability**
  - Systems and data are ready to meet the needs of legitimate users <!-- .element: class="fragment" data-fragment-index="2" -->
- Related concepts <!-- .element: class="fragment" data-fragment-index="3" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Authentication**
    - Process of verifying the identity of a user or system <!-- .element: class="fragment" data-fragment-index="5" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Non-repudiation**
    - Actions taken by a system user are evident and irrefutable <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-01/slides/assets/01_03.png)
Source: LibreTexts

</div>

</div>

NOTE:

- Availability
  - ISC2 Definition: Ensuring timely and reliable access to and use of information by authorized users.
  - Can users access the systems?
  - Examples:
    - Automatic failover system
    - Cloud backup
    - Clustering
- Authentication
  - Process of verifying the identity of a user or system
  - It is what's happening every time you are asked for username and password
  - Examples:
    - Username and passwords
    - Biometric data
    - Access cards
- Non-repudiation
  - Assurance that an individual or entity cannot deny their involvement or the validity of an action or communication
  - Examples:
    - Digital Signatures
    - Certificates

---

<!-- .element class="title-and-subtitle" -->

# NIST Cybersecurity Framework

## Unleashing Cyber Resilience

---

<!-- .element class="split-screen-with-title" -->
# Core Concepts

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is a Framework?**
  - A set of guidelines, best practices, and standards for managing cyber risks <!-- .element: class="fragment" data-fragment-index="2" -->
  - A blueprint for designing, implementing, and continuously improving a cybersecurity program <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**The NIST Cybersecurity Framework**
  - Core framework comprises five functions: <!-- .element: class="fragment" data-fragment-index="5" -->
    - Identify <!-- .element: class="fragment" data-fragment-index="6" -->
    - Protect <!-- .element: class="fragment" data-fragment-index="7" -->
    - Detect <!-- .element: class="fragment" data-fragment-index="8" -->
    - Respond <!-- .element: class="fragment" data-fragment-index="9" -->
    - Recover <!-- .element: class="fragment" data-fragment-index="10" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-01/slides/assets/01_04.png)

</div>

</div>

NOTE:

- What is a cybersecurity framework?
  - Serves as a blueprint for designing, implementing, and continuously improving an organization's cybersecurity program.
  - Primary objectives:
    - Provide a structured approach
    - Address key cybersecurity domains
    - Align with industry standards and regulations
    - Foster continuous improvement
  - Don't confuse a framework with a compliance or regulation requirement like HIPAA and PCI/DSS
- NIST Framework
  - Introduce the NIST Framework core functions: Identify, Protect, Detect, Respond and Recover

DO:

- Navigate to the NIST website and show students the NIST Framework document.
- Review some of the security controls listed on the document

---

<!-- .element class="split-screen-with-title" -->
# Business Units

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Information Security Business Units**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Security Operation Center (SOC)**
    - Responsible for monitoring, detecting, and responding to incidents <!-- .element: class="fragment" data-fragment-index="3" -->
    - A central hub for real-time monitoring of security events and alerts. <!-- .element: class="fragment" data-fragment-index="4" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Computer Incident Response Team (CIRT)**
    - Coordinates incident response efforts. <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-01/slides/assets/01_05.png)
Source: VISA Data Center, Blogspot

<div>

</div>

NOTE:

- Security Operations Center (SOC)
  - The SOC team is responsible for monitoring, detecting, and responding to cybersecurity incidents.
  - It acts as a central hub for real-time monitoring of security events and alerts.
  - They continuously monitor and analyze network traffic, logs, and security events to identify potential threats.
- Computer Incident Response Team (CIRT)
  - It works closely with the Security Operations Center (SOC) and other teams to coordinate incident response efforts.
  - The team follows predefined incident response plans and procedures to effectively mitigate and resolve security incidents.
  - Incident response team members document and report incident findings, actions taken, and lessons learned.

---

<!-- .element class="split-screen-with-title" -->
# Security Controls

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Security Control Categories**
  - Technical <!-- .element: class="fragment" data-fragment-index="2" -->
  - Administrative <!-- .element: class="fragment" data-fragment-index="3" -->
  - Physical <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Security Control Functional Types**
  - Preventive <!-- .element: class="fragment" data-fragment-index="6" -->
  - Detective <!-- .element: class="fragment" data-fragment-index="7" -->
  - Corrective <!-- .element: class="fragment" data-fragment-index="8" -->
  - Recovery <!-- .element: class="fragment" data-fragment-index="9" -->
  - Deterrent <!-- .element: class="fragment" data-fragment-index="10" -->
  - Compensating <!-- .element: class="fragment" data-fragment-index="11" -->
  - Directive <!-- .element: class="fragment" data-fragment-index="12" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-01/slides/assets/01_05.png)

</div>

</div>

NOTE:

- Security Controls
  - Classified according to their characteristics
    - Physical
      - Fences, doors, locks, access-control vestibule (FKA: "mantraps"), and fire extinguishers
    - Technical
      - Technical controls are implemented through technology to safeguard systems, networks, and data.
      - Examples include firewalls, intrusion detection systems, antivirus software, encryption, secure authentication mechanisms, and access controls.
    - Administrative
      - These controls involve policies, procedures, and guidelines that govern the management of security within an organization.
      - Examples: security policies, access control policies, incident response plans, security awareness training, and risk assessments.
  - Classified by when they act relative to a security breach:
    - Preventive - intended to prevent an incident from occurring
      - System Hardening
      - Security Guards
      - Security Awareness Training
    - Detective - intended to identify and characterize an incident in progress (sounding the alarm)
      - SIEM
      - Log Monitoring
      - Video Surveillance
    - Corrective - intended to limit the extent of any damage cause by the incident
      - IPS
      - Backups and System Recovery
    - Deterrent - reduce the likelihood of a deliberate attack
    - Compensating - Alternative method put in place to satisfy the requirement for a security measure that cannot be implemented
    - Recovery - includes backups and restores, AV, server clustering, disaster recovery sites
    - Directive - deployed to direct, confine, or control the actions of subjects to ensure compliance with security policies

---
<!-- .element class="image-and-title" -->

# Security Controls Matrix

![Image](/ops-401-cybersecurity-guide/curriculum/class-01/slides/assets/01_06.png)

NOTE:

- Discuss how security controls can be categorized based on their characteristics and how they relate to an incident.
- For example, a control can be technical and preventative (Firewalls, IPS, MFA, AV)

---
<!-- .element class="main-title" -->
# Demo

NOTE:
DO:

- Demonstrate the creation of one policy from the template that is not a part of the lab's objectives.
- Demonstrate the creation and testing of a PowerShell script that configures the endpoint to a specific setting.
  - Example:
    - `Set-ADDefaultDomainPasswordPolicy -Identity globex.com -LockoutDuration 00:40:00 -LockoutObservationWindow 00:20:00 -ComplexityEnabled $True -ReversibleEncryptionEnabled $False -MaxPasswordAge 10.00:00:00`
