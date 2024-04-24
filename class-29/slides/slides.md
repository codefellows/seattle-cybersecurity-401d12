<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 29

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

Daily TODOs

- Hide/unhide slides to show as necessary
- Toggle presentation mode on and screen share this first slide when you initialize recording on Zoom to indicate class number

---

<!-- .element class="split-screen-with-title" -->

## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Module 6** - Threat Modeling & Analysis

- **Module 7** - Threat Hunting

- **Module 8** - Web Application Security

- **Module 9** - Penetration Testing

- **Module 10** - Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/0_01.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-with-text" -->

## Module 6 Labs

### Threat Modeling & Analysis

<div align="left" style="font-size: 45px">

- &shy;**Class 26** - Remote Code Execution

<br>

- **Class 27** - Persistence

<br>

- **Class 28** - Log Clearing

<br>

- **Class 29** - Modeling a Web Application

<br>

- **Class 30** - Career Coaching Workshop

</div>

---

<!-- .element class="split-screen-with-title" -->

## Module 6 Challenges

<div>

<div align="left" style="font-size: 35px">

- &shy;<!-- .element style="color: red;" -->**Class 26** - Event Logging Tool (Part 1 of 3)

<br>

- **Class 27** - Event Logging Tool (Part 2 of 3)

<br>

- **Class 28** - Event Logging Tool (Part 3 of 3)

<br>

- **Class 29** - Mock Interviews

<br>

- **Class 30** - Antivirus Evasion

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/0_03.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 29 - Modeling a Web Application

- Course Overview
- Warmup <!-- .element style="color: red;" -->
- Review
- Lecture:
  - Modeling a Web Application
- Demo

---

<!-- .element class="main-title" -->

# Warmup

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 29 - Modeling a Web Application

- Course Overview
- Warmup
- Review <!-- .element style="color: red;" -->
- Lecture:
  - Modeling a Web Application
- Demo

---

<!-- .element class="main-title" -->

# Review

- Previous Concepts <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Lab 28
- Ops Challenge 28

---

<!-- .element class="main-title" -->
# Review:

## Review: Log Clearing

NOTE:

---

<!-- .element class="split-screen-with-title" -->
# T1070.001 Log Clearing

<div>

<div>

ATT&CK details

- ID: T1070.001
- Sub-technique of: T1070
- Tactic: Defense Evasion
- Platforms: Windows
- System Requirements: Clearing the Windows event logs requires Administrator permissions
- Permissions Required: Administrator
- Data Sources: Command: Command Execution, Process: OS API Execution
- Defense Bypassed: Anti Virus, Host Intrusion Prevention Systems, Log Analysis

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/0_11.png)

---

<!-- .element class="split-screen-with-title" -->
# Atomic Testing Cycle

<div>

<div>

- The Atomic Testing Cycle is a phased approach to improving your cyber defenses by testing them.
- Levels of security team sophistication:
  - Level 1: Just starting out, limited resources
  - Level 2: Starting to mature, some resources
  - Level 3: Advanced cybersecurity teams and resources
- Even at level 1, Atomic Tests can add a great deal of value to security efforts

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/28_03.png)

NOTE:
All Atomic Tests by Tactic and Technique: <https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/Indexes/Indexes-Markdown/index.md>
Reading: <https://medium.com/mitre-attack/getting-started-with-attack-red-29f074ccf7e3>

---

<!-- .element class="split-screen-with-title" -->
# Team Colors

<div>

<div>

- Adversary emulation in action <!-- .element class="fragment" data-fragment-index="1" -->
  - The red team acts as the adversary, attempting to penetrate the network or exploit the network as a rogue internal attacker <!-- .element class="fragment" data-fragment-index="2" -->
    - In-house security staff or a third-party company <!-- .element class="fragment" data-fragment-index="3" -->
- The blue team operates the security system with a view to detecting and repelling the red team <!-- .element class="fragment" data-fragment-index="4" -->

</div>

<div>

- A white team sets the parameters for the exercise <!-- .element class="fragment" data-fragment-index="5" -->
  - Authorized to monitor or halt the exercise <!-- .element class="fragment" data-fragment-index="6" -->
- Purple Teams enhance information sharing between the red and blue teams <!-- .element class="fragment" data-fragment-index="7" -->
  - Maximize each team's effectiveness <!-- .element class="fragment" data-fragment-index="8" -->

</div>

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/28_05.png)

---

<!-- .element class="main-title" -->

# Review:

## Lab 28

NOTE:

---

<!-- .element class="main-title" -->
# Review:

## Ops Challenge 28

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 29 - Modeling a Web Application

- Course Overview
- Warmup
- Review
- Lecture: <!-- .element style="color: red;" -->
  - Modeling a Web Application
- Demo

---

<!-- .element class="title-and-subtitle" -->

# Lecture:

## Class 29 - Modeling a Web Application


- **Modeling a Web Application:**
  - Threat Modeling
  - STRIDE

---

<!-- .element class="main-title" -->
# Modeling a Web Application:

## Threat Modeling

NOTE:
Is there a relevant Ch. in the Wiley Wiley Security+ (SY0-601) Study Guide?

---

<!-- .element class="split-screen-with-title" -->
# Threat Modeling

<div>

<div>

- Threat modeling is process of identifying and assessing the possible threat actors and attack vectors that pose a risk to the security of an app, network, or other system <!-- .element class="fragment" data-fragment-index="1" -->
- Why use threat modeling? <!-- .element class="fragment" data-fragment-index="2" -->
  - Cyber education and awareness <!-- .element class="fragment" data-fragment-index="3" -->
  - Create teachable moments for non-security teams to gain awareness <!-- .element class="fragment" data-fragment-index="4" -->
  - Improve application security posture <!-- .element class="fragment" data-fragment-index="5" -->
  - Fundamental to DevSecOps <!-- .element class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_01.png)
Source: InfoQ

</div>

---

<!-- .element class="split-screen-with-title" -->
# SDLC

<div>

<div>

- The Software Development Lifecycle (SDLC) is a systematic approach to developing software with great: <!-- .element class="fragment" data-fragment-index="1" -->
  - Robustness <!-- .element class="fragment" data-fragment-index="2" -->
  - Performance <!-- .element class="fragment" data-fragment-index="3" -->
  - Security <!-- .element class="fragment" data-fragment-index="4" -->
  - User experience (UX) <!-- .element class="fragment" data-fragment-index="5" -->
- Software development security is one of the eight domains of the Certified Information Systems Security Professionals (CISSP) certification from ISC2 <!-- .element class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_02.png)
Source: Husson

</div>

---

<!-- .element class="split-screen-with-title" -->
# DevSecOps

<div>

<div>

- Threat modeling helps build DevSecOps culture <!-- .element class="fragment" data-fragment-index="1" -->
  - DevSecOps stands for development, security, and operations. It automates the integration of security at every phase of the SDLC <!-- .element class="fragment" data-fragment-index="2" -->
  - Development team and the operations team should: <!-- .element class="fragment" data-fragment-index="3" -->
    - Share skill sets <!-- .element class="fragment" data-fragment-index="4" -->
    - Establish a common goal <!-- .element class="fragment" data-fragment-index="5" -->
    - Function as a unit <!-- .element class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_03.png)
Source: NotSoSecure

</div>

---

<!-- .element class="split-screen-with-title" -->
# Threat Modeling

<div>

<div>

- What is threat modeling? <!-- .element class="fragment" data-fragment-index="1" -->
  - Threat modeling is the practice of identifying and prioritizing potential threats and security mitigations to protect something of value, such as confidential data or intellectual property. <!-- .element class="fragment" data-fragment-index="2" -->
  - By continuously threat modeling applications, security teams can better protect apps while educating the development team and building a culture of security throughout the enterprise. <!-- .element class="fragment" data-fragment-index="3" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_04.png)

---

<!-- .element class="split-screen-with-title" -->
# Threat Modeling

<div>

<div>

- Design <!-- .element class="fragment" data-fragment-index="1" -->
  - Capture all requirements for your system and create a data-flow diagram. <!-- .element class="fragment" data-fragment-index="2" -->
- Break <!-- .element class="fragment" data-fragment-index="3" -->
  - Apply a threat modeling framework to the data-flow diagram and find potential security issues. <!-- .element class="fragment" data-fragment-index="4" -->
- Fix <!-- .element class="fragment" data-fragment-index="5" -->
  - Decide how to approach each issue with the right combination of security controls. <!-- .element class="fragment" data-fragment-index="6" -->
- Verify <!-- .element class="fragment" data-fragment-index="7" -->
  - Verify requirements are met, issues are found, and security controls are implemented. <!-- .element class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_04.png)

---

<!-- .element class="split-screen-with-title" -->
# Threat Modeling

<div>

<div>

- Limitations of a network topology diagram: <!-- .element class="fragment" data-fragment-index="1" -->
  - Nature of the traffic not defined <!-- .element class="fragment" data-fragment-index="2" -->
  - Processes and interactions not defined <!-- .element class="fragment" data-fragment-index="3" -->
  - Monolithic depiction of network hosts and not what the hosts do <!-- .element class="fragment" data-fragment-index="4" -->
  - Threats not depicted <!-- .element class="fragment" data-fragment-index="5" -->
  - Concepts such as user profiles not depicted <!-- .element class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_06.png)

---

<!-- .element class="split-screen-with-title" -->
# Threat Modeling

<div>

<div>

- A Data Flow Diagram (DFD), as the name indicates, shows the flow of data through the system <!-- .element class="fragment" data-fragment-index="1" -->
  - External entities <!-- .element class="fragment" data-fragment-index="2" -->
  - Processes <!-- .element class="fragment" data-fragment-index="3" -->
  - Data stores <!-- .element class="fragment" data-fragment-index="4" -->
  - Data flows <!-- .element class="fragment" data-fragment-index="5" -->
- Larger systems usually have composite processes, which expand into their own DFD. <!-- .element class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_07.png)

---

<!-- .element class="split-screen-with-title" -->
# Threat Modeling

<div>

<div>

- Microsoft Threat Modeling Tool is a data flow diagram (DFD) design software that helps teams: <!-- .element class="fragment" data-fragment-index="1" -->
  - Communicate about the security design of their systems <!-- .element class="fragment" data-fragment-index="2" -->
  - Analyze those designs for potential security issues using a proven methodology <!-- .element class="fragment" data-fragment-index="3" -->
  - Suggest and manage mitigations for security issues <!-- .element class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_08.png)
Source: Microsoft

</div>

---

<!-- .element class="split-screen-with-title" -->
# Threat Modeling

<div>

<div>

- Example Scenario <!-- .element class="fragment" data-fragment-index="1" -->
  - A dev team is building Useless Web App™ <!-- .element class="fragment" data-fragment-index="2" -->
    - Really doesn't do anything except simple authentication (not even OAuth!) <!-- .element class="fragment" data-fragment-index="3" -->
  - Key components <!-- .element class="fragment" data-fragment-index="4" -->
    - SQL Database to store user data via JDBC API <!-- .element class="fragment" data-fragment-index="5" -->
    - Web server to host the app <!-- .element class="fragment" data-fragment-index="6" -->
    - Web service to broker communications between server and SQL DB <!-- .element class="fragment" data-fragment-index="7" -->
    - Browser client <!-- .element class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_09.png)
Source: Gamezebo

</div>

---

<!-- .element class="image-and-title" -->
# Threat Modeling

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_10.png)

---

<!-- .element class="main-title" -->
# Modeling a Web Application:

## STRIDE


NOTE:
Is there a relevant Ch. in the Wiley Network+ (N10-008) Study Guide?


---

<!-- .element class="split-screen-with-title" -->
# STRIDE

<div>

<div>

- As part of threat modeling, we should be able to understand and classify the many types of threats. <!-- .element class="fragment" data-fragment-index="1" -->
  - Remember, we are threat modeling in order to proactively find and resolve security issues across our systems. <!-- .element class="fragment" data-fragment-index="2" -->
- Refresher: What is a threat? <!-- .element class="fragment" data-fragment-index="3" -->
  - How is a threat different from a vulnerability, risk, or problem? <!-- .element class="fragment" data-fragment-index="4" -->
  - A "model" is a representation of a real threat. <!-- .element class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_11.png)

---

<!-- .element class="split-screen-with-title" -->
# STRIDE

<div>

<div>

- STRIDE is a threat modeling methodology for identifying and classifying threats to a system
- Acronym for
  - Spoofing
  - Tampering
  - Repudiation
  - Information Disclosure
  - Denial of Service (DoS)
  - Elevation of privilege
- Security professionals use STRIDE to help answer the question “What can go wrong in this system?”

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/29_11.png)

</div>

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 29 - Modeling a Web Application

- Course Overview
- Warmup
- Review
- Lecture:
  - Modeling a Web Application
- Demo <!-- .element style="color: red;" -->

---

<!-- .element class="main-title" -->
# Demo

## Threat modeling and DFD

NOTE:

### Import OVA File


### Demo: Threat modeling and DFD
