<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 14

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 14 - Intrusion Detection and Prevention Systems

- Course Overview<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - Reconstructing a Cloud Attack using Log Data
- Lecture
  - Intrusion Detection and Prevention Systems
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

- **Class 13** - Reconstructing a Cloud Attack

<br>

- &shy;<!-- .element style="color: red;" -->**Class 14** - Intrusion Detection

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

- **Class 13** - Network Security Tool Pt. 3 of 3

<br>

- &shy;<!-- .element style="color: red;" -->**Class 14** - Mock Interviews

<br>

- **Class 15** - Brute Force Attacks

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Review:

## Ops Challenge

---

<!-- .element class="split-screen-with-title" -->
# Three-way Handshake

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**TCP three-way handshake**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->Client first sends a **Synchronization packet (SYN)**
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Server accepts and responds with a **Synchronization Acknowledgment (SYN-ACK)**
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->The client responds with an **Acknowledgment (ACK)**
  - TCP session is established <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_01.png)
Source: Coen's Blog

</div>

NOTE:

- What are FIN and RST packets?
  - While coding in how to terminate a connection during the three way hand shake, students will face a decision of using 'F' for FIN or 'R' for RST.
  - Referring to TCP FIN VS RST Packets- Know the Difference, discuss:
    - TCP FIN and RST are two ways to terminate a TCP connection.
    - RST packets are like forcefully hanging up a telephone call.
    - FIN packets are like saying your goodbyes and letting the conversation gradually unwind.

---

<!-- .element class="split-screen-with-title" -->
# Three-way Handshake

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What are FIN and RST packets?**
  - TCP FIN and RST are two ways to terminate a TCP connection <!-- .element: class="fragment" data-fragment-index="2" -->
- Difference between TCP FIN VS RST Packets: <!-- .element: class="fragment" data-fragment-index="3" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**RST packets** are like forcefully hanging up a telephone call
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**FIN packets** are like saying your goodbyes and letting the conversation elegantly close

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_01.png)
Source: Coen's Blog

</div>

</div>

NOTE:

- What are FIN and RST packets?
  - While coding in how to terminate a connection during the three way hand shake, students will face a decision of using 'F' for FIN or 'R' for RST.
  - Referring to TCP FIN VS RST Packets- Know the Difference, discuss:
    - TCP FIN and RST are two ways to terminate a TCP connection.
    - RST packets are like forcefully hanging up a telephone call.
    - FIN packets are like saying your goodbyes and letting the conversation gradually unwind.

---

<!-- .element class="main-title" -->
# Review:

# Reconstructing a Cloud Attack

NOTE:

- Review the attacker's console at Mordor
- Discuss what was the attacker doing
- What is ring.txt?

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/13_02.png)

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/13_06.png)
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

<!-- .element class="split-screen-with-title" -->
# Amazon S3 REST API

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->Amazon S3's REST API supports **GET** requests to download objects from a bucket

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/13_10.png) <!-- .element: class="fragment" data-fragment-index="2" -->
Source: AWS

NOTE:

- Amazon S3 REST API is a part of the Amazon Simple Storage Service. Therefore, S3 supports the REST API.
- The AWS CLI (AWS Command Line Interface) can be used to interact with the S3 REST API.

https://docs.aws.amazon.com/AmazonS3/latest/API/API_GetObject.html

---

<!-- .element class="split-screen-with-title" -->
# JSON Format

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**JavaScript Object Notation (JSON)**
  - An open standard file format <!-- .element: class="fragment" data-fragment-index="2" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Files saved as `.json`
  - Replaced XML <!-- .element: class="fragment" data-fragment-index="4" -->
  - Human-readable text to store attribute-value pairs and array data types (e.g. tables of data) <!-- .element: class="fragment" data-fragment-index="5" -->
  - Originally derived from JavaScript <!-- .element: class="fragment" data-fragment-index="6" -->
  - Used by many modern languages to generate and parse data <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/13_12.png)

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

<!-- .element class="main-title" -->
# Intrusion Detection

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What's the purpose of an IDS?**
  - Detect and prevent intrusions in real time on a network <!-- .element: class="fragment" data-fragment-index="2" -->
  - Allows defenders to customize defensive detection rules <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**When should an IDS be deployed?**
  - Private networks with high value assets <!-- .element: class="fragment" data-fragment-index="5" -->
  - Adequate SecOps coverage to configure rules and respond to IDS alerts <!-- .element: class="fragment" data-fragment-index="6" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_02.png)

NOTE:

- Why use IDS, IPS, or HIDS?
  - Detect and/or prevent intrusions in real time on a network
  - Allows defenders to customize defensive detection rules

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is an Intrusion Detection System (IDS)?**
  - A deployable security system that uses rules to detect suspicious activity on a network. <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**What is an Intrusion Prevention System (IPS)?**
  - Similar to an IDS, except it attempts to prevent the network traffic in addition to detecting it using rules. <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**IDS products**
  - Snort (used today) <!-- .element: class="fragment" data-fragment-index="6" -->
  - Suricata <!-- .element: class="fragment" data-fragment-index="7" -->
  - Trend Micro Deep Security <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_03.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_04.png)

</div>

</div>

NOTE:

- What is IDS/IPS?
  - Be sure to clarify that an IDS watches and establishes baseline network behavior before observing and reporting suspicious network activities.
  - The IPS instead acts like a firewall and attempts to block the activity altogether after the intrusion crosses the firewall.
- Network intrusion detection system (NIDS)
  - A NIDS is a detective security control that finds intruder activity on the network and raises alerts when suspicious traffic is captured using rule sets.
  - Also commonly referred to broadly as IDS.
  - Often included on the perimeter firewall UTM device
- Network intrusion prevention system (NIPS)
  - A NIPS is same as IDS but also detects and actively prevents intrusion.
  - Also commonly referred to broadly as IPS.
- Types
  - Behavioral
  - Signature-based

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is Snort?**
  - An open source NIPS, capable of performing real-time traffic analysis and packet logging on IP networks. <!-- .element: class="fragment" data-fragment-index="2" -->
    - Protocol analysis <!-- .element: class="fragment" data-fragment-index="3" -->
    - Content searching/matching <!-- .element: class="fragment" data-fragment-index="4" -->
    - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Detects**
      - Probes <!-- .element: class="fragment" data-fragment-index="6" -->
      - Buffer overflows <!-- .element: class="fragment" data-fragment-index="7" -->
      - Stealth port scans (performed with NMAP and other discovery tools) <!-- .element: class="fragment" data-fragment-index="8" -->
      - CGI attacks <!-- .element: class="fragment" data-fragment-index="9" -->
      - SMB probes <!-- .element: class="fragment" data-fragment-index="10" -->
      - OS fingerprinting attempts <!-- .element: class="fragment" data-fragment-index="11" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_03.png)

</div>

</div>

NOTE:

- What is Snort?
  - Snort is an open source NIPS, capable of performing real-time traffic analysis and packet logging on IP networks.
  - It can perform protocol analysis, content searching/matching, and can be used to detect a variety of attacks and probes, such as buffer overflows, stealth port scans, CGI attacks, SMB probes, OS fingerprinting attempts, and much more.

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Where can an IDS be deployed?**
  - Standalone appliance/VM <!-- .element: class="fragment" data-fragment-index="2" -->
  - Integrated into cloud IaaS provider's systems <!-- .element: class="fragment" data-fragment-index="3" -->
  - Installed on a router/firewall appliance such as pfSense <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Types**
  - Behavioral detection <!-- .element: class="fragment" data-fragment-index="6" -->
  - Signature-based detection <!-- .element: class="fragment" data-fragment-index="7" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_02.png)

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Packet logging**
  - Snort can be run as a packet logger <!-- .element: class="fragment" data-fragment-index="2" -->
  - Novel attacks do not exhibit known signatures in traffic <!-- .element: class="fragment" data-fragment-index="3" -->
  - Novel attacks require traffic inspection before a new IDS rule is generated <!-- .element: class="fragment" data-fragment-index="4" -->
  - This is exactly how the default publicly-available Snort rules are created <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_03.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is a host-based intrusion detection system (HIDS)?**
  - An IDS capable of monitoring and analyzing the internals of a computing system as well as the network packets on its network interfaces.
  - Ideally deployed in conjunction with a NIDS to capture traffic that slipped past the NIDS <!-- .element: class="fragment" data-fragment-index="2" -->
  - Example Product: OSSEC <!-- .element: class="fragment" data-fragment-index="3" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_05.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_06.png)

</div>

</div>

NOTE:

- What is HIDS?
  - A host-based intrusion detection system (HIDS) is an IDS capable of monitoring and analyzing the internals of a computing system as well as the network packets on its network interfaces.
  - Ideally deployed in conjunction with a NIDS to capture traffic that slipped past the NIDS
  - Example: OSSEC
    - Open source HIDS
    - Log-based IDS
    - Rootkit and malware detection
    - Active response
    - Compliance auditing
    - File integrity monitoring
    - System inventory
  - https://www.ossec.net/

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**OSSEC**
  - Open source HIDS <!-- .element: class="fragment" data-fragment-index="2" -->
  - Log-based IDS <!-- .element: class="fragment" data-fragment-index="3" -->
  - Rootkit and malware detection <!-- .element: class="fragment" data-fragment-index="4" -->
  - Active response <!-- .element: class="fragment" data-fragment-index="5" -->
  - Compliance auditing <!-- .element: class="fragment" data-fragment-index="6" -->
  - File integrity monitoring <!-- .element: class="fragment" data-fragment-index="7" -->
  - System inventory <!-- .element: class="fragment" data-fragment-index="8" -->
- Splunk can be integrated with OSSEC using Splunkbase <!-- .element: class="fragment" data-fragment-index="9" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_05.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_06.png)

</div>

</div>

NOTE:
https://www.ossec.net/

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**How does Snort work?**
  - Detects network baseline traffic <!-- .element: class="fragment" data-fragment-index="2" -->
  - Uses rules to detect network anomalies <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Network topology**
  - Snort requires a span port (traffic mirroring) for its sniffer interface <!-- .element: class="fragment" data-fragment-index="5" -->
  - PfSense supports traffic mirroring, as implemented in Ops 301 <!-- .element: class="fragment" data-fragment-index="6" -->
  - Keep this lab long term as a threat detection ecosystem for learning <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_07.png)

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Snort Deployment**
  - Typical on premise setup with traffic mirroring. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Needs to be BEFORE any encapsulation/encryption (VPN) <!-- .element: class="fragment" data-fragment-index="3" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_08.png)

Source: cisco.com

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Setting up Snort**
  - First test if Snort is installed with `snort -V` <!-- .element: class="fragment" data-fragment-index="2" -->
  - Once Snort is installed, configure it by editing the snort.conf file in /etc/snort/snort.conf <!-- .element: class="fragment" data-fragment-index="3" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_09.png)

Source: InfosecInstitute

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->Basic settings are in `snort.conf`
  - Set your network address first <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Rules are found in `/etc/snort/rules/local.rules`

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_10.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_11.png)

Source: Infosec

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Snort rule headers explained (example scenario):**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**`alert`** – Rule action. Snort will generate an alert when the set condition is met.
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**`any`** – Source IP. Snort will look at all sources.
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**`any`** – Source port. Snort will look at all ports.
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**`->`** – Direction. From source to destination.
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**`$HOME_NET`** – Destination IP. We are using the HOME_NET value from the snort.conf file.
  - &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**`any`** – Destination port. Snort will look at all ports on the protected network.

![Image](/ops-401-cybersecurity-guide/curriculum/class-14/slides/assets/14_11.png)

Source: Infosec

---

<!-- .element class="main-title" -->
# Demo

NOTE:

DO:

- In this demo we'll introduce students to Snort.
  - Installation
    - Show how to deploy Snort on a Ubuntu Linux VM.
    - Show where the config and log files are located.
    - How to test & validate Snort configuration:
      - `sudo snort -i enp0s3 -c /etc/snort/snort.conf -T`
  - Modes of Operation
    - Getting started with Snort’s sniffer mode
    - The sniffer mode reads the network’s traffic and displays the translation for a human viewer.
    - In order to test it type sudo snort -v
    - You won't use this commonly. Takes a lot of resources.
    - More verbose: sudo snort -v -d -e
  - Next, let's setup logging
  - `cd /var/log/snort`
  - `mkdir snortlogs`
  - `snort -d -l snortlogs` initiates Snort to log traffic to this folder
  - `snort -d -v -r logfilename.log.xxxxxxx` will let us read the log file
  - To initiate Snort NIDS mode and send alerts to the console view:
    - `sudo snort -d -l /var/log/snort/snortlogs -h 10.0.2.0/24 -A console -c /etc/snort/snort.conf`
    - Replace 10.0.0.0/24 with your actual network
  - Rule Writing
    - Show how to write a Snort rule.
    - Edit /etc/snort/rules/local.rules and add alert icmp any any -> $HOME_NET any (msg:”ICMP test”; sid:1000001; rev:1; classtype:icmp-event;)
    - This will create a rule detecting ICMP traffic on the network.
    - From this same computer you can ping scanme.nmap.org to test if Snort is triggering alerts correctly. You should see positive detections:
      - `10/19-21:39:47.901168  [**] [1:1000001:1] ”ICMP test"`
