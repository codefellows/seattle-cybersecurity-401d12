<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 41

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

Daily TODOs

- Update the class number for each video recording
- Move the dragon icon to the current day
- Hide/unhide slides to show as necessary
- Toggle presentation mode on and screen share this first slide when you initialize recording on Zoom to indicate class number

---

<!-- .element class="split-screen-with-title" -->

## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- **Module 6** - Threat Modeling & Analysis

- **Module 7** - Threat Hunting

- **Module 8** - Web Application Security

- &shy;<!-- .element style="color: red;" -->**Module 9** - Penetration Testing

- **Module 10** - Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/0_01.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-with-text" -->
## Module 9 Labs

### Penetration Testing

<div align="left" style="font-size: 45px">

- &shy;<!-- .element style="color: red;" -->**Class 41** - Reconnaissance with Maltego

<br>

- **Class 42** - Pass the Hash with Mimikatz

<br>

- **Class 43** - Traffic Sniffing with Ettercap

<br>

- **Class 44** - Pentest Practice 1 of 2

<br>

- **Class 45** - Pentest Practice 2 of 2

</div>

---

<!-- .element class="split-screen-with-title" -->
## Module 9 Challenges

<div>

<div align="left" style="font-size: 35px">

- &shy;<!-- .element style="color: red;" -->**Class 41** - Attack Tools Part 1 of 3

<br>

- **Class 42** - Attack Tools Part 2 of 3

<br>

- **Class 43** - Attack Tools Part 3 of 3

<br>

- **Class 44** - Create a Port Scanner

<br>

- **Class 45** - Create a Banner Grabber

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/3_0.png)

---

<!-- .element class="main-title" -->
# Review: Vulnerability Scanning

---

<!-- .element class="split-screen-with-title" -->
# Vulnerability Analyst

<div>

<div>

A vulnerability analyst security professional that detects weaknesses in networks and then takes measures to help the organization correct and strengthen the system's security levels.

- Develops risk-based mitigation strategies for networks, operating systems, and applications
- Organize network-based scans to identify possible network security attacks and host-based scans to identify vulnerabilities in workstations, servers, and other network hosts.
- Salary range: $75,000-92,600
- Demand: From 2016 to 2026, CompTIA projects an increase of 19 percent with 17,917 net new jobs expected during that 10-year period.

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-40/slides/assets/9_0.png)
Source: Technofaq.org

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Vulnerability Assessments

<div>

<div>

- A vulnerability is a weakness in an information system, system security procedures, internal controls, or implementation that could be exploited or triggered by a threat source
  - Important to differentiate vulnerability, exploit, and risk.
  - Not all vulnerabilities are likely to be exploited or high risk.
  - Prioritize your vulnerabilities.
- Common Weakness Enumeration (CWE) is a community-developed list of software and hardware weakness types

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-40/slides/assets/10_0.png)
Source: CodedX

</div>

</div>

NOTE:
Apart from these misconfigurations, when running a vulnerability assessment on your network you might find several security issues with a wide range of software and hardware including:
Default passwords on certain devices
Unnecessary services running on some devices
Running web services that contain known vulnerabilities
Dangerous applications such as peer-to-peer applications
Third-party applications that are a vulnerability to known exploits.

---

<!-- .element class="split-screen-with-title" -->
# Vulnerability Assessments

<div>

<div>

- Tenable's Nessus is a commercial vulnerability scanning software
  - Free for non-enterprise use
  - “As part of the Nessus family, Nessus® Essentials (formerly Nessus Home) allows you to scan your environment (up to 16 IP addresses per scanner) with the same high-speed, in-depth assessments and agentless scanning convenience that Nessus subscribers enjoy.”

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-40/slides/assets/12_0.png)
Source: Security-Database

</div>

</div>

NOTE:
Apart from these misconfigurations, when running a vulnerability assessment on your network you might find several security issues with a wide range of software and hardware including:
Default passwords on certain devices
Unnecessary services running on some devices
Running web services that contain known vulnerabilities
Dangerous applications such as peer-to-peer applications
Third-party applications that are a vulnerability to known exploits.

---

<!-- .element class="main-title" -->
# Pentester Careers

---

<!-- .element class="split-screen-with-title" -->
# Pentester Careers

<div>

<div>

- Penetration testers perform simulated cyber attacks against your computer system to check for exploitable vulnerabilities and communicate findings
- Not entry-level
- U.S. job openings: 13,753
  - Penetration tester
  - Senior penetration tester
  - Network relations consultant
  - Application security analyst
- The average salary for a penetration tester is $103,000 a year

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/9_0.png)
Source: Cyberseek.org, Odiseageek, Hacker Web Security

</div>

</div>

---

<!-- .element class="main-title" -->
# Penetration Testing

---

<!-- .element class="split-screen-with-title" -->
# Penetration Testing

<div>

<div>

- Why do organizations request penetration testing?
  - Compliance
  - Confidentiality, revenue, goodwill
  - Verify secure configurations
  - Security training
  - Testing new technology

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/11_0.png)
Source: Cyberseek.org, Odiseageek, Hacker Web Security

</div>

---

<!-- .element class="split-screen-with-title" -->
# Outdated Terms

<div>

<div>

- An ethical hacker is someone who performs the legal exploitations of vulnerabilities for companies with their express permission
  - Not a professional job title
  - Not a useful industry terminology
- Wearing hats (outdated role designations)
  - Black hat hackers circumvent computer defenses illegally
  - White hat hackers are ethical professionals paid to circumvent computer defenses
  - Gray hat hackers are on the fence

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/12_0.png)
Source: Cyberseek.org, Odiseageek, Hacker Web Security

</div>

</div>

NOTE:
The security industry is full of jargon, and a lot of it is outdated. Here are some example terms that you should not use in a professional capacity.

---

<!-- .element class="split-screen-with-title" -->
# Terms

<div>

<div>

- An ethical hacker is someone who performs the legal exploitations of vulnerabilities for companies with their express permission
  - Not a professional job title
  - Not a useful industry terminology
- A penetration test is formalized hacking process where vulnerabilities are discovered and exploited
  - Simulate real-world attacks
  - Findings are documented and reported

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/13_0.png)
Source: Cyberseek.org, Odiseageek, Hacker Web Security

</div>

</div>

NOTE:

Pentester is a more specific role than ethical hacker, which is broader. Also, pentester is an actual job title. Ethical hacker is not (usually).

---

<!-- .element class="split-screen-with-title" -->
# Penetration Testing

<div>

<div>

- Security testing
  - Not a penetration test
  - Test software behavior for security problems
  - Bring an outdated system up to date
  - Software security testing during SDLC

- Vulnerability testing
  - Not a penetration test
  - Finding vulnerabilities but not exploiting them

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/14_0.png)
Source: Cyberseek.org, Odiseageek, Hacker Web Security

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Penetration Testing

<div>

<div>

- Pentest stages (Imperva version)
  - Phase 1: Planning & Reconnaissance
    - Define scope and goals of test
    - Gather intelligence on target
  - Phase 2: Scanning
    - How will a target application respond
      - Static analysis
      - Dynamic analysis
    - Enumeration

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/15_0.png)
Source: Cyberseek.org, Odiseageek, Hacker Web Security

</div>

</div>

NOTE:
Disclaimer: You'll see different variations on the stages of a pentest depending on who you ask.

---

<!-- .element class="split-screen-with-title" -->
# Penetration Testing

<div>

<div>

- Pentest stages (Imperva version ctd.)
  - Phase 3: Gaining Access
    - Social engineering
    - Web app attacks
  - Phase 4: Maintaining Access
    - Achieving persistence = APT
  - Phase 5: Analysis
    - Compile results of testing into reports
      - Vulnerabilities discovered and exploited
      - Sensitive data/systems accessed

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/16_0.png)
Source: Cyberseek.org, Odiseageek, Hacker Web Security

</div>

</div>

---

<!-- .element class="main-title" -->
# Phase 1: Planning & Reconnaissance

---

<!-- .element class="split-screen-with-title" -->
# Phase 1: Plan & Recon

<div>

<div>

- Planning
  - How will we approach this pentest?
  - What does the client need from us?
    - Report deliverables
      - Offensive Security Pentest Report
- Scope of work
  - Rules of engagement dictate in clear, unambiguous terms the limits to the pentest engagement
    - Example: Allowed to access a system but not change it or damage it

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/18_0.png)
Source: Finsmes

</div>

</div>

NOTE:
Take a look at the sample pentest report and emphasize that pentesting isn't all about showing off your offensive security skills. It's mostly reporting; 80% of your time is spent writing reports. Share this link with class.

---

<!-- .element class="split-screen-with-title" -->
# Phase 1: Plan & Recon

<div>

<div>

- Pentesters perform reconnaissance against their target in order to gain more information about what they're about to attack
  - Military lingo is “targeting”
- Types of reconnaissance
  - Passive: OSINT, observing, and sniffing. Information Gathering
    - Open Source Intelligence (OSINT) consists of publicly available information on the target
  - Active: Interacting with target and probing network for weaknesses

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/19_0.png)
Source: Quantika14

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Phase 1: Plan & Recon

<div>

<div>

- Desired intelligence and outcomes
  - Company background
  - Document: Penetration testing plan
  - Penetration test objectives and scope
  - Objectives
    - List exactly what will be tested
    - Mutually agreed boundaries
    - Exclusions and constraints
    - Downtime and affected parties
    - Approach and documentation
    - Key findings
    - Business metrics and impact

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/20_0.png)
Source: Quantika14

</div>

</div>

---

<!-- .element class="main-title" -->
# Maltego

---

<!-- .element class="split-screen-with-title" -->
# Maltego

<div>

<div>

- How can we perform target investigation to learn more about a company and its web footprint?
- "Maltego is an open source intelligence (OSINT) and graphical link analysis tool for gathering and connecting information for investigative tasks."
  - Desktop client
  - Supports data integration
- A Maltego object/entity is either:
  - A person, company, domain, etc.
  - An artifact of online activity
- A Maltego transform helps the user discover relationships to existing entities

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/22_0.png)
Source: ThreatMiner

</div>

</div>

---

<!-- .element class="main-title" -->
# Demo
