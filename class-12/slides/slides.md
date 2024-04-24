<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 12

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 12 - Log Analysis with Splunk

- Course Overview<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - Foundational SIEM Operations
- Lecture
  - Log Analysis with Splunk
- Demo

---

<!-- .element class="split-screen-with-title" -->
## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- **Module 1** - Governance, Risk and Compliance (GRC)

- **Module 2** - Data Security

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Module 3** - Security Operations

- **Module 4** - Cloud Security

- **Module 5** - Midterm Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/00_01.png)
<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)

</div>

</div>

---

<!-- .element class="title-with-text" -->
# Module 3 Labs

### Security Operations

<div align="left" style="font-size: 45px">

- **Class 11** - Foundational SIEM Operations

<br>

- &shy;<!-- .element style="color: red;" -->**Class 12** - Log Analysis with Splunk

<br>

- **Class 13** - Reconstructing a Cloud Attack

<br>

- **Class 14** - Intrusion Detection

<br>

- **Class 15** - CCW3: Networking

</div>

---

<!-- .element class="split-screen-with-title" -->
# Module 3 Challenges

<div>

<div align="left" style="font-size: 38px">

- **Class 11** - Network Security Tool Pt. 1 of 3

<br>

- &shy;<!-- .element style="color: red;" -->**Class 12** - Network Security Tool Pt. 2 of 3

<br>

- **Class 13** - Network Security Tool Pt. 3 of 3

<br>

- **Class 14** - Mock Interviews

<br>

- **Class 15** - Brute Force Attacks

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Ops Challenge

---

<!-- .element class="main-title" -->
# Review:

## Foundational SIEM Ops

---

<!-- .element class="split-screen-with-title" -->
# SOC Concepts

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Security Operations Center (SOC)**
  - A central team that monitors security infrastructure across the organization.
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**What does a SOC do?**
  - Security Monitoring <!-- .element: class="fragment" data-fragment-index="3" -->
  - Risk management <!-- .element: class="fragment" data-fragment-index="4" -->
  - Incident response <!-- .element: class="fragment" data-fragment-index="5" -->
  - Threat intelligence <!-- .element: class="fragment" data-fragment-index="6" -->
  - Security Tool Management <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/11_06.png)
Source: Medium

</div>

</div>

NOTE:

- Security information and event management software
  - A “SIEM” is defined as a group of complex technologies that together provide a bird’s-eye view into an infrastructure.
- Performs these core functions for a SOC:
  - Event and log collection
  - Layered centric views or heterogeneous
  - Normalization
  - Correlation
  - Adaptability (scalable)
  - Reporting and alerting
  - Log management
- Key takeaways
  - A “SIEM” is defined as a group of complex technologies that together provide a bird’s-eye view into an infrastructure.
  - Provides centralized security event management
  - Provides correlation and normalization for context and alerting
  - Provides reporting on all ingested data
  - Can take in data from virtually any vendor or in-house applications

---

<!-- .element class="split-screen-with-title" -->
# Splunk Architecture

<div>

<div>

- An index is a repository for data. <!-- .element: class="fragment" data-fragment-index="1" -->
  - Indexes reside in flat files on the indexer, which transforms raw data into searchable events. <!-- .element: class="fragment" data-fragment-index="2" -->
- Your lab VM comes preloaded with three indexes that are data-populated: <!-- .element: class="fragment" data-fragment-index="3" -->
  - default <!-- .element: class="fragment" data-fragment-index="4" -->
  - botsv1 <!-- .element: class="fragment" data-fragment-index="5" -->
  - mordor <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/11_09.png)
Source: Splunk

</div>

</div>

NOTE:

- Splunk Indexer: Parsing data and Indexing the data
  - Splunk Indexer tool helps the data to be converted into events and indexed so that it is easy for performing search operations efficiently.
  - Data from forwarders gets parsed (incl. unwanted data removed) then index it.

---

<!-- .element class="main-title" -->
# Log Analysis with Splunk

---

<!-- .element class="split-screen-with-title" -->
# Outline

<div>

<div>

- Website defacement <!-- .element: class="fragment" data-fragment-index="1" -->
- Cyber Kill Chain <!-- .element: class="fragment" data-fragment-index="2" -->
- Web Vulnerability Scanners <!-- .element: class="fragment" data-fragment-index="3" -->
- OSINT <!-- .element: class="fragment" data-fragment-index="4" -->
- Brute Force attack <!-- .element: class="fragment" data-fragment-index="5" -->
- Dynamic DNS (DDNS) <!-- .element: class="fragment" data-fragment-index="6" -->
- Splunk commands <!-- .element: class="fragment" data-fragment-index="7" -->
- Boss of the SOC <!-- .element: class="fragment" data-fragment-index="8" -->
- Demo <!-- .element: class="fragment" data-fragment-index="9" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_01.png)

</div>

NOTE:
<https://www.blueshoon.com/the-5-funniest-hacked-website-defacements-ive-ever-seen/>

---

<!-- .element class="split-screen-with-title" -->
# Advanced Persistent Threats

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Advanced Persistent Threat (APT)**
  - Employ advanced and sophisticated hacking techniques, tools and tactics <!-- .element: class="fragment" data-fragment-index="2" -->
  - Attackers maintain unauthorized access for extended periods <!-- .element: class="fragment" data-fragment-index="3" -->
  - Operate stealthily, making detection challenging by disguising their activities <!-- .element: class="fragment" data-fragment-index="4" -->
  - Highly targeted, focusing on specific organizations, industries, or individuals. <!-- .element: class="fragment" data-fragment-index="5" -->
  - Many APTs are believed to have connections to nation-states, providing them with significant resources. <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_02.png)
Source: FireEye

</div>

</div>

NOTE:

- An advanced persistent threat (APT) is “a skilled and determined cyber criminal [who] can use multiple vectors and entry points to navigate around defenses, breach your network in minutes and evade detection for months. APTs present a challenge for organizational cyber security efforts.” -FireEye

Visit <https://www.fireeye.com/current-threats/apt-groups.html>

---

<!-- .element class="split-screen-with-title" -->
# Website Defacement

<div>

<div>

- Typically a form of hacktivism <!-- .element: class="fragment" data-fragment-index="1" -->
- The attacker infiltrates a web server and alters the front page to send a message <!-- .element: class="fragment" data-fragment-index="2" -->
- A hacktivist uses offensive security skills to influence policy and attempt to bring about social change <!-- .element: class="fragment" data-fragment-index="3" -->
  - Example: Anonymous, a decentralized international activist/hacktivist movement <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_03.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_04.png)

</div>

</div>

NOTE:

- Web site defacement is typically a form of hacktivism, where the attacker infiltrates a web server and alters the front page to send a message
- A hacktivist uses offensive security skills to influence policy and attempt to bring about social change
  - Example: Anonymous, a decentralized international activist/hacktivist movement

This is a fun and relevant topic.
<https://www.blueshoon.com/the-5-funniest-hacked-website-defacements-ive-ever-seen/>

---

<!-- .element class="split-screen-with-title" -->
# Cyber Kill Chain

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->A security model outlining the sequential phases of a cyber attack
- Used by defenders to plan ways to interrupt or “break” the cyber kill chain and hopefully thwart the attack entirely <!-- .element: class="fragment" data-fragment-index="2" -->
- Originally developed by Lockheed Martin <!-- .element: class="fragment" data-fragment-index="3" -->
- Today's lab will be structured around the sequential phases of a cyber kill chain <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_05.png)
Source: Lockheed Martin

</div>

</div>

NOTE:

- What is the Cyber Kill Chain?
  - A cyber kill chain is a security model outlining the sequential phases of a cyber attack
  - Used by defenders to plan ways to interrupt or “break” the cyber kill chain and hopefully thwart the attack entirely
  - Originally developed by Lockheed Martin
  - Today’s lab will be structured around the sequential phases of a cyber kill chain

---

<!-- .element class="split-screen-with-title" -->
# Cyber Kill Chain

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Stages of the Lockheed Martin Cyber Kill Chain:**
  - Reconnaissance <!-- .element: class="fragment" data-fragment-index="2" -->
  - Weaponization <!-- .element: class="fragment" data-fragment-index="3" -->
  - Delivery <!-- .element: class="fragment" data-fragment-index="4" -->
  - Exploitation <!-- .element: class="fragment" data-fragment-index="5" -->
  - Installation <!-- .element: class="fragment" data-fragment-index="6" -->
  - Command and Control <!-- .element: class="fragment" data-fragment-index="7" -->
  - Actions on Objectives <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_06.png)
Source: Lockheed Martin

</div>

</div>

NOTE:

- Stages of the Lockheed Martin Cyber Kill Chain:
  - Reconnaissance
  - Weaponization
  - Delivery
  - Exploitation
  - Installation
  - Command and Control
  - Actions on Objectives

---

<!-- .element class="split-screen-with-title" -->
# Cyber Kill Chain

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Stage 1: Reconnaissance**
  - Attacker is assessing the target from outside <!-- .element: class="fragment" data-fragment-index="2" -->
  - Cost-benefit analysis <!-- .element: class="fragment" data-fragment-index="3" -->
  - Gathering information <!-- .element: class="fragment" data-fragment-index="4" -->
    - Active information gathering <!-- .element: class="fragment" data-fragment-index="5" -->
    - Passive information gathering <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_06.png)
Source: Lockheed Martin

</div>

</div>

NOTE:

- Malicious actor identifies a target and explores vulnerabilities and weaknesses that can be exploited within the network
- Attacker may harvest login credentials or gather other information
  - Email addresses
  - User IDs
  - Physical locations
  - Software applications and OS details
- The more information the attacker is able to gather during the Reconnaissance phase
- The more sophisticated and convincing the attack will be and the higher the likelihood of success.

---

<!-- .element class="split-screen-with-title" -->
# Cyber Kill Chain

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Stage 2: Weaponization**
  - Threat actor develops malware payload designed to target newly-discovered vulnerabilities <!-- .element: class="fragment" data-fragment-index="2" -->
  - Tools customized to target network <!-- .element: class="fragment" data-fragment-index="3" -->
    - What will work? <!-- .element: class="fragment" data-fragment-index="4" -->
    - How will I develop it? <!-- .element: class="fragment" data-fragment-index="5" -->
    - Can I source the weapon from the dark web? <!-- .element: class="fragment" data-fragment-index="6" -->
    - Can I tailor it to the target? <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_06.png)
Source: Lockheed Martin

</div>

</div>

NOTE:

- The attacker creates an attack vector
  - Remote access malware, ransomware, virus or worm that can exploit a known vulnerability.
- The attacker may also set up back doors so that they can continue to access to the system if their original point of entry is identified and closed by network administrators.

---

<!-- .element class="split-screen-with-title" -->
# Cyber Kill Chain

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Stage 3: Delivery**
  - Malware payload delivered to target network or system <!-- .element: class="fragment" data-fragment-index="2" -->
    - Example: Spear phishing attack <!-- .element: class="fragment" data-fragment-index="3" -->
    - Targeted email with a malicious attachment <!-- .element: class="fragment" data-fragment-index="4" -->
  - Exploit mismanaged or misconfigured servers <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_06.png)
Source: Lockheed Martin

</div>

</div>

NOTE:

- Intruder launches the attack.
- The specific steps taken will depend on the type of attack they intend to carry out.
  - For example, the attacker may send email attachments or a malicious link to spur user activity to advance the plan.
  - This activity may be combined with social engineering techniques to increase the effectiveness of the campaign.

---

<!-- .element class="split-screen-with-title" -->
# Cyber Kill Chain

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Stage 4: Exploitation**
  - Malware executed <!-- .element: class="fragment" data-fragment-index="2" -->
  - Discovered vulnerabilities exploited <!-- .element: class="fragment" data-fragment-index="3" -->
  - Superuser access granted to threat actor <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Stage 5: Installation**
  - Malware embeds itself into targeted systems <!-- .element: class="fragment" data-fragment-index="6" -->
  - Additional malware components downloaded <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_06.png)
Source: Lockheed Martin

</div>

</div>

NOTE:

- Exploitation
  - The malicious code is executed in the victim system
- Installation
  - Malware or other attack vector will be installed on the victim system
  - This is a turning point in the attack, now the threat actor has entered the system and can assume control

---

<!-- .element class="split-screen-with-title" -->
# Cyber Kill Chain

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Stage 6: Command and Control (C2)**
  - Management and communication established from attacker to malware infection <!-- .element: class="fragment" data-fragment-index="2" -->
  - Facilitates greater movement within target network <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Stage 7: Actions on Objectives**
  - Mission-specific actions are finally taken to achieve original objectives <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_06.png)
Source: Lockheed Martin

</div>

</div>

NOTE:

- Command and Control (C2)
  - Attacker is able to use the malware to assume remote control of a device or identity within the target network.
  - In this stage, the attacker may also work to move laterally throughout the network, expanding their access and establishing more points of entry for the future.
- Actions on Objectives
  - Attacker takes steps to carry out their intended goals
    - data theft
    - destruction
    - encryption
    - exfiltration

---

<!-- .element class="split-screen-with-title" -->
# Web Vulnerability Scanners

<div>

<div>

- Automated tools that scan web applications looking for security vulnerabilities <!-- .element: class="fragment" data-fragment-index="1" -->
  - Cross-site scripting (XSS) <!-- .element: class="fragment" data-fragment-index="2" -->
  - SQL injection <!-- .element: class="fragment" data-fragment-index="3" -->
  - Cross-site request forgery (CSRF) <!-- .element: class="fragment" data-fragment-index="4" -->
- Example product <!-- .element: class="fragment" data-fragment-index="5" -->
  - Burp Suite by Portswigger <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_07.png)

</div>

</div>

NOTE:

- What is a web vulnerability scanner?
  - Web vulnerability scanners are automated tools that scan web applications to look for security vulnerabilities such as cross-site scripting (XSS), SQL injection (SQLi), and cross-site request forgery (CSRF).

---

<!-- .element class="main-title" -->
# OSINT

---

<!-- .element class="split-screen-with-title" -->
# OSINT

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Open Source Intelligence (OSINT)** includes information that can legally be gathered from free, public sources about an individual or organization
- Community databases of useful security information <!-- .element: class="fragment" data-fragment-index="2" -->
  - Threatminer <!-- .element: class="fragment" data-fragment-index="3" -->
  - VirusTotal <!-- .element: class="fragment" data-fragment-index="4" -->
  - Hybrid Analysis <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_08.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_09.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_10.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# OSINT

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**VirusTotal**
  - A community database of malware IOCs and has an API <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Hybrid Analysis**
  - A free malware analysis service for the community that detects and analyzes unknown threats using a unique Hybrid Analysis technology. <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**ThreatMiner**
  - A threat intelligence portal designed to enable analysts to research under a single interface. <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_08.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_09.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_10.png)

</div>

</div>

NOTE:
Visit and talk about how these sites work.
<https://www.virustotal.com/gui/>
<https://www.hybrid-analysis.com/>
<https://www.threatminer.org/>

---

<!-- .element class="split-screen-with-title" -->
# Brute Force Attack

<div>

<div>

- A brute force attack involves using automated authentication attempts to expedite the process of “guessing” the credentials to an account <!-- .element: class="fragment" data-fragment-index="1" -->
  - Preventable with lockout (set maximum authentication attempts) <!-- .element: class="fragment" data-fragment-index="2" -->

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_11.png)

---

<!-- .element class="image-and-title" -->
# Dynamic DNS

- A service that automatically updates a DNS with a web property's correct IP, even if that IP address changes. <!-- .element: class="fragment" data-fragment-index="1" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_12.png)
Source: Mikrotik Forum

NOTE:

- What is Dynamic DNS?
  - Dynamic DNS (DDNS) is a service that automatically updates a DNS with a web property's correct IP, even if that IP address changes.

---

<!-- .element class="main-title" -->
# Splunk

# Log Analysis

---

<!-- .element class="text-only" -->
# Splunk Commands

- The metadata command returns a list of sources, sourcetypes, or hosts from an index or search peer. <!-- .element: class="fragment" data-fragment-index="1" -->
  - Returns information accumulated over time <!-- .element: class="fragment" data-fragment-index="2" -->
  - Snapshot of an index over time frame, e.g. “last 7 days” <!-- .element: class="fragment" data-fragment-index="3" -->
  - Syntax: <!-- .element: class="fragment" data-fragment-index="4" -->
    - `| metadata type=<metadata-type> [<index-specifier>]... [splunk_server=<wc-string>] [splunk_server_group=<wc-string>]... `<!-- .element: class="fragment" data-fragment-index="5" -->
  - Example: <!-- .element: class="fragment" data-fragment-index="6" -->
    - `| metadata type=hosts` <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

NOTE:

- What is the metadata command and how does it work?
  - The metadata command returns a list of sources, sourcetypes, or hosts from a specified index or distributed search peer. The metadata command returns information accumulated over time.
  - You can view a snapshot of an index over a specific timeframe, such as the last 7 days, by using the time range picker.
  - Syntax
    - | metadata type=<metadata-type> [<index-specifier>]... [splunk_server=<wc-string>] [splunk_server_group=<wc-string>]...
  - Example
    - | metadata type=hosts

---

<!-- .element class="split-screen-with-title" -->
# Boss of the SOC

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Boss of the SOC (BOTS)**
  - First introduced at Splunk .conf2016 <!-- .element: class="fragment" data-fragment-index="2" -->
  - A 150-participant workshop to offer a fun, realistic learning experience in applying the Splunk SIEM to secops. <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**The BOTS EMEA Virtual Edition held in 2020**
  - 273 participating teams <!-- .element: class="fragment" data-fragment-index="5" -->
  - 732 active players <!-- .element: class="fragment" data-fragment-index="6" -->
  - 40 countries <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_13.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-12/slides/assets/12_14.png)

</div>

</div>

NOTE:
Results of BOTS EMEA Virtual Edition

---

<!-- .element class="main-title" -->
# Demo

NOTE:

- Demo 1 BOTSv1
  - Show students how to access BOTSv1 Scenario #1 - APT
  - Review and reinforce some basic SPL commands
  - index=botsv1 limits the search to that index
  - Point out the "All time" date range constraint
  - Talk through "SELECTED FIELDS" and "INTERESTING FIELDS" in the left panel
  - Manually type index=botsv1 sourcetype="" noting that sourcetype will automatically populate your choices as you type, like an IDE would.
  - If time allows, consider working through the first activity together, "Identifying the IP Address of a Victim System"
