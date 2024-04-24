<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 20

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 20 - Midterm Project Kickoff

- Review <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
  - Cloud Detective Controls
- Midterm Project Kickoff <!-- .element: class="fragment highlight-current-red" data-fragment-index="2" -->

---

<!-- .element class="split-screen-with-title" -->
## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- **Module 1** - Governance, Risk and Compliance (GRC)

- **Module 2** - Data Security

- **Module 3** - Security Operations

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Module 4** - Cloud Security

- **Module 5** - Midterm Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-20/slides/assets/00_01.png)
<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)

</div>

</div>

---

<!-- .element class="title-with-text" -->
# Module 4 Labs

### Cloud Security

<div align="left" style="font-size: 45px">

- **Class 16** - Cloud IAM

<br>

- **Class 17** - Cloud Network Security

<br>

- **Class 18** - Cloud Logging and Monitoring

<br>

- **Class 19** - Cloud Detective Controls

<br>

- &shy;<!-- .element style="color: red;" -->**Class 20** - Midterm Project Kickoff

</div>

---

<!-- .element class="split-screen-with-title" -->
# Module 4 Challenges

<div>

<div align="left" style="font-size: 38px">

- **Class 16** - Brute Force Attack Tool Pt. 1 of 3

<br>

- **Class 17** - Brute Force Attack Tool Pt. 2 of 3

<br>

- **Class 18** - Brute Force Attack Tool Pt. 3 of 3

<br>

- **Class 19** - Mock Interviews

<br>

- &shy;<!-- .element style="color: red;" -->**Class 20** - N/A

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-20/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Review:

# Cloud Detective Controls

---

<!-- .element class="split-screen-with-title" -->
# Event-Driven Architecture

<div>

<div>

- Event-Driven Architecture consist of decoupled systems that run in response to events.
  - Events trigger and communicate between separate services <!-- .element: class="fragment" data-fragment-index="1" -->
  - Modern applications <!-- .element: class="fragment" data-fragment-index="2" -->
    - Microservices <!-- .element: class="fragment" data-fragment-index="3" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Three key components:**
    - Event producers <!-- .element: class="fragment" data-fragment-index="5" -->
    - Event routers <!-- .element: class="fragment" data-fragment-index="6" -->
    - Event consumers <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-20/slides/assets/19_01.png)

NOTE:

- What is event-driven architecture?
  - Event-Driven Architecture consist of decoupled systems that run in response to events.
  - Events trigger and communicate between separate services
  - Modern applications
  - Microservices
  - Three key components:
    - Event producers
    - Event routers
    - Event consumers

- An event-driven architecture uses events to trigger and communicate between decoupled services and is common in modern applications built with microservices.
- An event is a change in state, or an update, like an item being placed in a shopping cart on an e-commerce website.
- Events can either carry the state (the item purchased, its price, and a delivery address) or events can be identifiers (a notification that an order was shipped).
- Event-driven architectures have three key components: event producers, event routers, and event consumers.
- A producer publishes an event to the router, which filters and pushes the events to consumers.
- Producer services and consumer services are decoupled, which allows them to be scaled, updated, and deployed independently.

---

<!-- .element class="split-screen-with-title" -->
# Serverless Code

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**“Canary in the coal mine”** as a detection technique
  - Execute a Lambda function at a regular scheduled interval to check the state of a resource <!-- .element: class="fragment" data-fragment-index="2" -->
  - Anomalies detected lead to CloudWatch alarms triggered <!-- .element: class="fragment" data-fragment-index="3" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-20/slides/assets/19_05.png)

---

<!-- .element class="image-and-title" -->
# Threat Detection

![Image](/ops-401-cybersecurity-guide/curriculum/class-20/slides/assets/19_08.png)

Source: YouTube - Online Tech Talks

---

<!-- .element class="main-title" -->
# Review: Term 1

NOTE:

- What is information assurance?
- What is a security audit?
- If a business has no security standard, what is a good one to start with?
  - NIST Cybersecurity Framework
- What compliance deals with credit card information?
  - PCI-DSS
- You need to quickly audit a client company against a specific NIST standard. What do you do?
  - CSET
- What kind of system can we use to monitor systems uptime in an environment?
  - ISCM, e.g. Nagios
- What is privilege creep?
- What is SSO?
- What is (and is not) MFA?
  - Have, Are, Know
- How can we protect data at rest?
  - FDE, Single file encryption
- How can we protect data in motion?
  - SSL, TLS, PGP, DLP
- Explain public key encryption.
  - Example OpenSSL
- What is PKI? Give an example.
  - HTTPS
- What are some documents associated with a data security policy?
  - AUP
  - BYOD policy
- What network port handles encrypted web traffic? Unencrypted web traffic?
- What does Wireshark do?
  - Packets can be sniffed, for better or worse
- What is promiscuous mode?
- What is PCAP/WinPCAP?
- What is traffic mirroring?
- What is an IPS and an IDS?
- How is encryption used offensively?
  - Evading detection
  - Ransomware (denial of service)
- What is risk? How can we calculate and define risk?
  - Quantitative: ALE = SLE x ARO
  - Qualitative: DREAD
- Why do we care about threats?
- What is threat modeling?
  - Cyber Kill Chain, DFD, STRIDE
- Why do we care about automation in security?
- What languages are security tools written in?

---

<!-- .element class="main-title" -->
# Midterm Project Kickoff

---

<!-- .element class="main-title" -->
# Demo
