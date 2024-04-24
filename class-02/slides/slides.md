<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 02

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 02 - Cloud Security Principles and Frameworks

- Course Overview <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - Strategic Policy Development
- Lecture
  - Cloud Security Principles and Frameworks
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/00_01.png)
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

- &shy;<!-- .element style="color: red;" -->**Class 02** - Cloud Security Principles and Frameworks

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

- **Class 01** - N/A

<br>

- &shy;<!-- .element style="color: red;" -->**Class 02** - Uptime Sensor Tool (Part 1 of 2)

<br>

- **Class 03** - Uptime Sensor Tool (Part 2 of 2)

<br>

- **Class 04** - Mock Interviews

<br>

- **Class 05** - File Encryption

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/00_02.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Ops Challenge

## Uptime Sensor Tool

---

<!-- .element class="main-title" -->
# Review

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/01_03.png)
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/01_03.png)
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/01_05.png)

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/01_06.png)

NOTE:

- Discuss how security controls can be categorized based on their characteristics and how they relate to an incident.
- For example, a control can be technical and preventative (Firewalls, IPS, MFA, AV)

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 02 - Cloud Security Principles and Frameworks

- Course Overview
- Warmup
- Ops Challenge
- Review
  - Strategic Policy Development
- Lecture <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
  - Cloud Security Principles and Frameworks
- Demo

---

<!-- .element class="title-and-subtitle" -->
# Cloud Security

## Defending the cloud

---

<!-- .element class="split-screen-with-title" -->
# Cloud Security

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Why do we care about cloud security frameworks?**
  - Computing frameworks shift as we move into cloud systems <!-- .element: class="fragment" data-fragment-index="2" -->
  - Aggressive cloud adoption as a business strategy <!-- .element: class="fragment" data-fragment-index="3" -->
  - Traditional IT processes are abstracted away <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Who secures what part of the cloud?**
  - We'll look at the **shared responsibility model** today <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_01.png)

</div>

</div>

NOTE:

- WHY
  - Why do we care about cloud security frameworks?
    - Computing paradigms shift as we move into cloud systems
    - Traditional IT processes are abstracted away
  - Who secures what part of the cloud?
    - We'll look at the "shared responsibility model" today which attempts to define this.

---

<!-- .element class="split-screen-with-title" -->
# Cloud Security

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Why do organizations adopt cloud services?**
  - Rapid and simple deployment <!-- .element: class="fragment" data-fragment-index="2" -->
  - Less time to market for services <!-- .element: class="fragment" data-fragment-index="3" -->
  - Cost efficiency <!-- .element: class="fragment" data-fragment-index="4" -->
  - More utilization of server resources <!-- .element: class="fragment" data-fragment-index="5" -->
  - Less capital and operational costs <!-- .element: class="fragment" data-fragment-index="6" -->
  - Better perceived security by managing and controlling it internally <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_01.png)

</div>

</div>

NOTE:

- Why do organizations adopt cloud services?
  - Rapid and simple deployment
  - Less time to market for services
  - Cost efficiency
  - More utilization of server resources
  - Less capital and operational costs
  - Better perceived security by managing and controlling it internally

---

<!-- .element class="split-screen-with-title" -->
# Cloud Security

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Cloud Service Models**
  - Private <!-- .element: class="fragment" data-fragment-index="2" -->
  - Public  <!-- .element: class="fragment" data-fragment-index="3" -->
  - Hybrid  <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Deployment Models**
  - Infrastructure as a Service (IaaS) <!-- .element: class="fragment" data-fragment-index="6" -->
  - Platform as a Service (PaaS) <!-- .element: class="fragment" data-fragment-index="7" -->
  - Software as a Service (SaaS) <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_01.png)

</div>

</div>

NOTE:

- Cloud Service Models
  - Public Cloud
    - Offered by third-party providers and accessible to the general public over the internet.
    - Examples: Azure, AWS, Google Cloud
  - Private Cloud
    - Exclusively dedicated to a single organization
    - Can be on-premise or a third-party data center
    - Enhanced control and privacy but more work
  - Hybrid Cloud
    - Combines both public and private cloud
  - Community Cloud
    - Shared cloud infrastructure that server multiple organizations within a specific community or industry
- Deployment Models
  - IaaS
    - Provides virtualized computing resources over the internet
    - Users can rent VMs, storage, and networking resources on a pay as you go basis
  - PaaS
    - Delivers a platform and environment for developers to build, deploy and manage applications without the complexity of managing underlying infrastructure
  - SaaS
    - Delivers fully functional software applications over the internet on a subscription basis
    - Users access the software through a web browser and the provider handles maintenance, updates and security

---

<!-- .element class="image-and-title" -->

# Cloud Computing as a Service

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_02.png)
Source: Technofaq

NOTE:

- IaaS
  - Virtualized computing resources (VMs, storage and networking) that allows organizations to build and manage their infrastructure without needing physical hardware
- PaaS
  - Platform and environment for developing, testing and deploying applications
  - Focus on application rather than managing infrastructure
- SaaS
  - Delivers software applications over the internet
  - Allows users to access and use software without needing to install the application or local infrastructure

---

<!-- .element class="split-screen-with-title" -->
# Cloud Security

### A changing environment

<div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_03.png) <!-- .element: class="fragment" data-fragment-index="1" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_04.png) <!-- .element: class="fragment" data-fragment-index="2" -->
Source: Statista

</div>

</div>

NOTE:

- Highlight the market share of each cloud provider
- Highlight the increase in cost of cybercrime worldwide

---

<!-- .element class="split-screen-with-title" -->
# Cloud Security

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**The AWS Shared Responsibility Model**
  - Outlines who is responsible for the security of what parts of the cloud. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Security and Compliance is a shared responsibility between AWS and the customer: <!-- .element: class="fragment" data-fragment-index="2" -->
    - &shy;<!-- .element: class="fragment" data-fragment-index="3" --> Customers are responsible for security and compliance **IN** the cloud
    - &shy;<!-- .element: class="fragment" data-fragment-index="4" --> AWS is responsible for the security **OF** the cloud

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_05.png) <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

</div>

NOTE:

- AWS Shared Responsibility Model: The shared responsibility model is a framework that defines the security responsibilities between Amazon Web Services (AWS) and its customers.
- AWS Infrastructure Security: AWS is responsible for the security of the underlying infrastructure, including data centers, networking, and hardware.
- Customer Responsibility for the Cloud: Customers are responsible for securing their applications, data, operating systems, and configurations within the AWS environment.
- Security "of" the Cloud vs. Security "in" the Cloud: AWS ensures the security of the cloud, while customers are responsible for the security within the cloud.

---

<!-- .element class="image-and-title" -->

# Cloud Security

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_06.png)
Source: AWS

---

<!-- .element class="split-screen-with-title" -->
# Cloud Security

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**ISO 27001**
  - A comprehensive set of standards for information security. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Includes best practices for <!-- .element: class="fragment" data-fragment-index="3" -->
    - Security and risk management <!-- .element: class="fragment" data-fragment-index="4" -->
    - Compliance <!-- .element: class="fragment" data-fragment-index="5" -->
    - Technical implementation <!-- .element: class="fragment" data-fragment-index="6" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**ISO 31000 (or 31K)**
  - A comprehensive set of standards for enterprise risk management. <!-- .element: class="fragment" data-fragment-index="8" -->
  - Not focused solely on information security risks <!-- .element: class="fragment" data-fragment-index="9" -->
  - Includes risks such as business continuity, market, currency, credit, operational, etc. <!-- .element: class="fragment" data-fragment-index="10" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_07.png)
Source: Quotium

</div>

</div>

NOTE:

- ISO 27001: ISO 27001 is a specific standard that focuses on information security management systems (ISMS).
  - It provides requirements and guidelines for establishing, implementing, maintaining, and continually improving an ISMS to protect sensitive information and manage information security risks.
- ISO 31000: ISO 31000, on the other hand, is a broader standard that provides guidance on risk management.
  - It offers a framework and principles for organizations to systematically identify, assess, treat, and monitor risks across various domains, not limited to information security.
- In summary, ISO 27001 is dedicated to information security management systems and focuses on protecting sensitive information, while ISO 31000 provides a general framework for risk management applicable to a wider range of risks and organizational objectives.

---

<!-- .element class="split-screen-with-title" -->
# Cloud Security

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" --> **Cloud Security Alliance (CSA)**
  - An industry body providing security guidance to cloud service providers (CSPs) <!-- .element: class="fragment" data-fragment-index="2" -->
  - CSA developed their own cybersecurity framework called the Cloud Controls Matrix (CCM) <!-- .element: class="fragment" data-fragment-index="3" -->
- CSA also developed the Security Guidance v4.0 <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_08.png)
Source: blog.atheno.com

</div>
NOTE:

- Cloud Security Alliance (CSA)
  - An industry body providing security guidance to cloud service providers (CSPs), including enterprise reference architecture and security controls matrix.
  - CSA developed their own cybersecurity framework called the Cloud Controls Matrix (CCM)
  - CSA also developed the Security Guidance v4.0

</div>
---

<!-- .element class="split-screen-with-title" -->
# SOC 2

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" --> **What is SOC2?**
  - An auditing standard designed to assess the security, availability, processing integrity, confidentiality, and privacy of customer data that a service organization handles. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Audits are conducted by independent certified public accountants who check the design and effectiveness of controls <!-- .element: class="fragment" data-fragment-index="3" -->
  - Reports give customer confidence in an organization's security and privacy controls <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_11.png)

</div>

</div>

NOTE:

- SOC 2 is an auditing standard that provides assurance on the security, availability, processing integrity, confidentiality, and privacy of service organizations.
- Independent Audit: SOC 2 audits are conducted by independent CPAs who assess controls' design and effectiveness.
- SOC 2 helps organizations demonstrate compliance, manage risks, and meet customer expectations.
- SOC 2 reports provide customers with confidence in an organization's security and privacy controls.
- SOC 2 compliance requires ongoing monitoring and enhancement of internal controls.

---

<!-- .element class="image-and-title" -->
# SOC 2

![Image](/ops-401-cybersecurity-guide/curriculum/class-02/slides/assets/02_10.png)

NOTE:

- Trust Principles
  - SOC 2 audits are based on five trust principles:
    - Security: The system is protected against unauthorized access, both physical and logical.
    - Availability: The system is available for operation and use as agreed upon.
    - Processing Integrity: System processing is complete, accurate, timely, and authorized.
    - Confidentiality: Information designated as confidential is protected as agreed upon.
    - Privacy: Personal information is collected, used, retained, and disclosed as specified in the organization's privacy notice.

---
<!-- .element class="main-title" -->
# Demo
