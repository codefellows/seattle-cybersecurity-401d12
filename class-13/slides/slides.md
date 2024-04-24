<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 13

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 13 - Reconstructing a Cloud Attack

- Course Overview<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - Log Analysis with Splunk
- Lecture
  - Reconstructing a Cloud Attack using Log Data
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/00_01.png)
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

- **Class 12** - Log Analysis with Splunk

<br>

- &shy;<!-- .element style="color: red;" -->**Class 13** - Reconstructing a Cloud Attack

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

- **Class 12** - Network Security Tool Pt. 2 of 3

<br>

- &shy;<!-- .element style="color: red;" -->**Class 13** - Network Security Tool Pt. 3 of 3

<br>

- **Class 14** - Mock Interviews

<br>

- **Class 15** - Brute Force Attacks

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Review:

# Log Analysis with Splunk

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/12_02.png)
Source: FireEye

</div>

</div>

NOTE:

- An advanced persistent threat (APT) is “a skilled and determined cyber criminal [who] can use multiple vectors and entry points to navigate around defenses, breach your network in minutes and evade detection for months. APTs present a challenge for organizational cyber security efforts.” -FireEye

Visit <https://www.fireeye.com/current-threats/apt-groups.html>

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/12_05.png)
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/12_08.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/12_09.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/12_10.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Threat Taxonomy

---

<!-- .element class="split-screen-with-title" -->
# Threat Taxonomy

<div>

<div>

- A classification system used to categorize and organize various types of security threats, vulnerabilities and risks. <!-- .element: class="fragment" data-fragment-index="1" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Tactics, techniques, and procedures (TTPs)** are “patterns of activities or methods associated with a specific threat actor or group of threat actors”
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->The global repository of known TTPs is maintained by MITRE and is known as the **MITRE ATT&CK®  matrix**

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_01.png)

</div>

</div>

NOTE:

- Tactics, techniques, and procedures (TTPs) are “patterns of activities or methods associated with a specific threat actor or group of threat actors” -Definitive Guide to Cyber Threat Intelligence
- The global repository of known TTPs is maintained by MITRE and is known at the MITRE ATT&CK® matrix

---

<!-- .element class="text-and-image" -->
# Threat Taxonomy

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**MITRE ATT&CK**
  - A knowledge base of adversary behavior <!-- .element: class="fragment" data-fragment-index="2" -->
    - Based on real-world observations <!-- .element: class="fragment" data-fragment-index="3" -->
    - Free and open, globally accessible <!-- .element: class="fragment" data-fragment-index="4" -->
    - A common language <!-- .element: class="fragment" data-fragment-index="5" -->
    - Community-driven <!-- .element: class="fragment" data-fragment-index="6" -->
  - Used for developing threat models and methodologies <!-- .element: class="fragment" data-fragment-index="7" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_02.png)

NOTE:

- What is MITRE ATT&CK®
  - MITRE ATT&CK is a "globally-accessible knowledge base of adversary tactics and techniques based on real-world observations."
  - "Used for developing threat models and methodologies"
  - Adversarial Tactics, Techniques, and Common Knowledge (ATT&CK™) for enterprise is a framework which describes the adversarial actions or tactics from Initial Access (Exploit) to Command & Control (Maintain).
  - A knowledge base of adversary behavior
    - Based on real-world observations
    - Free and open, globally accessible
    - A common language
    - Community-driven
    - Adversaries use TTPs: Tactics, Techniques, and Procedures
  - ATT&CK is a knowledge base of cyber adversary behavior and taxonomy for adversarial actions across their lifecycle. ATT&CK has several parts:
    - PRE-ATT&CK: Reconnaissance and infrastructure setup
    - ATT&CK: Enterprise IT networks and cloud
    - ATT&CK for Mobile: Behavior against mobile devices

---

<!-- .element class="split-screen-with-title" -->
# Threat Taxonomy

- ATT&CK defines the following tactics used in a cyberattack: <!-- .element: class="fragment" data-fragment-index="1" -->

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**TA0001**: Initial Access
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**TA0002**: Execution
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**TA0003**: Persistence
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**TA0004**: Privilege Escalation
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**TA0005**: Defense Evasion
- &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**TA0006**: Credential Access

</div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="8" -->**TA0007**: Discovery
- &shy;<!-- .element: class="fragment" data-fragment-index="9" -->**TA0008**: Lateral Movement
- &shy;<!-- .element: class="fragment" data-fragment-index="10" -->**TA0009**: Collection
- &shy;<!-- .element: class="fragment" data-fragment-index="11" -->**TA0010**: Exfiltration
- &shy;<!-- .element: class="fragment" data-fragment-index="12" -->**TA0011**: Command and Control (C2)

</div>

</div>

- Tactics are high level categories that contain techniques. Techniques can contain sub-techniques. <!-- .element: class="fragment" data-fragment-index="13" -->

NOTE:

DO:

- Visit TA0001

- TTPs referenced by today's lab
  - [TA0001](https://attack.mitre.org/tactics/TA0001)
  - [TA0003](https://attack.mitre.org/tactics/TA0003)
  - [TA0004](https://attack.mitre.org/tactics/TA0004)
  - [TA0005](https://attack.mitre.org/tactics/TA0005)
  - [TA0009](https://attack.mitre.org/tactics/TA0009)

---

<!-- .element class="split-screen-with-title" -->
# Threat Taxonomy

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**TA0001: Initial Access** - The adversary is trying to get into your network.
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**T1566: Phishing** - Adversaries may send phishing messages to gain access to victim systems.
    - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->.**001: Spearphishing Attachment** - Adversaries may send spearphishing emails with a malicious attachment in an attempt to gain access to victim systems.

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_03.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_04.png)
Source: Mitre, Pixabay

</div>

</div>

NOTE:
<https://attack.mitre.org/tactics/TA0001/>

---

<!-- .element class="text-and-image" -->
# MITRE D3FEND

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->A complementary framework to the **MITRE ATT&CK™** matrix
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->The **D3FEND** matrix helps cybersecurity professionals better defend and protect networks and information technology assets
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Provides defensive techniques that can be applied to counter the activities of threat actors detailed within the **MITRE ATT&CK™** matrix

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_02.png)

NOTE:

- MITRE D3FEND is a complementary framework to the MITRE ATT&CK™ matrix
- The D3FEND matrix helps cybersecurity professionals better defend and protect networks and information technology assets
- Provides defensive techniques that can be applied to counter the activities of threat actors detailed within the MITRE ATT&CK™ matrix

---

<!-- .element class="main-title" -->
# APIs

---

<!-- .element class="split-screen-with-title" -->
# API

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Application Programming Interface (API)**
  - Used to allow the integration of different software systems, allowing them to work together, share data, and perform tasks. <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Why do we need to analyze API interactions in the cloud?**
  - Security vulnerabilities <!-- .element: class="fragment" data-fragment-index="4" -->
  - Increasingly utilized for automation <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_05.png)
Source: API,  I'd Rather Be Writing

</div>

</div>

NOTE:

- Why do we need to analyze API interactions in the cloud?
  - APIs have a reputation for having security vulnerabilities, yet are increasingly being utilized to keep pace with automation

---

<!-- .element class="split-screen-with-title" -->
# REST API

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Representational State Transfer (REST) API**
  - A type of modern architectural style of API facilitating machine to machine communication
  - Pass in a noun and a verb <!-- .element: class="fragment" data-fragment-index="2" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Uses HTTP methods:**
    - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**GET** to fetch data
    - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**PUT** to alter the state of data (such as an object, file or block)
    - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**POST** to create data
    - &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**DELETE** methods to eliminate it

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_06.png)
Source: I'd Rather Be Writing

</div>

NOTE:

- What is a REST API?
  - Representational State Transfer (REST) API is a type of modern architectural style of API facilitating machine to machine communication
  - Formats: JSON, XML, or HTML
  - Pass in a noun and a verb
  - Uses HTTP methods:
    - GET to fetch data
    - PUT to alter the state of data (such as an object, file or block)
    - POST to create data
    - DELETE methods to eliminate it

---

<!-- .element class="main-title" -->
# Reconstructing a Cloud Attack

---

<!-- .element class="split-screen-with-title" -->
# Amazon S3

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is AWS S3?**
  - A cloud data storage service <!-- .element: class="fragment" data-fragment-index="2" -->
  - Buckets contain objects <!-- .element: class="fragment" data-fragment-index="3" -->
  - Objects consist of data and metadata <!-- .element: class="fragment" data-fragment-index="4" -->
    - Example: puppies.jpg <!-- .element: class="fragment" data-fragment-index="5" -->
  - Keys are the unique identifier of an object within a bucket <!-- .element: class="fragment" data-fragment-index="6" -->
  - Regions contain the buckets you create <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_07.png)
Source: Medium

</div>

</div>

NOTE:

- What is an AWS S3 Bucket?
  - S3 Buckets are a part of Amazon Simple Storage Service (S3).
  - Used for storing data files in the cloud.
  - Generally secured using:
    - Secure configuration including bucket policies and IAM
    - MFA
    - ACL permissions for allowed actions on S3 objects

---

<!-- .element class="image-and-title" -->
# AWS Command Line Interface

- Access Amazon S3 bucket and interact with it using a command line interface <!-- .element: class="fragment" data-fragment-index="1" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_08.png) <!-- .element: class="fragment" data-fragment-index="2" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_09.png) <!-- .element: class="fragment" data-fragment-index="3" -->
Source: AWS

---

<!-- .element class="split-screen-with-title" -->
# Amazon S3

<div>

<div>

- Accessible via web interface much like rest of AWS <!-- .element: class="fragment" data-fragment-index="1" -->
- Also has a REST API <!-- .element: class="fragment" data-fragment-index="2" -->
  - Requests to Amazon S3 can be authenticated or anonymous. <!-- .element: class="fragment" data-fragment-index="3" -->
    - Authenticated access requires credentials that AWS can use to authenticate your requests. <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_07.png)
Source: Medium

</div>

---

<!-- .element class="image-and-title" -->
# Amazon S3 REST API

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->Amazon S3's REST API supports **GET** requests to download objects from a bucket

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_10.png) <!-- .element: class="fragment" data-fragment-index="2" style="width: 50%"-->

Source: AWS

NOTE:

- Amazon S3 REST API is a part of the Amazon Simple Storage Service. Therefore, S3 supports the REST API.
- The AWS CLI (AWS Command Line Interface) can be used to interact with the S3 REST API.

<https://docs.aws.amazon.com/AmazonS3/latest/API/API_GetObject.html>

---

<!-- .element class="image-and-title" -->
# Reverse Proxy

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->A **reverse proxy** is “a server that sits in front of web servers and forwards client (e.g. web browser) requests to those web servers. <!-- .element: class="fragment" data-fragment-index="1" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Purpose**: Increase security, performance, and reliability.

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_11.png) <!-- .element: class="fragment" data-fragment-index="3" -->
Source: Cloudflare

NOTE:

- What is a reverse proxy?
  - A reverse proxy takes traffic from the internet from clients and routes to server
  - Opposite of a forward proxy (normal proxy)
Explanation: <https://www.cloudflare.com/learning/cdn/glossary/reverse-proxy/>

---

<!-- .element class="split-screen-with-title" -->
# JSON Format

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**JavaScript Object Notation (JSON)**
  - An open standard file format <!-- .element: class="fragment" data-fragment-index="2" -->
  - Files saved as `.json` <!-- .element: class="fragment" data-fragment-index="3" -->
  - Replaced XML <!-- .element: class="fragment" data-fragment-index="4" -->
  - Human-readable text to store attribute-value pairs and array data types (e.g. tables of data) <!-- .element: class="fragment" data-fragment-index="5" -->
  - Originally derived from JavaScript <!-- .element: class="fragment" data-fragment-index="6" -->
  - Used by many modern languages to generate and parse data <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_12.png)

</div>

</div>

NOTE:

- JSON, or JavaScript Object Notation
  - A lightweight format for storing and transporting data
  - Often used when data is sent from a server to a web page but increasingly adopted for situations where data arrays are needed.
  - Example JSON:

```json
{"employees":[
  {"firstName":"John", "lastName":"Doe"},
  {"firstName":"Anna", "lastName":"Smith"},
  {"firstName":"Peter", "lastName":"Jones"}
]}
```

- Note that in JSON format, data is stored in key-value pairs.
- JSON is composed of lists of dictionaries, making it easily readable by not only APIs but the Python programming language as well. Opportunities for automation abound.
- Objects are stored in curly braces.
- Arrays are written in square brackets.
- Example use case: AWS stores its configurations in JSON format. The IAM policy below serves as a block list for several IP addresses.

---

<!-- .element class="split-screen-with-title" -->
# Mordor Project

<div>

<div>

- The Mordor project provides pre-recorded security events generated by simulated adversarial techniques in the form of JSON files <!-- .element: class="fragment" data-fragment-index="1" -->
- The pre-recorded data is categorized by: <!-- .element: class="fragment" data-fragment-index="2" -->
  - Platforms <!-- .element: class="fragment" data-fragment-index="3" -->
  - Adversary groups <!-- .element: class="fragment" data-fragment-index="4" -->
  - TTPs <!-- .element: class="fragment" data-fragment-index="5" -->
- The pre-recorded data includes: <!-- .element: class="fragment" data-fragment-index="6" -->
  - Specific known malicious events <!-- .element: class="fragment" data-fragment-index="7" -->
  - Contextual events <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_13.png)

</div>

</div>

NOTE:
<https://mordordatasets.com/introduction.html>

---

<!-- .element class="split-screen-with-title" -->
# Amazon Logs as JSON

<div>

<div>

- Today's lab data is stored in JSON format<!-- .element: class="fragment" data-fragment-index="1" -->
- These logs are Amazon CloudWatch logs depicting API calls to S3 <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Notice the eventType: `AwsApiCall` signifies the method in which this transaction took place

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_14.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-13/slides/assets/13_07.png)

</div>

</div>

NOTE:
Deciphering Amazon's logs: <https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference-record-contents.html>

---

<!-- .element class="main-title" -->
# Demo

NOTE:

DO:

- Do a basic index search in Splunk and start inspecting the logs
- Show how keywords can be searched against in the REST API reference
- Share the link to CloudTrail Event Log Reference and show how a student can lookup each event log field to determine what is happening.
- Discuss how we're connecting what is seen in the logs to the requested TTPs.
