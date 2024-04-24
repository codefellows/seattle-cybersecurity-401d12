<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 11

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 11 - Foundational SIEM Operations

- Course Overview<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
  - Linux Data Streams
  - TCP Flags
- Review
  - Advanced Logging with Sysmon
- Lecture
  - Foundational SIEM Operations
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/00_01.png)
<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)

</div>

</div>

---

<!-- .element class="title-with-text" -->
# Module 3 Labs

### Security Operations

<div align="left" style="font-size: 45px">

- &shy;<!-- .element style="color: red;" -->**Class 11** - Foundational SIEM Operations

<br>

- **Class 12** - Log Analysis with Splunk

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

- &shy;<!-- .element style="color: red;" -->**Class 11** - Network Security Tool Pt. 1 of 3

<br>

- **Class 12** - Network Security Tool Pt. 2 of 3

<br>

- **Class 13** - Network Security Tool Pt. 3 of 3

<br>

- **Class 14** - Mock Interviews

<br>

- **Class 15** - Brute Force Attacks

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Ops Challenge: Linux Data Streams

---

<!-- .element class="text-only" -->
# Linux Data Streams

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->Linux data streams use **Standard Input/Output (STDIO)** for program input and output
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**STDIN (file handle 0)** is standard input
    - Typically from the keyboard <!-- .element: class="fragment" data-fragment-index="3" -->
    - Can be redirected from any file <!-- .element: class="fragment" data-fragment-index="4" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**STDOUT (file handle 1)** is standard output
    - Sends the data stream to the display by default <!-- .element: class="fragment" data-fragment-index="6" -->
    - Can be redirected to a file or to another program <!-- .element: class="fragment" data-fragment-index="7" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**STDERR (file handle 2)** is standard error
    - By default sent to the display <!-- .element: class="fragment" data-fragment-index="9" -->

NOTE:

Note that streams are handled like files
Pipes and redirects work on Linux data streams

---

<!-- .element class="image-and-title" -->
# Linux Data Streams

<br>

Normal data stream:

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_01.png)
Source: Github

NOTE:

---

<!-- .element class="image-and-title" -->
# Linux Data Streams

<br>

Redirected data stream:

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_02.png)
Source: Github

NOTE:

---

<!-- .element class="main-title" -->
# Ops Challenge: TCP Flags

---

<!-- .element class="split-screen-with-title" -->
# TCP Flags

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**TCP Header Flags**
  - Individual bits within the TCP header <!-- .element: class="fragment" data-fragment-index="2" -->
  - Server to control and manage TCP communication <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Common Flags:**
  - SYN
  - ACK
  - PSH
  - URG
  - RST
  - FIN

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_03.png)

</div>

</div>
---

<!-- .element class="main-title" -->
# Review:

## Advanced Event Logging

---

<!-- .element class="split-screen-with-title" -->
# Incident Response Process

<div>

<div>

- Preparation <!-- .element: class="fragment" data-fragment-index="1" -->
- Identification <!-- .element: class="fragment" data-fragment-index="2" -->
- Containment <!-- .element: class="fragment" data-fragment-index="3" -->
- Eradication <!-- .element: class="fragment" data-fragment-index="4" -->
- Recovery <!-- .element: class="fragment" data-fragment-index="5" -->
- Post-incident activity <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_04.png)
Source: Medium

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Incident Response Process

<div>

<div>

- Preparation <!-- .element: class="fragment" data-fragment-index="1" -->
- Detection & Analysis <!-- .element: class="fragment" data-fragment-index="2" -->
- Containment, Eradication, and Recovery <!-- .element: class="fragment" data-fragment-index="3" -->
- Post-Incident Activities <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_05.png)

Source: NIST SP800-61: The Incident Response Lifecycle

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Teams

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Incident Response teams**
  - CIRT <!-- .element: class="fragment" data-fragment-index="2" -->
  - CERT <!-- .element: class="fragment" data-fragment-index="3" -->
  - CSIRT <!-- .element: class="fragment" data-fragment-index="4" -->
  - SOC <!-- .element: class="fragment" data-fragment-index="5" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Other roles**
  - Legal <!-- .element: class="fragment" data-fragment-index="7" -->
  - HR <!-- .element: class="fragment" data-fragment-index="8" -->
  - Marketing <!-- .element: class="fragment" data-fragment-index="9" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_04.png)
Source: Medium

</div>

</div>

---

<!-- .element class="main-title" -->
# SOC Tools

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_06.png)
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

<!-- .element class="text-only" -->
# SOC Concepts

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->A **security incident** is an event or series of events that compromise the confidentiality, integrity, or availability of an organization's information, systems, or network.
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Incident Response (IR)** is the process by which an organization handles a data breach or cyberattack, including remediation
- The SOC team is responsible for monitoring, detecting, responding to, and mitigating security threats and incidents. <!-- .element: class="fragment" data-fragment-index="3" -->
- Threat hunters, however, do not perform the full IR lifecycle and instead focus on identification and detection <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

NOTE:

- What is an "incident"?
  - An event involving the breach of a system's security policy in order to affect its integrity or availability and/or the unauthorized access or attempted access to a system or systems
- What is "incident response"?
  - Process by which an organization handles a data breach or cyberattack, including the way the organization attempts to manage the consequences of the attack or breach (the “incident”)
  - A computer incident response team (CIRT) exists to enact playbooks against incidents.
- What is the NIST incident response lifecycle?
  - Preparation
  - Detection & Analysis
  - Containment, Eradication and Recovery
  - Post-Incident Activities

---

<!-- .element class="text-only" -->
# SOC Tools

- SIEM <!-- .element: class="fragment" data-fragment-index="1" -->
- EDR/XDR <!-- .element: class="fragment" data-fragment-index="2" -->
- IDS/IPS <!-- .element: class="fragment" data-fragment-index="3" -->
- Firewalls <!-- .element: class="fragment" data-fragment-index="4" -->
- Vulnerability Scanners <!-- .element: class="fragment" data-fragment-index="5" -->
- Investigation tools <!-- .element: class="fragment" data-fragment-index="6" -->
- Vulnerability Feeds and DB <!-- .element: class="fragment" data-fragment-index="7" -->
- Ticketing solutions <!-- .element: class="fragment" data-fragment-index="8" -->

---

<!-- .element class="text-only" -->
# SOC Tools

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Log Aggregation**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Security Information and Event Management (SIEM)** is software that aggregates and analyzes activity from many different resources in your IT infrastructure
    - Examples <!-- .element: class="fragment" data-fragment-index="3" -->
      - Splunk (commercial) <!-- .element: class="fragment" data-fragment-index="4" -->
      - Elastic/ELK Stack (open source) <!-- .element: class="fragment" data-fragment-index="5" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Performs**
    - Event and log collection <!-- .element: class="fragment" data-fragment-index="7" -->
    - Layered centric views or heterogeneous <!-- .element: class="fragment" data-fragment-index="8" -->
    - Normalization <!-- .element: class="fragment" data-fragment-index="9" -->
    - Correlation <!-- .element: class="fragment" data-fragment-index="10" -->
    - Adaptability (scalable) <!-- .element: class="fragment" data-fragment-index="11" -->
    - Reporting and alerting <!-- .element: class="fragment" data-fragment-index="12" -->
    - Log management <!-- .element: class="fragment" data-fragment-index="13" -->

---

<!-- .element class="main-title" -->
# SIEM Fundamentals

---

<!-- .element class="split-screen-with-title" -->
# Splunk Concepts

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is Splunk?**
  - A widely used software designed for searching, analyzing, and visualizing machine-generated data in real-time.
  - Primarily used for log and event data management and is especially valuable for monitoring the security of IT systems.
- Another major SIEM in this industry is Elastic/ELK Stack <!-- .element: class="fragment" data-fragment-index="2" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_07.png)
Source: Splunk

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Splunk Concepts

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Search Processing Language (SPL)**
  - The query language used in Splunk software <!-- .element: class="fragment" data-fragment-index="2" -->
  - Designed specifically for querying and analyzing data and filter large volumes of data <!-- .element: class="fragment" data-fragment-index="3" -->
  - Syntax originally based on the Unix pipeline and SQL <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**SPL scope:**
  - Data searching <!-- .element: class="fragment" data-fragment-index="6" -->
  - Filtering <!-- .element: class="fragment" data-fragment-index="7" -->
  - Modification <!-- .element: class="fragment" data-fragment-index="8" -->
  - Manipulation <!-- .element: class="fragment" data-fragment-index="9" -->
  - Insertion <!-- .element: class="fragment" data-fragment-index="10" -->
  - Deletion <!-- .element: class="fragment" data-fragment-index="11" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_08.png)
Source: Splunk

</div>

</div>

---

<!-- .element class="text-only" -->
# Splunk Concepts

- Stages of the SIEM data pipeline in Splunk <!-- .element: class="fragment" data-fragment-index="1" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Stage 1: Data Input**
    - Data accessed from the source and turned into 64k blocks <!-- .element: class="fragment" data-fragment-index="3" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Stage 2: Data Storage**
    - Parsing phase <!-- .element: class="fragment" data-fragment-index="5" -->
      - Splunk examines, analyzes, and transforms the data <!-- .element: class="fragment" data-fragment-index="6" -->
    - Indexing phase <!-- .element: class="fragment" data-fragment-index="7" -->
      - Splunk writes parsed events to the index queue. <!-- .element: class="fragment" data-fragment-index="8" -->
      - Individual indexes are created as objects in Splunk, and you define what scope of data gets monitored and goes into each index. <!-- .element: class="fragment" data-fragment-index="9" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="10" -->**Stage 3: Data Searching**
    - How data is accessed, used, and viewed is controlled. <!-- .element: class="fragment" data-fragment-index="11" -->

NOTE:

- STAGE 1: Data Input
  - In this stage, all the data will be accessed from the source. The metadata keys include the following:
    - Hostname
    - Source
    - Source type of data
- STAGE 2: Data Storage
  - This stage is carried out in two phases:
    - Parsing
      - In the parsing phase, the Splunk software examines, analyzes, and transforms the data. This phase is called event processing where all the data sets are broken down into different events. The following activities happen within this parsing phase.
      - Stream of data is broken down into individual lines
      - Identifies and sets time stamps
      - Transforms the metadata and events according to regex standards.
    - Indexing
      - In the indexing phase, the Splunk software writes parsed events to the index queue. The main benefit of using this is to make sure the data is easily available for anyone at the time of the search.
      - Individual indexes are created as objects in Splunk, and you define what scope of data gets monitored and goes into each index.
- STAGE 3: Data Searching
  - How data is accessed, used, and viewed is controlled.
  - Splunk will store user-defined knowledge objects like reports, event types, and alerts.

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_09.png)
Source: Splunk

</div>

</div>

NOTE:

- Splunk Indexer: Parsing data and Indexing the data
  - Splunk Indexer tool helps the data to be converted into events and indexed so that it is easy for performing search operations efficiently.
  - Data from forwarders gets parsed (incl. unwanted data removed) then index it.

---

<!-- .element class="split-screen-with-title" -->
# Splunk Architecture

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Search Head**
  - In a distributed search environment, a search head is a Splunk instance that handles: <!-- .element: class="fragment" data-fragment-index="2" -->
    - Search management functions <!-- .element: class="fragment" data-fragment-index="3" -->
    - Directing search requests to a set of search peers <!-- .element: class="fragment" data-fragment-index="4" -->
    - Merging the results back to the user <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_09.png)
Source: Splunk

</div>

</div>

NOTE:

- Search Head: User interface where the user will have an option to search, analyze and report data.
  - Search head: User interface where data is retrieved by keyword
  - Search peer: Search results & indexing

---

<!-- .element class="split-screen-with-title" -->
# Splunk Architecture

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Forwarders**
  - Provide reliable, secure data collection from various sources and deliver the data to Splunk for indexing and analysis. <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Universal forwarders:**
  - Forward data from remote systems securely in real time <!-- .element: class="fragment" data-fragment-index="4" -->
  - Have minimal impact on endpoint performance <!-- .element: class="fragment" data-fragment-index="5" -->
  - Provide many features such as SSL, compression and buffering <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_09.png)
Source: Splunk

</div>

</div>

NOTE:

- Splunk Forwarder: Forward the data
  - Splunk Universal Forwarder
  - Splunk Heavy Forwarder

---

<!-- .element class="text-only" -->
# Splunk Architecture

- What data sources does Splunk support? <!-- .element: class="fragment" data-fragment-index="1" -->
  - Many! Includes old-fashioned syslog <!-- .element: class="fragment" data-fragment-index="2" -->
- What data sources will Splunk typically be setup with? <!-- .element: class="fragment" data-fragment-index="3" -->
  - Enterprise with multiple Windows Servers will forward their logs to Splunk <!-- .element: class="fragment" data-fragment-index="4" -->
- What ingestion techniques does Splunk support? <!-- .element: class="fragment" data-fragment-index="5" -->
  - Syslog via Sysmon <!-- .element: class="fragment" data-fragment-index="6" -->
  - Splunk Universal Data Forwarder <!-- .element: class="fragment" data-fragment-index="7" -->
- What are some common challenges/problems encountered with ingesting logs from many sources? <!-- .element: class="fragment" data-fragment-index="8" -->
  - Inconsistent time/date formatting <!-- .element: class="fragment" data-fragment-index="9" -->
  - Syntax issues <!-- .element: class="fragment" data-fragment-index="10" -->

NOTE:

- What data sources does Splunk support?
  - Many! Includes old-fashioned syslog.
- What data sources will Splunk typically be setup with?
  - Enterprise with multiple Windows Servers will forward their logs to Splunk
- What ingestion techniques does Splunk support?
  - Syslog via Sysmon
  - Splunk Universal Data Forwarder
- What are some common challenges/problems encountered with ingesting logs from many sources?
  - Inconsistent time/date formatting
  - Syntax issues

---

<!-- .element class="image-and-title" -->

# Splunk Operations

- How do SPL queries work?

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_10.png)
Source: Splunk

---

<!-- .element class="split-screen-with-title" -->
# Splunk Operations

- Search assistant helps you build the queries

<div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_11.png)

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-11/slides/assets/11_12.png)

</div>

</div>

Source: Splunk

---

<!-- .element class="main-title" -->
# Demo
