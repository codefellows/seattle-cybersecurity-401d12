<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 33

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

Daily TODOs

- Hide/unhide slides to show as necessary
- Toggle presentation mode on and screen share this first slide when you initialize recording on Zoom to indicate class number

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 33 - Threat Hunting with Zeek, RITA

- Course Overview <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Review
  - Malware Traffic Analysis
- Ops Challenge
- Lecture:
  - Threat Hunting with Zeek, RITA
- Demo

---

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/0_01.png)
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

- &shy;<!-- .element style="color: red;" -->**Class 33** - Threat Hunting with Zeek, RITA

<br>

- **Class 34** - Forensics with Autopsy

<br>

- **Class 35** - N/A

</div>

---

<!-- .element class="split-screen-with-title" -->
## Module 7 Challenges

<div>

<div align="left" style="font-size: 35px">

- **Class 31** - Malware Detection Part 1 of 3

<br>

- **Class 32** - Malware Detection Part 2 of 3

<br>

- &shy;<!-- .element style="color: red;" -->**Class 33** - Malware Detection Part 3 of 3

<br>

- **Class 34** - Mock Interviews

<br>

- **Class 35** - Web Vulnerability Scanning with Nmap

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/0_03.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 33 - Threat Hunting with Zeek + RITA

- Course Overview
- Warmup <!-- .element style="color: red;" -->
- Review
  - Malware Traffic Analysis
- Ops Challenge
- Lecture:
  - Threat Hunting with Zeek + RITA
- Demo

---

<!-- .element class="main-title" -->

# Warmup

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 33 - Threat Hunting with Zeek + RITA

- Course Overview
- Warmup
- Review <!-- .element style="color: red;" -->
  - Malware Traffic Analysis
- Ops Challenge
- Lecture:
  - Threat Hunting with Zeek + RITA
- Demo

---

<!-- .element class="main-title" -->

# Review

- Previous Concepts <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Lab 32

---

<!-- .element class="main-title" -->
# Review:

## Malware Traffic Analysis

NOTE:

---

<!-- .element class="split-screen-with-title" -->

<div>

<div align="left">

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Malware incidents** leave a trail of bread crumbs: **logs and packets**
- What have you been practicing doing?<!-- .element: class="fragment" data-fragment-index="2" -->
  - **Log generation and ingestion**
  - **Packet capture**
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->We can use **Behavior Patterns** to spot suspicious activities
- We can pinpoint "invisible" threats<!-- .element: class="fragment" data-fragment-index="4" -->
- Ultimately, minimize damage and profit loss<!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div align="left">

> **Malware Traffic Analysis** involves monitoring and analyzing network communications to detect signs of malware-related activities

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/32_01.png)
<!-- .element style="width: 75%"-->

</div>

</div>

NOTE:

Image Source: include link to image source

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

<div align="left">

> An **Indicator of Compromise (IOC)** is a piece of digital forensics that suggests that an endpoint or network may have been breached

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/32_01.png)
<!-- .element style="width: 75%"-->

Source: [Crowdstrike.com](https://www.crowdstrike.com/cybersecurity-101/indicators-of-compromise/)

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

<!-- .element class="main-title" -->

# Review:

## Lab 32

NOTE:

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 33 - Threat Hunting with Zeek + RITA

- Course Overview
- Warmup
- Review
- Ops Challenge <!-- .element style="color: red;" -->
- Lecture:
  - Threat Hunting with Zeek + RITA
- Demo

---

<!-- .element class="main-title" -->
# Ops Challenge:

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Review Ops Challenge 32**
- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="2" -->**Ops Challenge 33** - Signature-based Malware Detection (part 3)

</div>

NOTE:

---

# Review: Ops Challenge 32

# Introduce: Ops Challenge 33

- Review Ops Challenge 32
- Ops Challenge 33 - Signature-based Malware Detection (part 3)

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 33 - Threat Hunting with Zeek + RITA

- Course Overview
- Warmup
- Review
- Ops Challenge
- Lecture: <!-- .element style="color: red;" -->
  - Threat Hunting with Zeek + RITA
- Demo

---

<!-- .element class="title-and-subtitle" -->

# Lecture:

## Class 33 - Threat Hunting with Zeek + RITA

---

<!-- .element class="split-screen-with-title" -->

# Hunting C2 Traffic

<div>

<div align="left">

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Overt Communication Channels** are approved means of communication on a corporate network
  - Done or shown openly or plainly apparent<!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Covert Communication Channels** are unapproved means of communication on a corporate network
  - Using an encrypted chat program to circumvent security controls<!-- .element: class="fragment" data-fragment-index="4" -->
  - Using a text file on the file server to chat without being monitored<!-- .element: class="fragment" data-fragment-index="5" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**C2 beacons**

</div>

<div>

> **Command and Control** traffic is communication between **compromised devices** and remote systems controlled by an attacker.

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/33_07.png)
<!-- .element style="width: 100%"-->

</div>

</div>

NOTE:

The C2 server hosts instructions for the malware, which are then executed on the infected machine after the malware checks in.

---

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

NOTE:

The C2 server hosts instructions for the malware, which are then executed on the infected machine after the malware checks in.

- **Threat Hunting:**
  - Command and Control (C2) Traffic
  - Zeek
  - RITA

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

---

<!-- .element class="split-screen" -->

<div>

<div align="center">

# Long Connections<!-- .element: class="fragment" data-fragment-index="1" -->

</div>

- Long connections may only open and close infrequently (compared to frequent beacons)<!-- .element: class="fragment" data-fragment-index="2" -->
- You may need to track these differently than you're used to<!-- .element: class="fragment" data-fragment-index="4" -->

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/33_02.png)
<!-- .element style="width: 100%"--><!-- .element: class="fragment" data-fragment-index="3" -->
&shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Top**: One long connection

&shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Bottom**: Six shorter connections

</div>

</div>

---

<div>

<div align="center">

# DNS<!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

- DNS based C2 is different than normal C2 direct communications as this instead utilizes the DNS infrastructure<!-- .element: class="fragment" data-fragment-index="6" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/33_03.png)
<!-- .element style="width: 100%"--><!-- .element: class="fragment" data-fragment-index="7" -->

Here is a normal non-cached DNS request to Google.com<!-- .element: class="fragment" data-fragment-index="7" -->

</div>

</div>

NOTE:

The C2 server hosts instructions for the malware, which are then executed on the infected machine after the malware checks in.

- The Client (your computer) only talks with its configured Recursive Name Server (NS). This name server is usually given to your computer when it connects to a network through DHCP. Though you can also set your DNS servers manually. For instance, you may choose to use one of the servers provided by large companies such as Cloudflare (1.1.1.1) or Google (8.8.8.8).
- Behind the scenes, your Recursive NS is doing a lot of work for you. All these requests would quickly overwhelm servers if they were done every time so the above sequence of events only happens if your Recursive NS doesn't already know an answer. Once it has performed this work once it will cache the answer for a period of time. So the next time you or any other client makes the same DNS query the NS will answer from its local cache instead of querying other name servers.

- What is RITA?
  - RITA stands for Real Intelligence Threat Analytics.
  - RITA is an open source framework for network traffic analysis.
  - The framework ingests Bro/Zeek Logs in TSV format, and currently supports the following major features:
    - Beaconing Detection: Search for signs of beaconing behavior in and out of your network
    - DNS Tunneling Detection Search for signs of DNS based covert channels
    - Block list Checking: Query block lists to search for suspicious domains and hosts

---

<!-- .element class="image-and-title" -->
# RITA

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->We perform **threat hunting** by analyzing at a deeper level our environment using tools like Zeek, RITA, and Wireshark
- Zeek can:<!-- .element: class="fragment" data-fragment-index="2" -->
  - Perform live capture/sniffing like an IDS<!-- .element: class="fragment" data-fragment-index="3" -->
  - Convert PCAPs to Zeek logs for analysis by RITA<!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->Originally developed in the 90s as *Bro*

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/13_0.png)

</div>

</div>

NOTE:
Score - The score is a metric calculated by taking into account the interval skew, dispersion, and duration as well as the data size skew, dispersion, and mode. The closer this score is to 1 the more likely that this is beaconing activity.
Source - IP address that initiated the connections.
Destination - IP address that received the connections.
Connections - The total number of connections between the source and destination IPs.
Avg Bytes - The average number of bytes transferred in either direction per connection.
Intvl Range - This is the difference between the maximum and minimum time intervals seen. For instance, if there were 2 connections 80 seconds apart and another 2 connections 20 seconds apart then the entire range of intervals would be 80-20 = 60 seconds. This is useful to know how spread out or close together the connections are, but it is easily thrown off by missed connections.
Size Range - This is the difference between the maximum and minimum connection sizes seen.
Top Intvl (CSV) / Intvl Mode (HTML) - The interval between connections that we saw the most.
Top Size (CSV) / Size Mode (HTML) - The number of bytes transferred in a connection that we saw the most.
Top Intvl Count (CSV) / Intvl Mode Count (HTML) - How many times we saw the interval mode.
Top Size Count (CSV) / Size Mode Count (HTML) - How many times we saw the size mode.
Intvl Skew - Skew measures how distorted or asymmetric the data is. A value closer to 0 means that the data is very symmetric. This measure is useful in the case of malware that does not try to hide itself, but more importantly will detect malware that tries to hide by adding jitter. This works because malware with jitter most likely uses a random number generator to add or subtract to a mean value (e.g. 30 seconds +/- 5 seconds). The random number generator will uniformly distribute the values which causes the data to be symmetric, and as such this particular measure is hard to beat.
Size Skew - Skew of the connection data sizes. Skew isn't as important of a measure for data sizes because we expect them to naturally vary if an attacker is actively sending commands or transferring data via a C2 session. But the majority of the time we expect the C2 session to be simply checking in.
Intvl Dispersion / Size Dispersion - Dispersion describes how likely it is that an interval or data size is to stray from the mean (very similar to standard deviation from the mean). A value closer to 0 means that most intervals or data sizes were clustered around the mean and had very little variation. This is useful in the case of beacons that don't make any effort to hide themselves by changing their beacon interval or data sizes. The more jitter added to a beacon, the less effective dispersion is.

---

<!-- .element class="split-screen-with-title" -->

# RITA

<div>

<div>

- show-databases: Print the datasets currently stored
- show-beacons: Print hosts which show signs of C2 software
- show-bl-hostnames: Print blacklisted hostnames which received connections
- show-bl-source-ips: Print blacklisted IPs which initiated connections

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/14_0.png)

</div>

</div>

NOTE:

RITA calculates various statistical measures for both the time interval between connections and the size of each connection.

---

<!-- .element class="split-screen-with-title" -->
# RITA

<div>

<div>

- show-bl-dest-ips: Print blacklisted IPs which received connections
- show-exploded-dns: Print dns analysis. Exposes covert dns channels
- show-long-connections: Print long connections and relevant information
- show-strobes: Print connections which occurred with excessive frequency
- show-useragents: Print user agent information

<br>

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/33_06.png)
<!-- .element style="width: 100%"-->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-33/slides/assets/15_0.png)

</div>

</div>

NOTE:

### Commands:

- **`show-databases`**: Print the datasets currently stored
- **`show-beacons`**: Print hosts which show signs of C2 software
- **`show-bl-hostnames`**: Print blacklisted hostnames which received connections
- **`show-bl-source-ips`**: Print blacklisted IPs which initiated connections
- **`show-bl-dest-ips`**: Print blacklisted IPs which received connections
- **`show-exploded-dns`**: Print dns analysis. Exposes covert dns channels
- **`show-long-connections`**: Print long connections and relevant information
- **`show-strobes`**: Print connections which occurred with excessive frequency
- **`show-useragents`**: Print user agent information

### Data:

- **Score** - The score is a metric calculated by taking into account the interval skew, dispersion, and duration as well as the data size skew, dispersion, and mode. The closer this score is to 1 the more likely that this is beaconing activity.
- **Source** - IP address that initiated the connections.
- **Destination** - IP address that received the connections.
- **Connections** - The total number of connections between the source and destination IPs.
- **Avg Bytes** - The average number of bytes transferred in either direction per connection.
- **Intvl Range** - This is the difference between the maximum and minimum time intervals seen. For instance, if there were 2 connections 80 seconds apart and another 2 connections 20 seconds apart then the entire range of intervals would be 80-20 = 60 seconds. This is useful to know how spread out or close together the connections are, but it is easily thrown off by missed connections.
- **Size Range** - This is the difference between the maximum and minimum connection sizes seen.
- **Top Intvl (CSV) / Intvl Mode (HTML)** - The interval between connections that we saw the most.
- **Top Size (CSV) / Size Mode (HTML)** - The number of bytes transferred in a connection that we saw the most.
- **Top Intvl Count (CSV) / Intvl Mode Count (HTML)** - How many times we saw the interval mode.
- **Top Size Count (CSV) / Size Mode Count (HTML)** - How many times we saw the size mode.
- **Intvl Skew** - Skew measures how distorted or asymmetric the data is. A value closer to 0 means that the data is very symmetric. This measure is useful in the case of malware that does not try to hide itself, but more importantly will detect malware that tries to hide by adding jitter. This works because malware with jitter most likely uses a random number generator to add or subtract to a mean value (e.g. 30 seconds +/- 5 seconds). The random number generator will uniformly distribute the values which causes the data to be symmetric, and as such this particular measure is hard to beat.
- **Size Skew** - Skew of the connection data sizes. Skew isn't as important of a measure for data sizes because we expect them to naturally vary if an attacker is actively sending commands or transferring data via a C2 session. But the majority of the time we expect the C2 session to be simply checking in.
- **Intvl Dispersion / Size Dispersion** - Dispersion describes how likely it is that an interval or data size is to stray from the mean (very similar to standard deviation from the mean). A value closer to 0 means that most intervals or data sizes were clustered around the mean and had very little variation. This is useful in the case of beacons that don't make any effort to hide themselves by changing their beacon interval or data sizes. The more jitter added to a beacon, the less effective dispersion is.

---

<!-- .element class="title-and-subtitle" -->

# Agenda

## Class 33 - Threat Hunting with Zeek + RITA

- Course Overview
- Warmup
- Review
- Ops Challenge
- Lecture:
  - Threat Hunting with Zeek + RITA
- Demo <!-- .element style="color: red;" -->

---

<!-- .element class="main-title" -->
# Demo & Lab

### Find malicious attack with Wireshark & Incident Reporting

NOTE:

### Import OVA File

### Demo: Find malicious attack with Wireshark & Incident Reporting

NOTE:

Demo 1 Threat Hunting with Zeek and RITA

DO:

- Prep
  - Check that your lab VM is installed with a working copy of RITA, which includes Zeek.
  - Check that you've downloaded the required PCAPs for today from ActiveCM.
  - Demo
    - Sanity check your tooling is ready to go
      - `rita -version`
      - `zeek -version`
      - `wireshark -version`
      - `libreoffice --calc -version`
    - If any of the above commands don't show a software version output to your terminal, you'll need to check that the software is properly installed
    - Explain that while Zeek is a NIDS like Snort, we're going to instead use it today as a PCAP processor in order to turn our PCAPs into Zeek logs
    - We won't be using Zeek to perform packet capture or sniffing
    - Ingest one of the PCAPs (this will take a moment)
      - `zeek -r ~/Desktop/sample-200.pcap local`
    - Have rita import the logs
    - From your desktop, run rita import logs example
