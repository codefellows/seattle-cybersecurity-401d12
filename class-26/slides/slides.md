<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 26

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 26 - Remote Code Execution

- Course Overview<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Review
  - Term 1
- Ops Challenge
- Lecture
  - Intro to Threat Modeling
  - Remote Code Execution (RCE)
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/00_01.png)
<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)

</div>

</div>

---

<!-- .element class="title-with-text" -->
# Module 6 Labs

### Threat Modeling and Analysis

<div align="left" style="font-size: 45px">

- &shy;<!-- .element style="color: red;" -->**Class 26** - Remote Code Execution

<br>

- **Class 27** - Persistence

<br>

- **Class 28** - Log Clearing

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


- &shy;<!-- .element style="color: red;" -->**Class 26** - Event Logging Tool Part 1 of 3

<br>

- **Class 27** - Event Logging Tool Part 2 of 3

<br>

- **Class 28** - Event Logging Tool Part 3 of 3

<br>

- **Class 29** - Mock Interviews

<br>

- **Class 30** - Antivirus Evasion

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Review: Term 1

---

<!-- .element class="image-and-title" -->
# SOC Roles and Interactions

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_01.png) <!-- .element style= "width: 20%" -->

Source: Exabeam

---

<!-- .element class="split-screen-with-title" -->
# Review: Term 1

<div align= "left">

<div>

- **Architecture Planning**
  - Connectivity
  - Tools
  - Deployment
  - Scalability
- **Security Controls**
  - OS harding and logging
  - Control plane logging
  - IAM
  - Endpoint security
  - Network security
  - Vulnerabilities
  - Secure configuration

</div>

<div>

- **Adapting Existing Processes and Functions**
  - Initial Event
  - Initial triage
  - Event validation
  - Investigation
  - Follow-up process and forensics

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_02.png)

Source: The Modern Cloud-Aware SOC, SIEM Workflow

</div>

</div>

---

<!-- .element class="main-title" -->
# Threat Analysis

---

<!-- .element class="split-screen-with-title" -->
# Careers in Threat Analysis

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Cyber threat analysts leverage skills and expertise of network engineering to:**
  - Mitigate and avoid cyberattacks <!-- .element: class="fragment" data-fragment-index="2" -->
  - Identify vulnerabilities <!-- .element: class="fragment" data-fragment-index="3" -->
  - Study digital forensics <!-- .element: class="fragment" data-fragment-index="4" -->
  - Conduct threat modeling <!-- .element: class="fragment" data-fragment-index="5" -->
  - Simulate attacks <!-- .element: class="fragment" data-fragment-index="6" -->
  - Recommend defenses <!-- .element: class="fragment" data-fragment-index="7" -->
  - Monitor networks <!-- .element: class="fragment" data-fragment-index="8" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="9" -->**Avg. US salary**
  - Entry level $84,000 <!-- .element: class="fragment" data-fragment-index="10" -->
  - Experienced $98,885-126,976 <!-- .element: class="fragment" data-fragment-index="11" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_03.png)
Source: Toolbox, DegreeQuery

</div>

</div>

NOTE:

- Why should we study threat modeling and analysis?
  - Cyber threat analysts are information security professionals who leverage skills and expertise of network engineering to mitigate and avoid cyberattacks on the organization or its employees.
  - Threat analysts identify vulnerabilities, study digital forensics, and conduct threat modeling in order to monitor and defend against threats faced by organizational infrastructure.

---

<!-- .element class="split-screen-with-title" -->
# Threat Analysis

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is Cyber Threat Analysis?**
  - A process used by cybersecurity threat analysts to study and align a particular organization's defenses against its potential or realized cyber threats <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Threat analysis aims to answer:**
  - What are we working on? <!-- .element: class="fragment" data-fragment-index="4" -->
  - What are the things that can go wrong? <!-- .element: class="fragment" data-fragment-index="5" -->
  - How do we go about problems that occur? <!-- .element: class="fragment" data-fragment-index="6" -->
  - Did we do a good job? <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_03.png)
Source: Toolbox, DegreeQuery

</div>

</div>

NOTE:

- What is threat analysis?
  - Cyber threat analysis is a process used by cybersecurity threat analysts to study and align a particular organization's defenses against its potential or realized cyber threats
  - According to software engineer Goran Aviani, the goal of a threat analysis is to answer the four questions of:
    - What are we working on?
    - What are the things that can go wrong?
    - How do we go about problems that occur?
    - Did we do a good job?

---

<!-- .element class="split-screen-with-title" -->
# Threat Modeling

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is Cyber Threat Modeling?**
  - A structured approach to identifying, assessing, and mitigating cybersecurity threats and vulnerabilities <!-- .element: class="fragment" data-fragment-index="2" -->
  - A critical process for improving an organization's security posture <!-- .element: class="fragment" data-fragment-index="3" -->
  - Allows organizations to anticipate and address potential threats <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_04.png)
Source: Coalfire

</div>

</div>

NOTE:

- What is threat modeling?
  - Cyber threat modeling is the structured process used to determine potential security threats and weaknesses, assess risk levels per threat and implement mitigations against specific threats.

---

<!-- .element class="split-screen-with-title" -->
# Threat Modeling Methodologies

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**STRIDE**
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**DREAD**
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**PASTA**
- Trike <!-- .element: class="fragment" data-fragment-index="4" -->
- VAST <!-- .element: class="fragment" data-fragment-index="5" -->
- Attack Tree <!-- .element: class="fragment" data-fragment-index="6" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Common Vulnerability Scoring System (CVSS)**
- T-MAP <!-- .element: class="fragment" data-fragment-index="8" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="9" -->**OCTAVE**
- Quantitative Threat Modeling Method <!-- .element: class="fragment" data-fragment-index="10" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_04.png)
Source: Coalfire

</div>

</div>

---

<!-- .element class="main-title" -->
# Case Study:  Colonial Pipeline

---

<!-- .element class="split-screen-with-title" -->
# Case Study: Colonial Pipeline

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What Happened?**
  - Colonial Pipeline suffered a ransomware attack by the DarkSide group in May 2021. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Colonial Pipeline paid a $4.4 million ransom in Bitcoin to the attackers to receive a decryption key. <!-- .element: class="fragment" data-fragment-index="3" -->
  - The attack caused fuel shortages and panic buying along the U.S. East Coast <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_06.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_07.png)
Source: wrcbtv

</div>

</div>

NOTE:
Share with students the technical breakdown of DarkSide: <https://www.bleepingcomputer.com/news/security/darkside-new-targeted-ransomware-demands-million-dollar-ransoms/>

---

<!-- .element class="text-and-image" -->
# Case Study: Colonial Pipeline

Attack Timeline

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_05.png)

Source: [Analyst1](https://analyst1.com/the-colonial-pipeline-ransomware-attack-one-year-later/)

---

<!-- .element class="split-screen-with-title" -->
# Case Study: Colonial Pipeline

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Who's DarkSide?**
  - A ransomware-as-a-service (RaaS) group <!-- .element: class="fragment" data-fragment-index="2" -->
  - The group is known for using a "double extortion" tactic <!-- .element: class="fragment" data-fragment-index="3" -->
  - Announced in May 2021 that it was withdrawing from ransomware activities. <!-- .element: class="fragment" data-fragment-index="4" -->
  - They are just one example of the many ransomware groups. <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_08.png)
Source: Bleeping Computer

</div>

</div>

---

<!-- .element class="text-and-image" -->
# Case Study: Colonial Pipeline

DarkSide Attack Techniques

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_09.png) <!-- .element: class="fragment" data-fragment-index="1" -->

Source: [Mandiant](https://www.mandiant.com/resources/blog/shining-a-light-on-darkside-ransomware-operations) <!-- .element: class="fragment" data-fragment-index="1" -->

NOTE:
TA0008, TA0004

---

<!-- .element class="split-screen-with-title" -->
# Case Study: Colonial Pipeline

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**DarkSide Attack Techniques**
  - Created a customized ransomware executable <!-- .element: class="fragment" data-fragment-index="2" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Custom ransomware executes an obfuscated **(encoded)** PowerShell command that deletes Shadow Volume Copies on the victim to prevent data file restoration

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_10.png) <!-- .element: class="fragment" data-fragment-index="4" -->

Source: Bleeping Computer <!-- .element: class="fragment" data-fragment-index="4" -->

Decodes to <!-- .element: class="fragment" data-fragment-index="5" -->
`Get-WmiObject Win32_Shadowcopy | ForEach-Object {$_.Delete();}` <!-- .element: class="fragment" data-fragment-index="5" -->

NOTE:
TA0008, TA0004

---

<!-- .element class="split-screen-with-title" -->
# Case Study: Colonial Pipeline

<div>

<div>

- DarkSide is believed to be based in Easter Europe but believed to be directly state-sponsored <!-- .element: class="fragment" data-fragment-index="1" -->
- DarkSide avoids targets in certain geographic locations by checking their system language settings <!-- .element: class="fragment" data-fragment-index="2" -->
- Similar to what is used in REvil and also GandCrab <!-- .element: class="fragment" data-fragment-index="3" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_11.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_12.png)
Source: Bleeping Computer

</div>

</div>

NOTE:
TA0008, TA0004

Share this link with students: https://www.mandiant.com/resources/blog/shining-a-light-on-darkside-ransomware-operations

---

<!-- .element class="image-and-title" -->
# ICS Threat Model

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_13.png)
Source: Slideshare

NOTE:

TA0008, TA0004
Consider drawing together an ICS topology and discussing threats

---

<!-- .element class="split-screen-with-title" -->
# Stages of Exploitation

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Pre-Exploitation**
  - OS Identification <!-- .element: class="fragment" data-fragment-index="2" -->
  - Software Identification <!-- .element: class="fragment" data-fragment-index="3" -->
  - Version Identification <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Exploitation**
  - Memory preparation <!-- .element: class="fragment" data-fragment-index="6" -->
  - Vulnerability preparation <!-- .element: class="fragment" data-fragment-index="7" -->
  - Memory disclosure <!-- .element: class="fragment" data-fragment-index="8" -->
  - Payload preparation <!-- .element: class="fragment" data-fragment-index="9" -->
  - Code Execution <!-- .element: class="fragment" data-fragment-index="10" -->

</div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="11" -->**Post-Exploitation**
  - Return Oriented Programming <!-- .element: class="fragment" data-fragment-index="12" -->
  - Payload Execution <!-- .element: class="fragment" data-fragment-index="13" -->
  - Continuation of Execution <!-- .element: class="fragment" data-fragment-index="14" -->
  - Persistence <!-- .element: class="fragment" data-fragment-index="15" -->

</div>

</div>

---

<!-- .element class="main-title" -->
# Remote Code Execution

---

<!-- .element class="split-screen-with-title" -->
# T1059.001

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" --> **T1059.001: Command and Scripting Interpreter: PowerShell**
  - Adversaries use PowerShell to execute malicious commands and scripts.<!-- .element: class="fragment" data-fragment-index="2" -->
  - Wide range of actions: <!-- .element: class="fragment" data-fragment-index="3" -->
    - Running malware <!-- .element: class="fragment" data-fragment-index="4" -->
    - Downloading and executing files <!-- .element: class="fragment" data-fragment-index="5" -->
  - Examples <!-- .element: class="fragment" data-fragment-index="6" -->
    - &shy; <!-- .element: class="fragment" data-fragment-index="7" -->`Start-Process` - runs an executable
  - &shy;<!-- .element: class="fragment" data-fragment-index="8" -->`Invoke-Command` - runs a command locally or on a remote computer

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_14.png)

Source: ITBros

</div>

</div>

NOTE:

Visit T1059.001

- What is remote code execution?
  - Remote code execution (RCE) is a class of security vulnerabilities that allows a malicious actor to execute any code of their choice on a remote machine over LAN, WAN, or the Internet

---

<!-- .element class="split-screen-with-title" -->
# Remote Code Execution

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" --> **MS15-011**
  - Addressed a bypass vulnerability in the way Group Policy settings were applied in Windows <!-- .element: class="fragment" data-fragment-index="2" -->
  - Vulnerability could allow remote code execution <!-- .element: class="fragment" data-fragment-index="3" -->
  - An attacker convinces a user with a domain-configured system to connect to an attacker-controlled network <!-- .element: class="fragment" data-fragment-index="4" -->
  - An attacker who exploited this vulnerability could take complete control of an affected system <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_15.png)
Source: ITBros

</div>

</div>

NOTE:

- Why should we prepare to defend against remote code execution?
  - Discuss MS15-011: Vulnerability in Group Policy could allow remote code execution: February 10, 2015

---

<!-- .element class="split-screen-with-title" -->
# Remote Code Execution

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" --> **Why is PowerShell often used in attacks?**
  - Represents one of the most interesting and powerful languages for a pentesting purpose <!-- .element: class="fragment" data-fragment-index="2" -->
  - Natively integrated into Windows <!-- .element: class="fragment" data-fragment-index="3" -->
  - Access to a lot of system information and configuration settings <!-- .element: class="fragment" data-fragment-index="4" -->
  - Exploit and Payload execution <!-- .element: class="fragment" data-fragment-index="5" -->
  - Ability to bypass security controls <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_15.png)
Source: ITBros

</div>

</div>

NOTE:

- Why is PowerShell important in cybersecurity?
  - "PowerShell represents one of the most interesting and powerful languages for a pentesting purpose."
  - "...for us, as pentesters, PowerShell represent a powerful shell and scripting language which is present (in most cases from windows 7, it’s integrated by default) on our pentest targets and provide to us specially a powerful post-exploitation “tool/language” that can give us so much power and a very big attack surface/possibility." -Infosec Institute

---

<!-- .element class="split-screen-with-title" -->
# Remote Code Execution

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is RCE?**
  - A severe security vulnerability that allows an attacker to run code on a victim's system or network from a remote location <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Post-exploitation**
  - Stage of a cyberattack that occurs after an attacker has successfully gained access to a target system <!-- .element: class="fragment" data-fragment-index="4" -->
  - Examples of post-exploitation frameworks <!-- .element: class="fragment" data-fragment-index="5" -->
    - Powershell Empire <!-- .element: class="fragment" data-fragment-index="6" -->
    - Metasploit <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_15.png)
Source: ITBros

</div>

</div>

NOTE:

- What is remote code execution?
  - Remote code execution (RCE) is a class of security vulnerabilities that allows a malicious actor to execute any code of their choice on a remote machine over LAN, WAN, or the Internet
- What is a post-exploitation framework?
  - Post-exploitation includes the phases of operation once a victim's system has been compromised by the attacker.
  - Examples of post-exploitation frameworks include Empire and Metasploit.

---

<!-- .element class="split-screen-with-title" -->
# Remote Code Execution

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is Powershell Empire?**
  - A post-exploitation framework that simplifies the control of compromised systems and post-exploitation activities <!-- .element: class="fragment" data-fragment-index="2" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Components:**
    - Stagers <!-- .element: class="fragment" data-fragment-index="4" -->
    - Listeners <!-- .element: class="fragment" data-fragment-index="5" -->
    - Agents <!-- .element: class="fragment" data-fragment-index="6" -->
    - Modules <!-- .element: class="fragment" data-fragment-index="7" -->
  - Uses encrypted communication between agents and the server to evade detection <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_15.png)
Source: ITBros

</div>

</div>

NOTE:

- What is PowerShell Empire?
  - PowerShell Empire is a pure PowerShell post-exploitation agent built on cryptologically-secure communications and a flexible architecture.
  - Empire implements the ability to run PowerShell agents without needing `powershell.exe`
  - Includes rapidly deployable post-exploitation modules ranging from key loggers to Mimikatz
  - Supports adaptable communications to evade network detection
  - Presented in an accessible framework (unified)

---

<!-- .element class="split-screen-with-title" -->
# Remote Code Execution

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is PsExec?**
  - A legitimate and widely used command-line utility that allows administrators to execute processes on remote systems <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Invoke-PsExec**
  - A cmdlet that allows an attacker to remotely execute commands or scripts on a target Windows system, using PsExec. <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**How can we defend against RCE threats?**

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-26/slides/assets/26_15.png)
Source: ITBros

</div>

NOTE:

- What is Invoke-PsExec?
  - Invoke-PsExec is a cmdlet that lets you execute PowerShell and batch/cmd.exe code asynchronously on target Windows computers, using PsExec.exe.
  - PsExec can be downloaded from the SysInternals suite on Microsoft's site
  - Remember, a batch file ends in .bat and contains non-PowerShell Windows commands only in the form of a script.
- How can we defend against RCE threats?
  - Patch and update software
  - Application security testing
  - Network segmentation
  - Least privilege
  - Web App Firewalls
  - Input Validation and sanitization
  - Firewalls and IDS systems
  - User training
  - Monitoring and Logging

---

<!-- .element class="main-title" -->
# Demo

NOTE:

DO:

- From Windows Server, run Invoke-PsExec to run notepad.exe.
- Next, run Invoke-PsExec to run notepad.exe on Windows 10.
- On Windows 10, access event viewer and take a look at Sysmon logs.
- Walk students through the initial setup steps for the lab environment.
