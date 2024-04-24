<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 28

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 28 - Log Clearing

- Course Overview<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - Persistence
- Lecture
  - Log Clearing
- Demo

---

<!-- .element class="split-screen-with-title" -->
# Course Overview

<div>

<div align="left" style="font-size: 40px">

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Module 6** - Threat Modeling & Analysis

- **Module 7** - Threat Hunting

- **Module 8** - Web Application Security

- **Module 9** - Penetration Testing

- **Module 10** - Final Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/00_01.png)<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)

</div>

</div>

---

<!-- .element class="title-with-text" -->
# Module 6 Labs

### Threat Modeling and Analysis

<div align="left" style="font-size: 45px">

- **Class 26** - Remote Code Execution

<br>

- **Class 27** - Persistence

<br>

- &shy;<!-- .element style="color: red;" -->**Class 28** - Log Clearing

<br>

- **Class 29** - Modeling a Web Application

<br>

- **Class 30** - N/A

</div>

---

<!-- .element class="split-screen-with-title" -->
# Module 6 Challenges

<div>

<div align="left" style="font-size: 38px">

- **Class 26** - Event Logging Tool Part 1 of 3

<br>

- **Class 27** - Event Logging Tool Part 2 of 3

<br>

- &shy;<!-- .element style="color: red;" -->**Class 28** - Event Logging Tool Part 3 of 3

<br>

- **Class 29** - Mock Interviews

<br>

- **Class 30** - Antivirus Evasion

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->

# Warmup

---

<!-- .element class="main-title" -->
# Review:

# Persistence

---

<!-- .element class="split-screen-with-title" -->
# TA0003: Persistence

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" --> **TA0003: Persistence**
  - Techniques used by threat actors to maintain access to a compromised system or network <!-- .element: class="fragment" data-fragment-index="2" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Various Techniques:**
    - Creating registry entries <!-- .element: class="fragment" data-fragment-index="4" -->
    - Scheduled tasks <!-- .element: class="fragment" data-fragment-index="5" -->
    - Backdoors <!-- .element: class="fragment" data-fragment-index="6" -->
    - Rootkits <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/26_14.png)
Source: ITBros

</div>

</div>

NOTE:
Visit T1059.001

---

<!-- .element class="split-screen-with-title" -->
# Modeling PsExec

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Can `Invoke-PsExec` be prevented from executing?**
  - Firstly, where is it originating? <!-- .element: class="fragment" data-fragment-index="2" -->
    - Within the LAN, or... <!-- .element: class="fragment" data-fragment-index="3" -->
    - Outside the LAN <!-- .element: class="fragment" data-fragment-index="4" -->
  - In a real engagement, the C2 server exists outside the network perimeter <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/27_01.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Modeling PsExec

<div>

<div>

- The C2 server is issuing commands to various malware payloads and compromised victim hosts from outside the LAN <!-- .element: class="fragment" data-fragment-index="1" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**What defenses can help us?**
  - Firewalls <!-- .element: class="fragment" data-fragment-index="3" -->
  - SIEM <!-- .element: class="fragment" data-fragment-index="4" -->
  - Group Policy <!-- .element: class="fragment" data-fragment-index="5" -->
  - Prevent privilege escalation <!-- .element: class="fragment" data-fragment-index="6" -->
  - IDS <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/27_01.png)

</div>

</div>

NOTE:

---

<!-- .element class="split-screen-with-title" -->
# PowerShell Empire

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**PowerShell Empire components**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Listener**:
    - Runs on the C2 server and awaits connection requests from compromised hosts. <!-- .element: class="fragment" data-fragment-index="3" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Agent**:
    - A program that maintains a connection between C2 and the compromised host. <!-- .element: class="fragment" data-fragment-index="5" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Stager**:
    - Small scripts that establish the initial connection to a compromised system. <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/27_04.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Atomic Testing Cycle

NOTE:
Is there a relevant Ch. in the Wiley Security+ (SY0-601) Study Guide?

---

<!-- .element class="split-screen-with-title" -->
# Atomic Testing

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" --> **Why is security testing important?**
  - Proactively identifies and addresses vulnerabilities
  - Simulates real-world attack scenarios
  - Enhances the ability to detect and respond to security incidents
  - Helps defenders adapt to the evolving global cyber threat landscape

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/27_03.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Post-Exploitation

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**The MITRE ATT&CK framework documents the attack techniques used in post-exploitation stages of the kill chain**
  - Control <!-- .element: class="fragment" data-fragment-index="2" -->
  - Execute <!-- .element: class="fragment" data-fragment-index="3" -->
  - Maintain <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**So far we've studied**
  - RCE <!-- .element: class="fragment" data-fragment-index="6" -->
  - Persistence <!-- .element: class="fragment" data-fragment-index="7" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**How to systematically simulate this?**
  - Learn from mistakes <!-- .element: class="fragment" data-fragment-index="9" -->

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/28_01.png)

---

<!-- .element class="image-and-title" -->
# Attack Lifecycle

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/28_02.png)<!-- .element style="width: 100%"-->

Source: FireEye

---

<!-- .element class="split-screen-with-title" -->
# Atomic Testing Cycle

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is the Atomic Testing Cycle?**
  - A phased approach to improving your cyber defenses by testing them. <!-- .element: class="fragment" data-fragment-index="2" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Levels of security team sophistication**:
    - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Level 1**: Just starting out, limited resources
    - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Level 2**: Starting to mature, some resources
    - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Level 3**: Advanced cybersecurity teams and resources

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/28_03.png)

NOTE:
All Atomic Tests by Tactic and Technique: <https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/Indexes/Indexes-Markdown/index.md>
Reading: <https://medium.com/mitre-attack/getting-started-with-attack-red-29f074ccf7e3>

---

<!-- .element class="split-screen-with-title" -->
# Adversary Emulation

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Matured security teams (Level 3)**
  - Already using the Atomic Testing Cycle should consider “adversary emulation” <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**In adversary emulation the red team executes the emulation engagement**
  - Gather threat intel <!-- .element: class="fragment" data-fragment-index="4" -->
  - Extract techniques <!-- .element: class="fragment" data-fragment-index="5" -->
  - Analyze and organize <!-- .element: class="fragment" data-fragment-index="6" -->
  - Develop tools and procedures <!-- .element: class="fragment" data-fragment-index="7" -->
  - Emulate the adversary <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/28_04.png)

Source: MITRE ATT&CK

</div>

</div>

NOTE:
Pull up and discuss MITRE ATT&CK's adversary emulation plan for APT3 and how defenders might use this.

---

<!-- .element class="split-screen-with-title" -->
# Team Colors

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Red Team**
  - Attempts to penetrate the network or exploit the network as a rogue internal attacker <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Blue Team**
  - Operates the security and monitoring systems with to detect and repel the red team <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**White Team**
  - Sets the parameters for the exercise <!-- .element: class="fragment" data-fragment-index="6" -->
  - Authorized to monitor or halt the exercise <!-- .element: class="fragment" data-fragment-index="7" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**Purple Teams**
  - Enhanced information sharing between the red and blue teams <!-- .element: class="fragment" data-fragment-index="9" -->
  - Maximizes each team's effectiveness <!-- .element: class="fragment" data-fragment-index="10" -->

</div>

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/28_05.png)

Source: DXC, CompTIACySA+

---

<!-- .element class="split-screen-with-title" -->
# Example Atomic Test Cycle

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Step 1: Select a test**
  - T1218.010 <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Step 2: Execute the test**
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**`Regsvr32.exe`** is a command-line program used to register and unregister OLE controls
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->Upon execution, **`calc.exe`** will be launched

</div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Step 3: Collect evidence**
  - What did your security tools observe? <!-- .element: class="fragment" data-fragment-index="7" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**Step 4: Develop detection**
  - Detect the event in your environment <!-- .element: class="fragment" data-fragment-index="9" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="10" -->**Step 5: Measure progress**
  - Measure your coverage against MITRE ATT&CK matrix <!-- .element: class="fragment" data-fragment-index="11" -->

</div>

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/28_06.png)

NOTE:
T1218.010 Atomic Test

---

<!-- .element class="image-and-title" -->
# Measuring Progress

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/28_09.png)

Source: Red Canary

NOTE:
Track your team's progress in a spreadsheet, makes for a useful KPI for upper management
Open up D3 Security's MITRE ATT&CK tracker spreadsheet and explain how this can be used as a “checklist” for executing Atomic Tests

---

<!-- .element class="image-and-title" -->
# Measuring Progress

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/28_10.png)

Source: Red Canary

NOTE:
Track your team's progress in a spreadsheet, makes for a useful KPI for upper management ;

---

<!-- .element class="main-title" -->
# Log Clearing

NOTE:
Is there a relevant Ch. in the Wiley ITF+ (FC0-U61) Study Guide?

---

<!-- .element class="split-screen-with-title" -->
# T1070.001 Log Clearing

<div>

<div>

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->**ATT&CK details**

- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**ID**: T1070.001
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Sub-technique of**: T1070
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Tactic**: Defense Evasion
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Platforms**: Windows
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**System Requirements**: Clearing the Windows event logs requires Administrator permissions
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Permissions Required**: Administrator
- &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**Defense Bypassed**: AV, HIPS, Log Analysis

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/26_14.png)

---

<!-- .element class="split-screen-with-title" -->
# Detecting Log Clearing

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What's our strategy?**
  - Detection by SIEM? <!-- .element: class="fragment" data-fragment-index="2" -->
  - Detection by IDS? <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Depends on how the attacker has entered**
  - Encrypted C2 traffic vs plaintext C2 traffic <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-28/slides/assets/28_11.png)

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 28 - Log Clearing

- Course Overview
- Warmup
- Review
- Lecture:
  - Log Clearing
- Demo <!-- .element style="color: red;" -->

---

<!-- .element class="title-and-subtitle" -->
# Demo:

- Ops Challenge 28: <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
  - Event Logging Tool (Part 3 of 3)
- Lab 28: <!-- .element: class="fragment highlight-current-red" data-fragment-index="2" -->
  - Reproduce and Mitigate a Log Clearing Attack

NOTE:

# Challenge 28

---

<!-- .element class="main-title" -->
# Demo & Lab

## Reproduce and Mitigate a Log Clearing Attack

NOTE:

### Import OVA File

### Demo: Reproduce and Mitigate a Log Clearing Attack
