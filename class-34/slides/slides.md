<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 34

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

Daily TODOs

- Update the class number for each video recording
- Move the dragon icon to the current day
- Hide/unhide slides to show as necessary
- Toggle presentation mode on and screen share this first slide when you initialize recording on Zoom to indicate class number

---

<<<<<<< HEAD
<!-- .element class="split-screen-with-title" -->

## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- **Module 6** - Threat Modeling & Analysis

- &shy;<!-- .element style="color: red;" --> **Module 7** - Threat Hunting

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

## Module 7 Labs

### Threat Hunting

<div align="left" style="font-size: 45px">

- **Class 31** - Threat Hunting with YARA

<br>

- **Class 32** - Malware Traffic Analysis

<br>

- **Class 33** - Threat Hunting with Zeek, RITA

<br>

- &shy;<!-- .element style="color: red;" -->**Class 34** - Forensics with Autopsy

<br>

- **Class 35** - N/A
=======
<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 34 - Digital Forensics
- Course Overview <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Review
- Ops Challenge
- Lecture:
  - Digital Forensics
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/0_01.png)
<!-- .element style="width: 100%"-->

</div>
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

---

<<<<<<< HEAD
<!-- .element class="split-screen-with-title" -->
=======
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

- &shy;<!-- .element style="color: red;" -->**Class 34** - Digital Forensics with Autopsy

<br>

- **Class 35** - Career Coaching Workshop


</div>

---

<!-- .element class="split-screen-with-title" -->


>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da
## Module 7 Challenges

<div>

<div align="left" style="font-size: 35px">

<<<<<<< HEAD
- **Class 31** - Malware Detection Part 1 of 3

<br>

- **Class 32** - Malware Detection Part 2 of 3

<br>

- **Class 33** - Malware Detection Part 3 of 3

<br>

- &shy;<!-- .element style="color: red;" -->**Class 34** - Mock Interviews

<br>

- **Class 35** - Web Vulnerability Scanning with Nmap
=======
- **Class 31** - Signature-based Malware Detection (Part 1 of 3)

<br>

- **Class 32** - Signature-based Malware Detection (Part 2 of 3)

<br>

- **Class 33** - Signature-based Malware Detection (Part 3 of 3)

<br>

- &shy;<!-- .element style="color: red;" -->**Class 34** - Mock Interviews

<br>

- **Class 35** - Web Vulnerability Scanning with Nmap

>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

<div>
<<<<<<< HEAD

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/2_0.png)<!-- .element style="width: 100%"-->

</div>

</div>
=======

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/0_03.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 34 - Digital Forensics
- Course Overview
- Warmup <!-- .element style="color: red;" -->
- Review
- Ops Challenge
- Lecture:
  - Digital Forensics
- Demo
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

---

<!-- .element class="main-title" -->
<<<<<<< HEAD
# Review: Threat Hunting with Zeek & RITA

---

<!-- .element class="split-screen-with-title" -->
# Beacons

<div>

<div>
=======

# Warmup

---

<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 34 - Digital Forensics
- Course Overview
- Warmup
- Review <!-- .element style="color: red;" -->
- Ops Challenge
- Lecture:
  - Digital Forensics
- Demo
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

---

<!-- .element class="main-title" -->

# Review
- Previous Concepts <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Lab 33

---

<!-- .element class="main-title" -->
# Review: 

<<<<<<< HEAD
<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/4_0.png)
=======
## Threat Hunting with Zeek + RITA
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

</div>

NOTE:

- What is beaconing? [CS](https://askinglot.com/what-is-beaconing-in-cyber-security)
  - Beaconing is when the malware communicates with a C2 server asking for instructions or to exfiltrate collected data on some predetermined asynchronous interval.
  - The C2 server hosts instructions for the malware, which are then executed on the infected machine after the malware checks in.
  - DO: Draw this out as a diagram referencing hunting
  - Key characteristics of a beacon
  - Beacon timing
  - Beacon packet size
  - Beacon false positives WILL occur
  - Proper beacon analysis is a difficult, tedious process
  - Beacon with many connections strobe

<<<<<<< HEAD
---

<!-- .element class="text-and-image" -->
# Long Connections

<div>

- Long connections may only open and close infrequently compared to frequent beacons.
  - Top: One long connection
  - Bottom: Six shorter connections
- You may need to track these differently than you're used to

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/9_0.png)
=======
<!-- .element class="split-screen-with-title" -->


# Beacons

<div>

<div align="left">

- Key characteristics of a beacon<!-- .element: class="fragment" data-fragment-index="1" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Timing** (periodic or irregular communication)
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Packet size** (asking for instructions or exfiltrating collected data)
- Beware false positives<!-- .element: class="fragment" data-fragment-index="4" -->
- Proper beacon analysis is a difficult, tedious process<!-- .element: class="fragment" data-fragment-index="5" -->
- A beacon with many connections is a strobe<!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div align="left">

> **Beaconing** is when malware establishes communication with a remote command and control (C2) server

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/33_01.png)
<!-- .element style="width: 100%"-->


</div>

</div>
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

NOTE:

The C2 server hosts instructions for the malware, which are then executed on the infected machine after the malware checks in.

---

<<<<<<< HEAD
<!-- .element class="text-and-image" -->
# DNS
=======
<!-- .element class="split-screen" -->

<div>

<div align="center">
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

# Long Connections<!-- .element: class="fragment" data-fragment-index="1" -->

<<<<<<< HEAD
![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/10_0.png)
=======
</div>

- Long connections may only open and close infrequently (compared to frequent beacons)<!-- .element: class="fragment" data-fragment-index="2" -->
- You may need to track these differently than you're used to<!-- .element: class="fragment" data-fragment-index="4" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/33_02.png)
<!-- .element style="width: 100%"--><!-- .element: class="fragment" data-fragment-index="3" -->
&shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Top**: One long connection

&shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Bottom**: Six shorter connections

</div>

<div>

<div align="center">

# DNS<!-- .element: class="fragment" data-fragment-index="5" -->

</div>

- DNS based C2 is different than normal C2 direct communications as this instead utilizes the DNS infrastructure<!-- .element: class="fragment" data-fragment-index="6" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/33_03.png)
<!-- .element style="width: 100%"--><!-- .element: class="fragment" data-fragment-index="7" -->

Here is a normal non-cached DNS request to Google.com<!-- .element: class="fragment" data-fragment-index="7" -->

</div>
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

NOTE:

The C2 server hosts instructions for the malware, which are then executed on the infected machine after the malware checks in.

- The Client (your computer) only talks with its configured Recursive Name Server (NS). This name server is usually given to your computer when it connects to a network through DHCP. Though you can also set your DNS servers manually. For instance, you may choose to use one of the servers provided by large companies such as Cloudflare (1.1.1.1) or Google (8.8.8.8).
- Behind the scenes, your Recursive NS is doing a lot of work for you. All these requests would quickly overwhelm servers if they were done every time so the above sequence of events only happens if your Recursive NS doesn't already know an answer. Once it has performed this work once it will cache the answer for a period of time. So the next time you or any other client makes the same DNS query the NS will answer from its local cache instead of querying other name servers.
<<<<<<< HEAD
=======
 
---

<!-- .element class="main-title" -->

# Review:

## Lab 33

NOTE:

---

<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 34 - Digital Forensics
- Course Overview
- Warmup
- Review
- Ops Challenge <!-- .element style="color: red;" -->
- Lecture: 
  - Digital Forensics
- Demo
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

---

<!-- .element class="main-title" -->
# Ops Challenge:

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Review Ops Challenge 33**
- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="2" -->**Ops Challenge 34** - Mock Interviews

NOTE:

### Review: Ops Challenge 33

<<<<<<< HEAD
---

<!-- .element class="split-screen-with-title" -->
# Digital Forensics

<div>

<div>

- Why digital forensics?
  - Answer the question: "What happened on this device?"
- Digital Forensics & Incident Response (DFIR) is a multidisciplinary profession that focuses on identifying, investigating, and remediating computer network exploitation
  - Ever seen Dexter?
  - DFIR is the cyber  equivalent of the character Dexter
=======
### Introduce: Ops Challenge 34 - Mock Interviews

---

<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 34 - Digital Forensics
- Course Overview
- Warmup
- Review
- Ops Challenge
- Lecture: <!-- .element style="color: red;" -->
  - Digital Forensics
- Demo

>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

---

<!-- .element class="main-title" -->


<<<<<<< HEAD
<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/8_0.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/8_1.png)
Source: Medium, WP

</div>

</div>

NOTE:

- Why computer forensics?
  - Going to help you in situations where you answer the question "what happened on this device?"
  - Digital forensics is commonly used interchangeably but denotes a broader scope of work including all devices capable of storing digital information.
  - IT professionals can sometimes end up doing quite a lot of forensics work, such as chasing down a malicious process on an endpoint or investigating a user policy violation. Another example of why IT roles are "feeder" roles for security specialization.

Ever seen the show Dexter? The main character, Dexter Morgan, works as a Forensic Blood Spatter Analyst. The character is commonly called to crime scenes (after the crime occurs) to analyze the situation and then work to reverse-engineer in his lab environment what actually happened during the crime. Sound familiar?
=======
# Lecture:

### Class 34 - Digital Forensics


NOTE:
Is there a relevant Ch. in the Wiley Security+ (SY0-601) Study Guide?
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

---

<!-- .element class="split-screen-with-title" -->
<<<<<<< HEAD
# Digital Forensics

<div>

<div>

- In a digital forensics investigation, investigators recover documents, photos, emails and files from computer systems, hard drives, and devices
  - Commonly a part of cyber crime investigation
  - Examine computer systems to find evidence of illegal activity
  - Forensics specialists also assist with network breaches in DFIR role

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/9_0.png)
Source: Brixia
=======


# Digital Forensics & Incident Response (DFIR)

<div>

<div align="left">

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->**DFIR** is a field within cybersecurity that involves **identifying**, **investigating**, and **remediating** cyber incidents and attacks:
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->A **multidisciplinary profession:**

</div>

<div align="left">

> **DFIR professionals** are the Crime Scene Investigators of the digital world

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/34_01.png)
<!-- .element style="width: 90%"-->
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

</div>

NOTE:

<<<<<<< HEAD
- What is a computer forensics investigation?
  - Recover documents, photos, emails and files from computer systems, hard drives, and devices
  - Commonly a part of cyber crime investigation
  - Examine computer systems to find evidence of illegal activity
  - Forensics specialists also assist with network breaches
  - Cybersecurity focuses on prevention, whereas forensics is more reactionary
=======
Source: Medium, WP

Image Source: include link to image source

Source: [ChatGPT](https://chat.openai.com/share/1aed47ee-c43c-4711-b024-78c941752e22)

DFIR stands for "Digital Forensics and Incident Response." It is a field within cybersecurity that involves identifying, investigating, and mitigating cyber incidents and attacks. DFIR professionals are responsible for gathering and analyzing digital evidence related to cybercrimes, data breaches, and other malicious activities.

The two main components of DFIR are:

1. **Digital Forensics:** This involves the collection, preservation, and analysis of digital evidence from various sources, such as computers, servers, mobile devices, and networks. Digital forensics experts use specialized tools and techniques to extract and examine data, including files, logs, and system artifacts. The goal is to reconstruct events, identify the extent of the breach or attack, and gather evidence that can be used in legal proceedings if necessary.

2. **Incident Response:** This focuses on identifying, containing, and mitigating cyber incidents in real time. Incident response teams are tasked with rapidly responding to security breaches and attacks to minimize their impact. This includes isolating compromised systems, analyzing the attack vector, eradicating malicious code, and implementing safeguards to prevent further incidents.
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

---

<!-- .element class="split-screen-with-title" -->
<<<<<<< HEAD
# Digital Forensics

<div>

<div>

- What are the stages of a digital forensics investigation?
  - Planning
  - Identification and preservation
    - The first rule of digital forensics is to preserve the original evidence
    - Protect original copies of data by making copies first
    - Integrity is everything!
    - Isolate, safeguard, and preserve the master copy

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/10_0.png)
Source: Guru99
=======


# Digital Forensics & Incident Response (DFIR)

<div>

<div align="left">

&shy;<!-- .element: class="fragment semi-fade-out" data-fragment-index="0" -->**DFIR** is a field within cybersecurity that involves **identifying**, **investigating**, and **remediating** cyber incidents and attacks:
- &shy;<!-- .element: class="fragment semi-fade-out" data-fragment-index="0" -->A **multidisciplinary profession:**
  - &shy;<!-- .element: class="fragment semi-fade-out" data-fragment-index="0" -->Both **Investigators** and **Responders**
- &shy;<!-- .element: class="fragment" data-fragment-index="0" -->As **Investigators** their job is to:
  - &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Reconstruct** the events
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->Determine the **extent of the attack**
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Gather **legally admissable evidence**
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->Use **specialized tools and techniques** to extract and examine data

</div>

<div align="left">

> **DFIR professionals** are the Crime Scene Investigators of the digital world

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/34_01.png)
<!-- .element style="width: 90%"-->
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

</div>

NOTE:

<<<<<<< HEAD
What are the stages of a digital forensics investigation?

- Planning
- Identification and preservation
  - The first rule of digital forensics is to preserve the original evidence
  - Protect original copies of data by making copies first
  - Integrity is everything!
  - Isolate, safeguard, and preserve the master copy
- Analysis
  - Here's the part we'll be doing today in lab!
  - Construct a timeline of events
  - Build a picture of what happened
- Documentation
  - Record, date & sign
- Presentation
  - Present your findings without any bias or partiality
=======
Source: Medium, WP

Image Source: include link to image source

Source: [ChatGPT](https://chat.openai.com/share/1aed47ee-c43c-4711-b024-78c941752e22)

DFIR professionals work closely with law enforcement agencies, legal teams, and IT departments to ensure that cyber incidents are properly investigated, evidence is preserved, and appropriate actions are taken to prevent future incidents. The ultimate goal of DFIR is to effectively manage and respond to cyber incidents while also ensuring the preservation of digital evidence for potential legal actions.
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

---

<!-- .element class="split-screen-with-title" -->
<<<<<<< HEAD
# Digital Forensics

<div>

<div>

- Stages (ctd.)
- Analysis
  - Here's the part we'll be doing today in lab!
  - Construct a timeline of events
  - Build a picture of what happened
- Documentation
  - Record, date & sign
- Presentation
  - Present your findings without any bias or partiality

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/11_0.png)
Source: Guru99
=======


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

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/34_03.png)
<!-- .element style="width: 95%"-->

>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

</div>

NOTE:

<<<<<<< HEAD
NOTE:

What are the stages of a digital forensics investigation?

- Planning
- Identification and preservation
  - The first rule of digital forensics is to preserve the original evidence
  - Protect original copies of data by making copies first
  - Integrity is everything!
  - Isolate, safeguard, and preserve the master copy
- Analysis
  - Here's the part we'll be doing today in lab!
  - Construct a timeline of events
  - Build a picture of what happened
- Documentation
  - Record, date & sign
- Presentation
  - Present your findings without any bias or partiality
=======
Image Source?: Brixia

Source:
- [ERMProtect.com](https://ermprotect.com/blog/what-are-the-5-stages-of-a-digital-forensics-investigation/)
- [ChatGPT](https://chat.openai.com/share/1aed47ee-c43c-4711-b024-78c941752e22)

A digital forensics investigation involves a series of systematic steps to gather, preserve, analyze, and present digital evidence related to a cyber incident, crime, or security breach. These steps help investigators reconstruct events, identify the extent of the incident, and determine the responsible parties.

**Legal Considerations:**
 - Preserve evidence in a manner that maintains its admissibility in court, if required.

Throughout the investigation, digital forensics professionals must adhere to strict protocols and practices to maintain the integrity of the evidence and ensure that their actions are legally defensible.
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

---

<!-- .element class="split-screen-with-title" -->
<<<<<<< HEAD
# Data Volatility

<div>

<div>

- Why is data volatility relevant to forensics?
  - Volatile data can be permanently lost due to mishandling of evidence
    - RAM
    - CPU cache
- How do forensic investigators handle non-volatile memory (e.g. hard drives)?
  - Follow specific procedures designed to preserve evidence integrity
  - Example
    - Clone the hard disk, then derive a hash value of both

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/12_0.png)
Source: Flickr
=======


# Digital Forensics

<div>

<div align="center">

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/34_04.png)
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
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

</div>
<<<<<<< HEAD
=======

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
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

---

<!-- .element class="split-screen-with-title" -->
<<<<<<< HEAD
# Hard Disk Copy

<div>

<div>

- DD files (with the .dd file extension) are data containers created by hard drive copy tools
- In Linux, DD utility uses the following command to create a dd image file:
  - `dd if=/dev/hdr of=mydisk.dd`
  - `mydisk.dd` is a name of the destination file
- In Windows, DD utility uses the following command to create a dd disk image:
  - `dd.exe if=\\.\PhysicalDrive0 of=d:\images\PhysicalDrive0.dd`
  - Creates a duplicate copy of a source drive

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/13_0.png)
=======


# Data Volatility

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/34_05.png)
<!-- .element style="width: 75%"-->

</div>

</div>

NOTE:

Source: Flickr

Image Source: include link to image source

Source: [ChatGPT](https://chat.openai.com/share/1aed47ee-c43c-4711-b024-78c941752e22)
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
<<<<<<< HEAD
# File Types

<div>

<div>

- A file with the DAT file extension is usually a generic data file that stores information specific to the application it refers to
  - Sometimes you'll find them by themselves but often they're with other configuration files like DLL files.
- A file with the JPG file extension is an image file

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/14_0.png)
Source: Lifewire, de.wikipedia.org
=======


# Hard Disk Copy

<div>

<div align="left" style="font-size: 34px">

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->**In Linux**, the DD utility uses the following command to create a dd image file:

<div style="font-size: 27px">

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->&emsp;**`> dd if=/dev/hdr of=mydisk.dd`**

&emsp;

</div>

&shy;<!-- .element: class="fragment" data-fragment-index="2" -->**In Windows**, DD utility uses the following command to duplicate a source drive, creating a DD disk image:

<div style="font-size: 27px">

&shy;<!-- .element: class="fragment" data-fragment-index="2" -->&emsp;**`> dd.exe if=\\.\PhysicalDrive0`**

&shy;<!-- .element: class="fragment" data-fragment-index="2" -->&emsp;&emsp;&nbsp;**`of=d:\images\PhysicalDrive0.dd`**

</div>

</div>

<div align="left">

> **DD files** (with the ".dd" file extension) are data containers created by hard drive copy tools

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/34_06.png)
<!-- .element style="width: 100%"-->

>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

</div>
<<<<<<< HEAD
=======

NOTE:

Source: de.wikipedia.org

Image Source: include link to image source

- "mydisk.dd" is the name of the destination file
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

---

<!-- .element class="split-screen-with-title" -->
<<<<<<< HEAD
# Autopsy

<div>
=======

>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

<div>

<<<<<<< HEAD
- Autopsy is an open source forensics platform that comes bundled in FLARE VM
  - Analyze mobile devices and digital media
  - Used in law enforcement, national security, litigation support, and corporate investigation
- Why use Autopsy over manual file navigation?
  - Multi-user cases, timeline analysis, registry analysis, keyword search, email analysis, media playback, EXIF analysis, malicious file detection

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/15_0.png)
=======
<div>

<div align="left">

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Used by**: law enforcement, national security, litigation support, and cybersecurity experts

&shy;<!-- .element: class="fragment" data-fragment-index="2" -->Investigators working with **multiple machines or file systems** can build a **central repository of data**:
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Flag patterns or data that might be found in multiple places
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->Multi-user cases, timeline analysis, registry analysis, keyword search, email analysis, media playback, EXIF analysis, malicious file detection

</div>

<div align="left">

> **Autopsy**:
>
> An open source forensics platform used for analyzing and investigating digital evidence

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/34_07.png)
<!-- .element style="width: 62%"-->

</div>

</div>
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

</div>

NOTE:

<<<<<<< HEAD
- What is Autopsy?
  - Open source forensics platform that comes bundled in FLARE VM
  - Analyze mobile devices and digital media
  - Used in law enforcement, national security, litigation support, and corporate investigation
  - Why use Autopsy over manual file navigation?
    - Multi-user cases, timeline analysis, registry analysis, keyword search, email analysis, media playback, EXIF analysis, malicious file detection

=======
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da
https://sleuthkit.org/sleuthkit/

Image Source: include link to image source

Source: [Wikipedia: Autopsy (software)](https://en.wikipedia.org/wiki/Autopsy_(software))

---

<!-- .element class="split-screen-with-title" -->
<<<<<<< HEAD
# Continued Study

- The Computer Hacking Forensic Investigator (CHFI) from EC-Council is a digital forensics certification
  - Vendor-neutral
  - Crime investigation process, emphasizing on proper collection, handling, and preservation of digital evidence
- GIAC Certified Forensic Analyst (GCFA) is an advanced digital forensics certification that certifies cyber incident responders and threat hunters in advanced skills needed to hunt, identify, counter, and recover from a wide range of threats within networks.
=======


# Continued Study:

<div>

<div align="left">

### **Computer Hacking Forensic Investigator (CHFI)**
- A digital forensics certification from *EC-Council*
- Vendor-neutral
- Emphasizes proper collection, handling, and preservation of digital evidence

<div align="center">

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/34_12.png)
<!-- .element style="width: 100%"-->

</div>

</div>

<div align="left">

<div align="center">

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/34_09.png)
<!-- .element style="width: 45%"-->
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

<div>

<div>

### **GIAC Certified Forensic Analyst (GCFA)**
- Certificate in advanced skills needed to hunt, identify, counter, and recover from a wide range of threats within networks. 

</div>
<<<<<<< HEAD

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/16_1.png)

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-34/slides/assets/16_2.png)
=======

</div>
>>>>>>> 8f8f1c4cc1b22a5c48114396bfd8363439ae83da

</div>

</div>

NOTE:

Image Source: include link to image source

https://www.giac.org/certification/certified-forensic-analyst-gcfa

SIFT VM from SANS DFIR


---

<!-- .element class="title-and-subtitle" -->

# Agenda
## Class 34 - Digital Forensics
- Course Overview
- Warmup
- Review
- Ops Challenge
- Lecture: 
  - Digital Forensics
- Demo <!-- .element style="color: red;" -->

---

<!-- .element class="main-title" -->
# Demo & Lab

### Post Mortem analysis of hard drive using Autopsy

NOTE:

### Import OVA File


### Demo: Post Mortem analysis of hard drive using Autopsy

NOTE:

- Hashing with PowerShell
- In FLARE-VM, open PowerShell and access today's folder. Derive a hash of the DD file.

```
Get-FileHash .\8-jpeg-search.dd | Format-List

Algorithm : SHA256
Hash      : 9C43D6A2DD5132CF6AFC29E5C644CDE0CB747C64998A68E73F2EFB787887B126
Path      : C:\Users\labuser\Desktop\class-34-forensic\8-jpeg-search\8-jpeg-search.dd
Hashing is a valuable tool in proving the integrity of digital evidence.
```

Running Autopsy
In FLARE-VM open class-34-forensic with Autopsy and demonstrate a full investigation of 8-jpeg-search. You may want to pull up the walkthrough of the old Autopsy.

View the `README.txt`
View the `results.txt` and work through it in class to find the files
Import `8-jpeg-search.dd` into Autopsy
Introduce the interface. Draw attention to the ribbon with Data Source, Images/Videos, etc.
Click Images/Videos to run an automated scan for the target JPEGs.
Sort by Group Name, then select CAT-0: Uncategorized (11) to view all 11 JPEG hits from this method. However, this isn't all our targets.
Because the user of this computer deleted some of the images we need, we can use Autopsy to restore them.

Some of the target pictures are in the views > deleted files branch of the file system tree panel on the left.
Autopsy can also quickly traverse compressed archives to let you view the data inside.

Go to `Archive > file10.tar.gz` and show that you can easily traverse archives.
We can also search by Keyword using Keyword Search.

Search for the word "Archive" and right click > View Source File in Directory.
