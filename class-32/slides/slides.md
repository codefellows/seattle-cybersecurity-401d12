<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 32

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

Daily TODOs

- Hide/unhide slides to show as necessary
- Toggle presentation mode on and screen share this first slide when you initialize recording on Zoom to indicate class number

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 32 - Malware Traffic Analysis

- Course Overview <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Review
  - Threat Hunting with YARA
- Ops Challenge
- Lecture:
  - Malware Traffic Analysis
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/0_01.png)
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

- &shy;<!-- .element style="color: red;" -->**Class 32** - Malware Traffic Analysis with Wireshark

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

- **Class 31** - Signature-based Malware Detection (Part 1 of 3)

<br>

- &shy;<!-- .element style="color: red;" -->**Class 32** - Signature-based Malware Detection (Part 2 of 3)

<br>

- **Class 33** - Signature-based Malware Detection (Part 3 of 3)

<br>

- **Class 34** - Mock Interviews

<br>

- **Class 35** - Web Vulnerability Scanning with Nmap

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/0_03.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 32 - Malware Traffic Analysis

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

## Class 32 - Malware Traffic Analysis

- Course Overview
- Warmup
- Review <!-- .element style="color: red;" -->
- Ops Challenge
- Lecture:
  - Malware Traffic Analysis
- Demo

---

<!-- .element class="main-title" -->
# Review:

## Threat Hunting with YARA

NOTE:

---

<!-- .element class="split-screen-with-title" -->

<div>

<div>

1. &shy;<!-- .element: class="fragment" data-fragment-index="1" -->A hunt starts when we **create a Hypothesis about an observed activity**
2. &shy;<!-- .element: class="fragment" data-fragment-index="2" -->Hypotheses are **Investigated** via various **Tools and Techniques**
3. &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Tools and Techniques** uncover new malicious patterns of behavior and adversary TTPs
4. &shy;<!-- .element: class="fragment" data-fragment-index="4" -->From successful hunts allow us to **Inform and Enrich automated analytics**

</div>

<div>

> The **Threat Hunting Loop**: a four-stage model for successful threat hunting

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/31_01.png)
<!-- .element style="width: 78%"-->

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

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->Targets files using a **boolean logic pattern matching system** based on:
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Regular Expressions** (Regex)
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Text strings**
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Hexadecimal**
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->A **YARA Rule** checks whether the target file meets the rule or not

</div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Used in:**
  - Digital forensics
  - Incident response
  - Reverse engineering
  - Threat hunting

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/31_03.png)

</div>

</div>

NOTE:

Image Source: include link to image source

---

<!-- .element class="split-screen-with-title" -->

<div>

<div>

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Clam AntiVirus (ClamAV)** is an open source antimalware toolkit

- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->Designed to **scan files quickly**
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Great for **email gateway scanning**
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->Maintains a signed **malware signatures database**
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->Supports the **YARA Engine**:
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->YARA rules can either complement or replace the ClamAV **signatures database**
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->ClamAV can decompress an archived file and run the **YARA Engine** on it

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/31_06.png)
<!-- .element style="width: 100%"-->

> How can YARA rules be practically applied to defensive SecOps?

</div>

</div>

NOTE:

Image Source: include link to image source

---

<!-- .element class="main-title" -->

# Review:

## Lab 31

NOTE:

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 32 - Malware Traffic Analysis

- Course Overview
- Warmup
- Review
- Ops Challenge <!-- .element style="color: red;" -->
- Lecture:
  - Malware Traffic Analysis
- Demo

---

<!-- .element class="main-title" -->
# Ops Challenge:

- &shy;<!-- .element: data-fragment-index="1" -->**Ops Challenge 32** - Signature-based Malware Detection (part 2)

NOTE:

# Review: Ops Challenge 31

# Introduce: Ops Challenge 32

- Review Ops Challenge 31
- Ops Challenge 32 - Signature-based Malware Detection (part 2)

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 32 - Malware Traffic Analysis

- Course Overview
- Warmup
- Review
- Ops Challenge
- Lecture: <!-- .element style="color: red;" -->
  - Malware Traffic Analysis
- Demo

---

<!-- .element class="title-and-subtitle" -->

# Lecture:

## Class 32 - Malware Traffic Analysis

- **Malware Traffic Analysis with Wireshark**

---

<!-- .element class="main-title" -->
# Malware Traffic Analysis

NOTE:
Is there a relevant Ch. in the Wiley Security+ (SY0-601) Study Guide?

---

<!-- .element class="split-screen-with-title" -->

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Malware incidents** leave a trail of bread crumbs: **logs and packets**
- What have you been practicing doing?<!-- .element: class="fragment" data-fragment-index="2" -->
  - **Log generation and ingestion**
  - **Packet capture**
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->We can use **Behavior Patterns** to spot suspicious activities
- We can pinpoint "invisible" threats<!-- .element: class="fragment" data-fragment-index="4" -->
- Ultimately, minimize damage and profit loss<!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

> **Malware Traffic Analysis** involves monitoring and analyzing network communications to detect signs of malware-related activities

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/32_01.png)
<!-- .element style="width: 75%"-->

</div>

</div>

NOTE:

- Why perform traffic analysis?
  - Malware incidents leave a bread crumb trail, e.g. logs and packets
  - Use behavior patterns to spot suspicious activities
  - Pinpoint "invisible" threats
  - Minimize damage and profit loss
  - Traffic analysis can have different purposes or contexts. Threat hunting is one context you'd perform traffic analysis in. Today's focus is on capturing malware behavior patterns using traffic analysis tools and techniques.

---

<!-- .element class="split-screen-with-title" -->

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->Traffic analysis consists of capturing network traffic into a **Packet Capture file (PCAP)**, then analyzing that file
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->Packets may contain valuable evidence in the form of:
  - IP Addresses, Domain names, and URLs
  - File Hashes
  - DNS Queries
  - Traffic volumes and patterns
  - Patterns of Behavior
  - Network Ports and protocols

</div>

<div>

> During an **investigation** we seek to answer **who**, **what**, **when**, **where**, and **why**.

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/32_01.png)
<!-- .element style="width: 75%"-->

</div>

</div>

NOTE:

---

<!-- .element class="split-screen-with-title" -->

# Malware Traffic Analysis: Indicators of Compromise

<div>

<div align="left" style="font-size: 25px">

- Unusual Outbound Network Traffic<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="1" -->
- Anomalies in Privileged User Account Activity<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="2" -->
- Geographical Irregularities<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="3" -->
- Log-In Red Flags<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="4" -->
- Increases in Database Read Volume<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="5" -->
- HTML Response Sizes<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="6" -->
- Large Numbers of Requests for the Same File<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="7" -->
- Mismatched Port-Application Traffic<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="8" -->
- Suspicious Registry or System File Changes<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="9" -->
- Unusual DNS Requests<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="10" -->
- Unexpected Patching of Systems<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="11" -->
- Mobile Device Profile Changes<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="12" -->
- Bundles of Data in the Wrong Place<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="13" -->
- Web Traffic with Unhuman Behavior<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="14" -->

</div>

<div>

> An **Indicator of Compromise (IOC)** is a piece of digital forensics that suggests that an endpoint or network may have been breached

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/32_01.png)
<!-- .element style="width: 75%"-->

</div>

Source: [Crowdstrike.com](https://www.crowdstrike.com/cybersecurity-101/indicators-of-compromise/)

</div>

NOTE:

- What is an IOC?
  - Indicators of compromise (IOC) are pieces of forensic data that identify potentially malicious activity on a system or network.
    - Can be system log entries, data objects such as malicious system files recovered from a compromised machine, or network traffic indicating suspicious activity on the network.
      - Data objects determined to be IOCs are commonly referred to as artifacts.
      - Note that artifacts can be hashed to produce a unique signature, which is how signature-based malware detection software is able to determine if a file is malware.
    - IOCs help us answer the question, "What happened?"
    - Identified after the attack or incident has taken place.
    - Alerts, system log entries, files
    - IOCs are the "breadcrumbs" that lead to detection
    - Sometimes not the easiest to find
    - Here are some additional IOC examples that you may encounter in field:
      - Unusual Outbound Network Traffic
      - Anomalies in Privileged User Account Activity
      - Geographical Irregularities
      - Log-In Red Flags
      - Increases in Database Read Volume
      - HTML Response Sizes
      - Large Numbers of Requests for the Same File
      - Mismatched Port-Application Traffic
      - Suspicious Registry or System File Changes
      - Unusual DNS Requests
      - Unexpected Patching of Systems
      - Mobile Device Profile Changes
      - Bundles of Data in the Wrong Place
      - Web Traffic with Unhuman Behavior
      - Signs of DDoS Activity

---

<!-- .element class="split-screen-with-title" -->

# Malware Traffic Analysis: Indicators of Attack

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**"What is happening and why?"**
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**OpenIOC** is a framework that attempts to standardize the workflow of reporting IOCs:
  - Initial leads<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="3" -->
  - IOC Creation<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="4" -->
  - Deploy IOC<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="5" -->
  - Identify Suspect Systems<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="6" -->
  - Preserve/Collect Evidence<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="7" -->
  - Analyze Data<!-- .element: class="fragment fade-in-then-semi-out" data-fragment-index="8" -->

</div>

<div>

> An **Indicator of Attack** is similar to an **IOC** but is instead a forensic analysis of attack taking place right now.

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/32_02.png)
<!-- .element style="width: 100%"-->

</div>

</div>

NOTE:

- What is an indicator of attack?
  - An indicator of attack (IoA) is similar to an IOC but is a forensic piece of evidence associated with an attack in progress.
  - Answers "What is happening and why?"

---

<!-- .element class="text-only" -->
# Malware Traffic Analysis

<div>

<div align="left" style="font-size: 35px">

- Key Features:<!-- .element: class="fragment" data-fragment-index="2" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Structured Representation**
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Common Vocabulary**
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Contextual Information**
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Sharing and Interoperability**
  - &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Extensibility**
- &shy;<!-- .element: class="fragment" data-fragment-index="8" -->Developed by the **OASIS Cyber Threat Intelligence (CTI)** Committee
  - &shy;<!-- .element: class="fragment" data-fragment-index="9" -->Now a component of the **Structured Threat Information eXpression (STIX)** framework

</div>

<div>

> **CybOX (Cyber Observable Expression):**
>
> An open standard for capturing and sharing structured information about cyber observables and events.

&shy;<!-- .element: class="fragment" data-fragment-index="1" -->**CybOX is to IOC as SQL is to relational database transactions.**

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/32_03.png)
<!-- .element style="width: 100%"-->

</div>

</div>

NOTE:

Source: [ChatGPT](https://chat.openai.com/share/10ca4f4ea-c924-4648-9c06-1f691c42b7da)

CybOX, short for "Cyber Observable Expression," is an open standard for capturing and sharing structured information about cyber observables and events. It is a standardized way of representing and exchanging cyber threat intelligence, allowing security professionals and organizations to share information about threats, attacks, and indicators of compromise in a structured and standardized format.

CybOX was developed by the MITRE Corporation as part of the Cyber Threat Intelligence (CTI) initiative. It provides a common language for describing various aspects of cyber observables, which are the pieces of information that can be used to detect, analyze, and respond to cyber threats. Observables include things like IP addresses, domain names, file hashes, registry keys, network connections, and more.

Key features of CybOX include:

1. **Structured Representation:** CybOX uses a structured XML-based format to represent cyber observables, events, and relationships between them. This structured approach makes it easier to share and compare threat intelligence across different organizations and tools.

2. **Common Vocabulary:** CybOX defines a standardized vocabulary and data model for describing different types of cyber observables, ensuring consistency and clarity in threat intelligence sharing.

3. **Contextual Information:** CybOX allows for the inclusion of contextual information about the observables, such as timestamps, locations, and relationships to other observables. This helps provide a more complete picture of the threat landscape.

4. **Sharing and Interoperability:** By using a standardized format, CybOX enables security professionals to share threat intelligence with each other and across different security tools and platforms, enhancing collaboration and interoperability.

5. **Extensibility:** CybOX is designed to be extensible, allowing organizations to add custom fields and attributes to the standard schema to accommodate specific use cases or types of observables.

CybOX is one of the key standards within the Structured Threat Information eXpression (STIX) framework, which is an overarching standard for sharing cyber threat intelligence. STIX provides a way to package and exchange threat intelligence in a comprehensive manner, combining CybOX for observables and TAXII (Trusted Automated eXchange of Indicator Information) for transport and exchange.

Overall, CybOX plays a crucial role in the field of cyber threat intelligence by providing a common language and format for expressing and sharing information about cyber threats, attacks, and indicators of compromise.

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 32 - Malware Traffic Analysis

- Course Overview
- Warmup
- Review
- Ops Challenge
- Lecture:
  - Malware Traffic Analysis
- Demo <!-- .element style="color: red;" -->

---

<!-- .element class="main-title" -->
# Demo & Lab

### Find Malicious Attack with Wireshark & Incident Reporting

NOTE:

### Import OVA File

### Demo: Find Malicious Attack with Wireshark & Incident Reporting

- How do we get the MD5 Hash of a target file in FLARE VM (Win10)?
  - `CertUtil -hashfile yourFileName MD5`
  - `CertUtil -hashfile yourFileName SHA256`
  - You can then upload the hash to VirusTotal. This is preferred over uploading the actual file. Discuss - Why?
  - Malware components won't always test positive on VirusTotal, but may still be relevant to the investigation. Why?
- How do we use alerts to inform our Wireshark analysis?
  - Open alerts for demo2 and use ports and IPs to filter Wireshark. Surprisingly simple yet effective.
- DO: Show class the Wireshark cheat sheet and share the link
- Refresh on how to filter Wireshark PCAPs by:
  - IP
  - TCP Port
  - Source IP
  - Dest IP
  - URL
  - Host name
- How to "follow a TCP stream" to reconstruct the data
  - Right click a TCP packet and Follow > TCP Stream.
- How to export a file from HTTP traffic
  - File > Export File > HTTP
- Walk through a demo together in class that's similar to today's lab
