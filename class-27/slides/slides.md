<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 27

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 27 - Persistence

- Course Overview<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - Remote Code Execution (RCE)
- Lecture
  - Persistence
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/00_01.png)<!-- .element style="width: 100%"-->
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

- &shy;<!-- .element style="color: red;" -->**Class 27** - Persistence

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

- **Class 26** - Event Logging Tool Part 1 of 3

<br>

- &shy;<!-- .element style="color: red;" -->**Class 27** - Event Logging Tool Part 2 of 3

<br>

- **Class 28** - Event Logging Tool Part 3 of 3

<br>

- **Class 29** - Mock Interviews

<br>

- **Class 30** - Antivirus Evasion

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Review:
## Remote Code Execution (RCE)

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/26_14.png)
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

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is RCE?**
  - A severe security vulnerability that allows an attacker to run code on a victim's system or network from a remote location <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Post-exploitation**
  - Stage of a cyberattack that occurs after an attacker has successfully gained access to a target system <!-- .element: class="fragment" data-fragment-index="4" -->
  - Examples of post-exploitation frameworks <!-- .element: class="fragment" data-fragment-index="5" -->
    - Powershell Empire <!-- .element: class="fragment" data-fragment-index="6" -->
    - Metasploit <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/26_15.png)
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/27_01.png)

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/27_02.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Modeling PsExec

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What logs does Invoke-PsExec generate?**
  - SIEM
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**What does Invoke-PsExec traffic look like?**
  - Network traffic analysis
  - Wireshark
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**If we know what logs look like, what can we do?**
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**If we know what the packets look like, what can we do?**

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/27_02.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Modeling PsExec

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**In addition to a traditional network topology, we need to depict traffic flows on the diagram**
  - Protocol of the traffic <!-- .element: class="fragment" data-fragment-index="2" -->
  - Direction of the traffic <!-- .element: class="fragment" data-fragment-index="3" -->
  - Entities interacting, such as users <!-- .element: class="fragment" data-fragment-index="4" -->
  - Explore various scenarios <!-- .element: class="fragment" data-fragment-index="5" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**We'll need a new kind of diagram for this (to be continued!)...**

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/27_02.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Case Study: Colonial Pipeline

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**DarkSide Attack Techniques**
  - Created a customized ransomware executable <!-- .element: class="fragment" data-fragment-index="2" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Custom ransomware executes an obfuscated **(encoded)** PowerShell command that deletes Shadow Volume Copies on the victim to prevent data file restoration

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/26_10.png) <!-- .element: class="fragment" data-fragment-index="4" -->

Source: Bleeping Computer <!-- .element: class="fragment" data-fragment-index="4" -->

Decodes to <!-- .element: class="fragment" data-fragment-index="5" -->
`Get-WmiObject Win32_Shadowcopy | ForEach-Object {$_.Delete();}` <!-- .element: class="fragment" data-fragment-index="5" -->

NOTE:
TA0008, TA0004

---

<!-- .element class="main-title" -->
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/26_14.png)
Source: ITBros

</div>

</div>

NOTE:
Visit T1059.001

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/27_03.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Atomic Testing

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**How do we perform security testing?**
  - Testing should be fast and easy <!-- .element: class="fragment" data-fragment-index="2" -->
  - Determine scope of testing <!-- .element: class="fragment" data-fragment-index="3" -->
  - Without a testing method <!-- .element: class="fragment" data-fragment-index="4" -->
    - Admins would just have to use a VM and pull 100 viruses to test their defenses <!-- .element: class="fragment" data-fragment-index="5" -->
    - Not realistic! <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/27_03.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Atomic Testing

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is Atomic Red Team?**
  - A library of simple tests that security teams can execute to test their defenses. <!-- .element: class="fragment" data-fragment-index="2" -->
  - It breaks down attack techniques into small, modular test cases. <!-- .element: class="fragment" data-fragment-index="3" -->
  - Aligns with the MITRE ATT&CK framework <!-- .element: class="fragment" data-fragment-index="4" -->
    - Tests are mapped to a tactic <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/27_03.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# PowerShell Empire

---

<!-- .element class="split-screen-with-title" -->
# PowerShell Empire

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is PowerShell Empire?**
  - A PowerShell post-exploitation framework used by penetration testers and red teams. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Deploys agents on compromised systems to establish command and control. <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Isn't Empire retired?**
  - Infamous for its use by nation-state APTs <!-- .element: class="fragment" data-fragment-index="5" -->
  - Actively maintained by BC Security <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/27_04.png)

</div>

</div>

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/27_04.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# PowerShell Empire

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Stager types**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Launcher stager**
    - Generates a one-liner stage0 launcher for an Empire agent <!-- .element: class="fragment" data-fragment-index="3" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Launcher_bat stager**
    - Generates a self-deleting `.BAT` file <!-- .element: class="fragment" data-fragment-index="5" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Macrostager**
    - Generates an office macro that launches an Empire stager. <!-- .element: class="fragment" data-fragment-index="7" -->
    - This macro can be embedded into any office document for the purposes of phishing. <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/27_04.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# PowerShell Empire

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**DLL stager**
  - Loads and executes a payload in the form of a Dynamic Link Library (DLL) on a target system <!-- .element: class="fragment" data-fragment-index="2" -->
  - These .DLLs are the key to running Empire in a process that's not powershell.exe <!-- .element: class="fragment" data-fragment-index="3" -->
  - The DLL establishes a connection with the attacker's C2 server <!-- .element: class="fragment" data-fragment-index="4" -->
  - Allows the attacker to send further instructions and control the compromised system <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-27/slides/assets/27_04.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Demo
