<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 31

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

Daily TODOs

- Hide/unhide slides to show as necessary
- Toggle presentation mode on and screen share this first slide when you initialize recording on Zoom to indicate class number

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 31 - Threat Hunting with YARA

- Course Overview <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Lecture:
  - Threat Hunting
  - YARA
- Demo

---
<!-- .element class="split-screen-with-title" -->

## Course Overview

<div>

<div align="left" style="font-size: 40px">

- **Module 6** - Threat Modeling & Analysis

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Module 7** - Threat Hunting

- **Module 8** - Web Application Security

- **Module 9** - Penetration Testing

- **Module 10** - Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-31/slides/assets/0_01.png)<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)

</div>

</div>

---

<!-- .element class="title-with-text" -->

## Module 7 Labs

### Threat Hunting

<div align="left" style="font-size: 45px">

- &shy;<!-- .element style="color: red;" -->**Class 31** - Threat Hunting with YARA

<br>

- **Class 32** - Malware Traffic Analysis with Wireshark

<br>

- **Class 33** - Threat Hunting with Zeek, RITA

<br>

- **Class 34** - Forensic Investigation with Autopsy

<br>

- **Class 35** - Career Coaching Workshop

</div>

---

<!-- .element class="split-screen-with-title" -->

## Module 7 Challenges

<div>

<div align="left" style="font-size: 35px">

- &shy;<!-- .element style="color: red;" -->**Class 31** - Malware Detection Part 1 of 3

<br>

- **Class 32** - Signature-based Malware Detection (Part 2 of 3)

<br>

- **Class 33** - Signature-based Malware Detection (Part 3 of 3)

<br>

- **Class 34** - Mock Interviews

<br>

- **Class 35** - Web Vulnerability Scanning with Nmap

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-31/slides/assets/0_03.png)<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 31 - Threat Hunting with YARA

- Course Overview
- Warmup <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Ops Challenge
- Lecture:
  - Threat Hunting
  - YARA
- Demo

---

<!-- .element class="main-title" -->

# Warmup

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 31 - Threat Hunting with YARA

- Course Overview
- Warmup
- Ops Challenge
- Lecture:
  - Threat Hunting
  - YARA
- Demo

---

<!-- .element class="main-title" -->
# Ops Challenge:

- &shy;<!-- .element:  data-fragment-index="2" -->**Ops Challenge 31** - Signature-based Malware Detection (part 1)

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 31 - Threat Hunting with YARA

- Course Overview
- Warmup
- Review
- Ops Challenge
- Lecture: <!-- .element style="color: red;" -->
  - Threat Hunting
  - YARA
- Demo

---

<!-- .element class="title-and-subtitle" -->

# Lecture:

## Class 31 - Threat Hunting with YARA

- **Threat Hunting**
- **YARA**

---

<!-- .element class="main-title" -->

# Threat Hunting

NOTE:
Is there a relevant Ch. in the Wiley Security+ (SY0-601) Study Guide?

---

<!-- .element class="split-screen-with-title" -->

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Threat Hunters** are experts on Tactics, Techniques, and Procedures (TTPs)
  - Highly knowledgeable of IT environments, malware attack vectors, and threat actors<!-- .element: class="fragment" data-fragment-index="2" -->
- Avg. US salary<!-- .element: class="fragment" data-fragment-index="3" -->
  - Entry level $63,446
    - (Source: SimplyHired)
  - Experienced $99,730 median
    - (Source: U.S. Bureau of Labor Statistics)

</div>

<div>

> **Threat Hunters** proactively search for cyber threats lurking undetected in a network

![Image](/ops-401-cybersecurity-guide/curriculum/class-31/slides/assets/31_01.png)
<!-- .element style="width: 78%"-->

</div>

</div>

NOTE:

Source: SQRRL

---

<!-- .element class="split-screen-with-title" -->

<div>

<div align="left" style="font-size: 35px">

1. &shy;<!-- .element: class="fragment" data-fragment-index="1" -->A hunt starts when we **create a Hypothesis about an observed activity**
2. &shy;<!-- .element: class="fragment" data-fragment-index="2" -->Hypotheses are **Investigated** via various **Tools and Techniques**
3. &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Tools and Techniques** uncover new malicious patterns of behavior and adversary TTPs
4. &shy;<!-- .element: class="fragment" data-fragment-index="4" -->From successful hunts allow us to **Inform and Enrich automated analytics**

</div>

<div>

> The **Threat Hunting Loop**: a four-stage model for successful threat hunting

![Image](/ops-401-cybersecurity-guide/curriculum/class-31/slides/assets/31_01.png)<!-- .element style="width: 78%"-->

</div>

</div>

NOTE:

Source: SQRRL

“The loop illustrates that hunting is most effective when it's habitual and adaptable. Let's break it down step by step starting from what we call trailheads:

### A hunt starts with **Creating a Hypothesis**, or an educated guess, about some type of activity that might be going on in your IT environment.

- An example of a hypothesis could be that users who have recently traveled abroad are at elevated risk of being targeted by state-sponsored threat actors, so you might begin your hunt by planning to look for signs of new malware on their laptops or assuming that their accounts are being misused around your network.
- Hypotheses are typically formulated by analysts based on any number of factors, including friendly and threat intelligence.
- There are various ways that a hunter might form a hypothesis.
- Often this involves laying out attack models and the possible tactics a threat might use, determining what would already be covered by automated alerting systems, and then formulating a hunting investigation of what else might be happening.

### Hypotheses are **Investigated** via various **Tools and Techniques**, including Linked Data Search and visualization.

- Effective tools will leverage both raw and linked data analysis techniques such as visualization, statistical analysis or machine learning to fuse disparate cybersecurity datasets.
- Linked Data Analysis is particularly effective at laying out the data necessary to address the hypotheses in an understandable way, and so is a critical component for a hunting platform.
- Linked data can even add weights and directionality to visualizations, making it easier to search large data sets and use more powerful analytics.
- Many other complementary techniques exist, including row-oriented techniques such as stack counting and datapoint clustering.
- Analysts can use these techniques to easily discover new malicious patterns in their data and reconstruct complex attack paths to reveal an attacker's Tactics, Techniques, and Procedures (TTPs).

### **Tools and Techniques** uncover new malicious patterns of behavior and adversary TTPs.

- This is a critical part of the hunting cycle.
- An example of this process could be that a previous investigation revealed that a user account has been behaving anomalously, with the account sending an unusually high amount of outbound traffic.
- After conducting a Linked Data investigation, it is discovered that the user's account was initially compromised via an exploit targeting a third party service provider of the organization.
- New hypotheses and analytics are developed to specifically discover other user accounts affiliated with similar third party service providers.

### From successful hunts allow us to **Inform and Enrich automated analytics**.

- Don't waste your team's time doing the same hunts over and over.
- Once you find a technique that works to bring threats to light, automate it so that your team can continue to focus on the next new hunt.
- Information from these hunts can also be used to improve existing detection mechanisms.
- For example, you may uncover information that leads to new threat intelligence or indicators of compromise.
- You might even create some friendly intelligence, that is, information about your own environment and how it is meant to operate, such as network maps, software inventories, lists of authorized web servers, etc.
- The more you know about your own network, the better you can defend it, so it makes sense to try to record and leverage new findings as you encounter them on your hunts.

---

<!-- .element class="split-screen-with-title" -->

<div>

<div align="left" style="font-size: 38px">

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Indicator of Compromise (IOC)**:

- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->The digital and informational clues that **Incident Responders** use to detect, diagnose, halt, and remediate **Malicious Activity** in their networks.
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Refers to the evidence on a device that points out to a security breach.

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-31/slides/assets/31_02.png)<!-- .element style="width: 120%"-->

> The Pyramid of Pain depicts how much pain it will cause the adversary when you are able to deny IOCs to them<!-- .element: class="fragment" data-fragment-index="4" -->

</div>

</div>

NOTE:

Source: [Cisa.gov](https://www.cisa.gov/news-events/events/understanding-indicators-compromise-ir108)

Image Source: include link to image source

---

<!-- .element class="main-title" -->

# YARA

NOTE:
Is there a relevant Ch. in the Wiley Security+ (SY0-601) Study Guide?

---

<!-- .element class="split-screen-with-title" -->

<div>

<div align="left" style="font-size: 35px">

- Used in:<!-- .element: class="fragment" data-fragment-index="1" -->
  - Digital forensics
  - Incident response
  - Reverse engineering
  - Threat hunting
  - Tools such as: SIEMs, IDS, Antimalware/Antivirus
- Open source<!-- .element: class="fragment" data-fragment-index="2" -->
- Works on many Operating Systems<!-- .element: class="fragment" data-fragment-index="3" -->

</div>

<div>

> **YARA**:
>
> Malware detection system using **boolean logic pattern matching** to identify targeted attacks and security threats in your environment

![Image](/ops-401-cybersecurity-guide/curriculum/class-31/slides/assets/31_03.png)<!-- .element style="width: 100%"-->

</div>

</div>

NOTE:

Image Source: include link to image source

---

<!-- .element class="split-screen-with-title" -->

<div>

<div align="left" style="font-size: 38px">

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->Targets files using a **boolean logic pattern matching system** based on:
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Regular Expressions** (Regex)
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Text strings**
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Hexadecimal**
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->A **YARA Rule** checks whether the target file meets the rule or not

</div>

<div>

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-31/slides/assets/31_04.png)<!-- .element style="width: 120%"-->

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-31/slides/assets/31_03.png)

</div>

</div>

NOTE:

- What is a YARA rule?
  - Checks whether the target file meets the rule or not
  - Often used to determine whether a file is malicious or not
- Syntax
  - Strings
    - Hexadecimal
    - Text
    - Regular expressions
  - Conditions
    - Boolean in nature. True/False.
  - Great unique strings and identifier for YARA rules
    - Mutexes
    - Unusual user agents
    - Registry keys
    - PBD paths
    - Encrypted config strings
  - What is ClamAV?
    - Open source anti-malware solution
    - Supports the YARA engine
    - YARA rules can either compliment or replace the ClamAV signatures database

---

<!-- .element class="split-screen-with-title" -->

<div>

<div align="left" style="font-size: 38px">

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->The **Portable Executable (PE)** format:

- A file format for executables, object code, DLLs and others used in 32-bit and 64-bit versions of Windows OS<!-- .element: class="fragment" data-fragment-index="2" -->
- Example: <!-- .element: class="fragment" data-fragment-index="3" -->
  - notepad.exe
  - cmd.exe

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-31/slides/assets/31_05.png)
<!-- .element style="width: 120%"-->

> Based on your Friday challenge activity, what is the significance of a .exe file in the security context?

</div>

</div>

NOTE:

Image Source: include link to image source

---

<!-- .element class="split-screen-with-title" -->

<div>

<div align="left">

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Clam AntiVirus (ClamAV)** is an open source antimalware toolkit

- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->Designed to **scan files quickly**
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Great for **email gateway scanning**
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->Maintains a signed **malware signatures database**
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->Supports the **YARA Engine**:
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->YARA rules can either complement or replace the ClamAV **signatures database**
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->ClamAV can decompress an archived file and run the **YARA Engine** on it

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-31/slides/assets/31_06.png)
<!-- .element style="width: 100%"-->

> How can YARA rules be practically applied to defensive SecOps?

</div>

</div>

NOTE:

Image Source: include link to image source

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 31 - Threat Hunting with YARA

- Course Overview
- Warmup
- Review
- Ops Challenge
- Lecture:
  - Threat Hunting
  - YARA
- Demo <!-- .element style="color: red;" -->

---

<!-- .element class="main-title" -->
# Demo & Lab

## Write and test YARA rules

NOTE:

### Import OVA File

### Demo: Write and test YARA rules
