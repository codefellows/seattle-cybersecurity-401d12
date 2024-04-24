<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 35

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

Daily TODOs

- Update the class number for each video recording
- Move the dragon icon to the current day
- Hide/unhide slides to show as necessary
- Toggle presentation mode on and screen share this first slide when you initialize recording on Zoom to indicate class number

---

<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 35 - Career Coaching Workshop
- Course Overview <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Review
- Lecture:
  - Web Vulnerability Scanning
- Demo

---

<!-- .element class="split-screen-with-title" -->

## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- **Module 6** - Threat Modeling & Analysis

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Module 7** - Threat Hunting

- **Module 8** - Web Application Security

- **Module 9** - Penetration Testing

- **Module 10** - Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-35/slides/assets/0_01.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-with-text" -->

## Module 7 Labs

### Threat Hunting


<div align="left" style="font-size: 45px">

- **Class 31** - Threat Hunting with YARA

<br>

- **Class 32** - Malware Traffic Analysis with Wireshark

<br>

- **Class 33** - Threat Hunting with Zeek, RITA

<br>

- **Class 34** - Forensic Investigation with Autopsy

<br>

- &shy;<!-- .element style="color: red;" -->**Class 35** - Career Coaching Workshop


</div>

---

<!-- .element class="split-screen-with-title" -->


## Module 7 Challenges

<div>

<div align="left" style="font-size: 35px">

- **Class 31** - Signature-based Malware Detection (Part 1 of 3)

<br>

- **Class 32** - Signature-based Malware Detection (Part 2 of 3)

<br>

- **Class 33** - Signature-based Malware Detection (Part 3 of 3)

<br>

- **Class 34** - Mock Interviews

<br>

- &shy;<!-- .element style="color: red;" -->**Class 35** - Web Vulnerability Scanning with Nmap


</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-35/slides/assets/0_03.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 35 - Career Coaching Workshop
- Course Overview
- Warmup <!-- .element style="color: red;" -->
- Review
- Lecture:
  - Web Vulnerability Scanning
- Demo

---

<!-- .element class="main-title" -->

# Warmup

---

<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 35 - Career Coaching Workshop
- Course Overview
- Warmup
- Review <!-- .element style="color: red;" -->
- Lecture:
  - Web Vulnerability Scanning
- Demo

---

<!-- .element class="main-title" -->

# Review
- Previous Concepts <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Lab 34

---

<!-- .element class="main-title" -->
# Review:

## Digital Forensics

NOTE:

---

<!-- .element class="split-screen-with-title" -->


# Digital Forensics & Incident Response (DFIR)

<div>

<div align="left">

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->**DFIR** is a field within cybersecurity that involves **identifying**, **investigating**, and **remediating** cyber incidents and attacks:
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->A **multidisciplinary profession:**
  - Both **Investigators** and **Responders**
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->As **Investigators** their job is to:
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Reconstruct** the events
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->Determine the **extent of the attack**
  - &shy;<!-- .element: class="fragment" data-fragment-index="7" -->Gather **legally admissable evidence**
- &shy;<!-- .element: class="fragment" data-fragment-index="8" -->Use **specialized tools and techniques** to extract and examine data

</div>

<div align="left">

> **DFIR professionals** are the Crime Scene Investigators of the digital world

![Image](/ops-401-cybersecurity-guide/curriculum/class-35/slides/assets/34_01.png)
<!-- .element style="width: 90%"-->

</div>

</div>

NOTE:

Source: Medium, WP

Image Source: include link to image source

Source: [ChatGPT](https://chat.openai.com/share/1aed47ee-c43c-4711-b024-78c941752e22)

DFIR stands for "Digital Forensics and Incident Response." It is a field within cybersecurity that involves identifying, investigating, and mitigating cyber incidents and attacks. DFIR professionals are responsible for gathering and analyzing digital evidence related to cybercrimes, data breaches, and other malicious activities.

The two main components of DFIR are:

1. **Digital Forensics:** This involves the collection, preservation, and analysis of digital evidence from various sources, such as computers, servers, mobile devices, and networks. Digital forensics experts use specialized tools and techniques to extract and examine data, including files, logs, and system artifacts. The goal is to reconstruct events, identify the extent of the breach or attack, and gather evidence that can be used in legal proceedings if necessary.

2. **Incident Response:** This focuses on identifying, containing, and mitigating cyber incidents in real time. Incident response teams are tasked with rapidly responding to security breaches and attacks to minimize their impact. This includes isolating compromised systems, analyzing the attack vector, eradicating malicious code, and implementing safeguards to prevent further incidents.

DFIR professionals work closely with law enforcement agencies, legal teams, and IT departments to ensure that cyber incidents are properly investigated, evidence is preserved, and appropriate actions are taken to prevent future incidents. The ultimate goal of DFIR is to effectively manage and respond to cyber incidents while also ensuring the preservation of digital evidence for potential legal actions.

---

<!-- .element class="split-screen-with-title" -->


# Digital Forensics Investigations

<div>

<div align="left" style="font-size: 32px">

- A **systematic and detailed process** of collecting, analyzing, and interpreting digital evidence
- Meant to **uncover information related to cyber incidents**.
- The investigative process aims to:
  - **Reconstruct events**
  - **Identify the root causes of incidents**
  -  **Provide a clear understanding** of the events in a digital environment

</div>

<div align="left">

> **Digital Forensics Investigations** are crucial for determining the scope of incidents, attributing responsibility, and supporting legal actions if necessary

![Image](/ops-401-cybersecurity-guide/curriculum/class-35/slides/assets/34_03.png)
<!-- .element style="width: 95%"-->


</div>

</div>

NOTE:

Image Source?: Brixia

Source:
- [ERMProtect.com](https://ermprotect.com/blog/what-are-the-5-stages-of-a-digital-forensics-investigation/)
- [ChatGPT](https://chat.openai.com/share/1aed47ee-c43c-4711-b024-78c941752e22)

A digital forensics investigation involves a series of systematic steps to gather, preserve, analyze, and present digital evidence related to a cyber incident, crime, or security breach. These steps help investigators reconstruct events, identify the extent of the incident, and determine the responsible parties.

**Legal Considerations:**
 - Preserve evidence in a manner that maintains its admissibility in court, if required.

Throughout the investigation, digital forensics professionals must adhere to strict protocols and practices to maintain the integrity of the evidence and ensure that their actions are legally defensible.

---

<!-- .element class="split-screen-with-title" -->

<div>

<div>

<div align="center">

![Image](/ops-401-cybersecurity-guide/curriculum/class-35/slides/assets/34_04.png)
<!-- .element style="width: 68%"-->

</div>

<div align="left" style="font-size: 24px">

1. &shy;<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="1" -->**Identification and Planning:**
   - Define the scope and goals of the investigation.
1. &shy;<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="2" -->**Collect and Preserve:**
   - Secure the affected systems and data.
1. &shy;<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="3" -->**Analysis:**
   - Examine the collected evidence to reconstruct the incident.
1. &shy;<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="4" -->**Documentation:**
   - Prepare detailed reports that document the investigation process, methodologies, and findings.
1. &shy;<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="5" -->**Communication and Mitigate:**
   - Present findings to stakeholders.
   - Implement changes to prevent similar incidents in the future.

</div>

</div>

NOTE:

Source: Guru99

Image Source: include link to image sourceSource:
- [ERMProtect.com](https://ermprotect.com/blog/what-are-the-5-stages-of-a-digital-forensics-investigation/)
- [ChatGPT](https://chat.openai.com/share/1aed47ee-c43c-4711-b024-78c941752e22)

1. **Identification and Planning:**
   - Define the scope and goals of the investigation.
   - Identify the type of incident.
   - Identify required resources and tools.

1. **Collect and Preserve:**
   - Secure and isolate the affected systems.
   - Create a forensic image or snapshot of storage media to capture its state at the time of the incident.
   - Gather other relevant digital evidence from various sources (other computers, servers, mobile devices, and network logs).
   - Recover deleted files, analyze system artifacts, and review logs.

1. **Analysis:**
   - Examine the collected evidence.
   - Identify potential malware, malicious code, or unauthorized access points.
   - Analyze the findings to determine the cause, scope, and impact of the incident.
   - Identify any security vulnerabilities or weaknesses that were exploited.
   - Determine if sensitive data was compromised, altered, or stolen.
   - Reconstruct events and user activities (create a timeline).

1. **Documentation:**
   - Prepare detailed reports that document the investigation process, methodologies, and findings.
   - Include clear and concise explanations of technical details for non-technical stakeholders.
   - Provide a timeline of events and actions taken during the investigation.

1. **Communication and Mitigate:**
   - Present findings to stakeholders.
   - Implement security patches, system updates, and SOP changes to prevent similar incidents in the future.

**Legal Considerations:**
 - Preserve evidence in a manner that maintains its admissibility in court, if required.

Throughout the investigation, digital forensics professionals must adhere to strict protocols and practices to maintain the integrity of the evidence and ensure that their actions are legally defensible.

---

<!-- .element class="split-screen-with-title" -->

<div>

<div>

<div align="left">

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->*Why is data volatility relevant to forensics?*
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Volatile data can be permanently lost** due to mishandling of evidence
  - RAM
  - CPU cache

&shy;<!-- .element: class="fragment" data-fragment-index="3" -->*How do forensic investigators handle non-volatile memory (e.g. hard drives)?*
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Follow specific procedures** designed to preserve evidence integrity
  - Example: Clone the hard disk, then derive a hash value of both

</div>

<div align="left">

> **Data volatility**:
>
> The degree to which digital data changes or is altered over time.

![Image](/ops-401-cybersecurity-guide/curriculum/class-35/slides/assets/34_05.png)
<!-- .element style="width: 75%"-->

</div>

</div>

NOTE:

Source: Flickr

Image Source: include link to image source

Source: [ChatGPT](https://chat.openai.com/share/1aed47ee-c43c-4711-b024-78c941752e22)

---

<!-- .element class="split-screen-with-title" -->

<div>

<<<<<<< HEAD
- Autopsy is an open source forensics platform that comes bundled in FLARE VM
  - Analyze mobile devices and digital media
  - Used in law enforcement, national security, litigation support, and corporate investigation
- Why use Autopsy over manual file navigation?
  - Multi-user cases, timeline analysis, registry analysis, keyword search, email analysis, media playback, EXIF analysis, malicious file detection

- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Flag patterns or data that might be found in multiple places
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->Multi-user cases, timeline analysis, registry analysis, keyword search, email analysis, media playback, EXIF analysis, malicious file detection

</div>

<div align="left">

> **Autopsy**:
>
> An open source forensics platform used for analyzing and investigating digital evidence

![Image](/ops-401-cybersecurity-guide/curriculum/class-35/slides/assets/34_07.png)
<!-- .element style="width: 62%"-->
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

</div>

NOTE:
https://sleuthkit.org/sleuthkit/

Image Source: include link to image source

Source: [Wikipedia: Autopsy (software)](https://en.wikipedia.org/wiki/Autopsy_(software))

---

<!-- .element class="main-title" -->

# Review:

## Lab 34

NOTE:

---

<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 35 - Career Coaching Workshop
- Course Overview
- Warmup
- Review
- Lecture:
  - Web Vulnerability Scanning
- Demo

---

<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 35 - Career Coaching Workshop
- Course Overview
- Warmup
- Review
- Lecture: <!-- .element style="color: red;" -->
  - Web Vulnerability Scanning
- Demo


---

<!-- .element class="main-title" -->

# Lecture:

### Class 35 - Web Vulnerability Scanning

NOTE:
Is there a relevant Ch. in the Wiley Security+ (SY0-601) Study Guide?

---

<!-- .element class="split-screen-with-title" -->


# Vulnerability Scanning with Nmap

<div>

<div align="left" style="font-size: 45px">

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->Nmap can tell us about:
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Port Status** (Open / Closed)
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Running Services** and versions (FTP, SSH, Nginx, etc.)
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Operating System** types and versions

</div>

<div align="center">

![Image](/ops-401-cybersecurity-guide/curriculum/class-35/slides/assets/35_01.png)
<!-- .element style="width: 100%"-->

</div>

</div>

NOTE:

Image Source: include link to image source

---

<!-- .element class="split-screen-with-title" -->


# Vulnerability Scanning with Nmap

<div>

<div align="left" style="font-size: 37px">

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->The **Nmap Scripting Engine (NSE)** suite of scripts allows us to run more advanced scans:

&shy;<!-- .element: class="fragment" data-fragment-index="2" -->**`vuln`**
- searches for vulnerabilities and returns “cve-xxx” results<!-- .element: class="fragment" data-fragment-index="2" -->

&shy;<!-- .element: class="fragment" data-fragment-index="3" -->**`dos`**
- checks if the host is vulnerable to DOS attacks<!-- .element: class="fragment" data-fragment-index="3" -->


</div>

<div align="left">

![Image](/ops-401-cybersecurity-guide/curriculum/class-35/slides/assets/35_01.png)
<!-- .element style="width: 80%"-->

&shy;<!-- .element: class="fragment" data-fragment-index="4" -->Find more scripts here: **`nmap.org/nsedoc`**

</div>

</div>

NOTE:

Find more scripts here: [NSE Docs](https://nmap.org/nsedoc/)

---

<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 35 - Career Coaching Workshop
- Course Overview
- Warmup
- Review
- Lecture:
  - Web Vulnerability Scanning
- Demo <!-- .element style="color: red;" -->

---

<!-- .element class="main-title" -->
# Demo:

### Web Vulnerability Scanning with Nmap

NOTE:

### Demo: Web Vulnerability Scanning with Nmap

NOTE:

Demo: Ops Challenge Class 35 Web Vulnerability Scanning with Nmap Scripting Engine (NSE)

- First, ensure students have downloaded class-35-webserv.ova and have imported it into Virtualbox in NAT Network next to Kali Linux so they can follow along.

Today we will be demonstrating some basic Nmap operations.

Explain: Nmap is the terminal version of Zenmap. From here on forward, we won't be using the Zenmap GUI.

How do we identify on the NAT Network our target web server?

- Run ip a to determine the Kali box's IP address
- ASK: What is my network address?
- Run `nmap -sn 10.0.2.0/24` to get a quick assessment of what's on the LAN. The -sn modifier eliminates details like ports and should speed up the scan.
- ASK: What ports do we expect our target web server to have open?
- Run a normal `nmap 10.0.2.0/24` to check the open ports. Which one is the target web server?
- We now have our target IP address. This is a big first step. Next, let's review the Nmap cheat sheet and look at some basic commands.
- Run `nmap -O __webservip__` to have Nmap guess the operating system.
- Alternatively, run `nmap __webservip__ > nmap.log` to output the data to a log file. View the log file to verify.
- This is an example of a basic Nmap command. How boring! Let's get into something more powerful: Nmap Scripting Engine.

What is Nmap Scripting Engine (NSE)?

This is the more powerful extensible side of Nmap, allowing users to write .nse scripts in the Lua programming language.

First install Lua on your Ubuntu VM.

- `sudo apt-get update -y`
- `sudo apt-get install -y lua`

Let's go over some LUA basic syntax. (Reference Null Byte)

Let's take a look at an example NSE script. View the DEMO.md.

DO: Breakdown the components of this example script. What's it doing? (Below if from Null Byte)

NSE scripts are made up of three main sections: head, rule, and action.

- The head section contains mostly meta-data, such as the author, description, category, and other relevant information about the script.
- The rule section is where conditions are defined that allow the script to execute; This section must contain at least one of the following functions that will determine when the script will run: prerule, hostrule, portrule, or postrule.
- The action section is where the main functionality of the script takes place. All of the logic and instructions will go in this section.
- This example script determines if a given port is open and outputs a relevant message.

This is about how complex your submission today will be, although you should add sample output to a commented section.

DO: Copy the script into `/usr/share/nmap/scripts directory` where all the other .nse scripts are. Execute the script in Kali using Nmap command terminal: `nmap --script portscan __targetip__ -p 80`

Review today's assignment along with all remaining assignments due tonight and weekend.
