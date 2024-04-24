<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 04

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 04 - Systems Hardening with CIS Standards

- Course Overview <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - Cyber Risk Analysis
- Lecture:
  - Systems Hardening with CIS Standards
- Demo

---

<!-- .element class="split-screen-with-title" -->
## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Module 1** - Governance, Risk and Compliance (GRC)

- **Module 2** - Data Security

- **Module 3** - Security Operations

- **Module 4** - Cloud Security

- **Module 5** - Midterm Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/00_01.png)
<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)

</div>

</div>

---

<!-- .element class="title-with-text" -->
## Module 1 Labs

### Strategic Policy Development

<div align="left" style="font-size: 45px">

- **Class 01** - Strategic Policy Development

<br>

- **Class 02** - Cloud Security Principles and Frameworks

<br>

- **Class 03** - Cyber Risk Analysis

<br>

- &shy;<!-- .element style="color: red;" -->**Class 04** - Systems Hardening with CIS Standards

<br>

- **Class 05** - Career Coaching Workshop

</div>

---

<!-- .element class="split-screen-with-title" -->

## Module 1 Challenges

<div>

<div align="left" style="font-size: 38px">

- **Class 01** - N/A

<br>

- **Class 02** - Uptime Sensor Tool (Part 1 of 2)

<br>

- **Class 03** - Uptime Sensor Tool (Part 2 of 2)

<br>

- &shy;<!-- .element style="color: red;" -->**Class 04** - Mock Interviews

<br>

- **Class 05** - File Encryption

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/00_02.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Review:

## Lab

NOTE:

DO: Review the previous day's Lab and Ops challenge

---

<!-- .element class="main-title" -->
# Review

## Ops Challenge

---

<!-- .element class="main-title" -->
# Review:

## Cyber Risk Analysis

---

<!-- .element class="split-screen-with-title" -->
# Cyber Risk Analysis

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Risk**
  - The likelihood and impact of a threat actor exploiting a vulnerability. <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Vulnerability**
  - A weakness that could be triggered accidentally or exploited intentionally to cause a security breach. <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Threat**
  - The potential for someone or something to exploit a vulnerability, whether intentional or unintentional. <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/03_01.png)
Source: osdefsec

</div>

</div>

NOTE:

- Why do we need to learn how to communicate risk?
  - Our core mission is to mitigate cyber risk.
- What are due care and due diligence?
  - Showing due care and due diligence is the only way to disprove negligence in an occurrence of loss.
  - Due care is using reasonable care to protect the interests of an organization.
    - Example: Developing a formalized security structure including policies and procedures.
  - Due diligence is practicing the activities that maintain the due care effort.
    - Example: continued application of this security structure onto the IT infrastructure
- What is risk?
  - CompTIA indicates there is a relationship between vulnerability, threat, and risk.
  - A vulnerability is a weakness that could be triggered accidentally or exploited intentionally to cause a security breach.
  - A threat is the potential for someone or something to exploit a vulnerability and breach security. A threat may be intentional or unintentional.
  - Risk is the likelihood and impact (or consequence) of a threat actor exploiting a vulnerability.

---

<!-- .element class="split-screen-with-title" -->
# Cyber Risk Analysis

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Risk management options**
  - Risk acceptance <!-- .element: class="fragment" data-fragment-index="2" -->
  - Risk avoidance <!-- .element: class="fragment" data-fragment-index="3" -->
  - Risk mitigation <!-- .element: class="fragment" data-fragment-index="4" -->
  - Risk transference <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/03_07.png)
Source: EdJet

</div>

</div>

NOTE:

- Risk Mitigation/Response
  - Risk avoidance
    - Determining that the impact and/or likelihood of a specific risk is too great to be offset by the potential benefits and not performing a certain business function because of that determination.
  - Risk mitigation
    - Putting security controls in place to attenuate the possible impact and/or likelihood of a specific risk.
  - Risk transference
    - Paying an external party to accept the financial impact of a given risk.
    - Example: Cyber insurance

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 04 - Systems Hardening with CIS Standards

- Course Overview
- Warmup
- Ops Challenge
- Review
  - Cyber Risk Analysis
- Lecture <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
  - Systems Hardening with CIS Standards
- Demo

---

<!-- .element class="title-and-subtitle" -->
# Systems Hardening

## The Art of Hardening Defenses

NOTE:

---

<!-- .element class="split-screen-with-title" -->
# Security Controls

<div>

<div>

- Secure configuration of your systems is one very important dimension of security risk management. <!-- .element: class="fragment" data-fragment-index="1" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Key benefits to secure configuration:**
  - Enhanced system functionality <!-- .element: class="fragment" data-fragment-index="3" -->
  - Significantly improved security <!-- .element: class="fragment" data-fragment-index="4" -->
  - Simplified compliance and auditability <!-- .element: class="fragment" data-fragment-index="5" -->
- Belongs in an overall defense in depth strategy <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/04_01.png)
Source: Emsisoft

</div>

</div>

NOTE:

- What is "systems hardening"?
  - Broadly speaking, systems hardening is a methodical approach to audit, identify, close, and control potential security vulnerabilities throughout your organization. This can be performed on:
    - Applications
    - Operating systems
    - Servers
    - Databases
    - Networks

---

<!-- .element class="split-screen-with-title" -->
# Security Controls

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is systems hardening?**
  - Systems hardening is a methodical approach to audit, identify, close, and control potential security vulnerabilities throughout your organization. <!-- .element: class="fragment" data-fragment-index="2" -->
  - This can be performed on: <!-- .element: class="fragment" data-fragment-index="3" -->
    - Applications <!-- .element: class="fragment" data-fragment-index="4" -->
    - Operating Systems <!-- .element: class="fragment" data-fragment-index="5" -->
    - Servers <!-- .element: class="fragment" data-fragment-index="6" -->
    - Databases <!-- .element: class="fragment" data-fragment-index="7" -->
    - Networks <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/04_02.png)
Source: CIS

</div>

</div>

NOTE:

- By default, computer systems "out of the box" tend to prioritize convenience over security, or lack the configuration necessary to make it an effective security defense in your environment until you take the time to configure it.
- We can use certain industry standards to demonstrate secure configuration.

---

<!-- .element class="split-screen-with-title" -->
# Center for Internet Security (CIS)

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->The **Center for Internet Security (CIS)** is a non-profit organization that creates secure configuration benchmarks for computer systems.
- CIS Controls are 20 categories of best practices to improve cyber defenses. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Focus security resources based on proven best practices, not on any one vendor's solution <!-- .element: class="fragment" data-fragment-index="3" -->
  - Organize an effective cybersecurity program according to Implementation Groups <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/04_02.png)
Source: CIS

</div>

</div>

NOTE:

- What is CIS?
  - The Center for Internet Security (CIS) is a non-profit org that creates secure configuration benchmarks for computer systems.
- What are CIS Controls?
  - CIS Controls are 20 categories of best practices to improve cyber defenses.
- Why use CIS Controls?
  - "Leverage the battle-tested expertise of the global IT community to defend against cyber attacks
  - Focus security resources based on proven best practices, not on any one vendor’s solution

---

<!-- .element class="split-screen-with-title" -->
# Security Controls

<div>

<div>

- Implementation groups separate the recommended CIS controls by organization size <!-- .element: class="fragment" data-fragment-index="1" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**IG1**: Small business, no IT staffing
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**IG2**: Some IT staffing responsible for protecting infrastructure
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**IG3**: Security experts employed

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/04_03.png)
Source: CIS

</div>

</div>

NOTE:

- Organize an effective cybersecurity program according to Implementation Groups"
  - Implementation groups separate the recommended CIS controls by organization size
    - IG1: Small business, no IT staffing
    - IG2: Some IT staffing responsible for protecting infrastructure
    - IG3: Security experts employed

---

<!-- .element class="split-screen-with-title" -->
# CIS Benchmarks

<div>

<div>

- CIS benchmarks are a set of configuration standards and best practices designed to help organizations ‘harden' the security of their digital assets <!-- .element: class="fragment" data-fragment-index="1" -->
  - Configuration of existing assets <!-- .element: class="fragment" data-fragment-index="2" -->
  - Developed by industry expert consensus <!-- .element: class="fragment" data-fragment-index="3" -->
- CIS benchmark levels <!-- .element: class="fragment" data-fragment-index="4" -->
  - Level 1 - Less strict <!-- .element: class="fragment" data-fragment-index="5" -->
  - Level 2 - More strict <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/04_02.png)
Source: CIS

</div>

</div>

NOTE:

- What are CIS Benchmarks?
  - CIS benchmarks are a set of configuration standards and best practices designed to help organizations ‘harden’ the security of their digital assets
  - "Relate specifically to the configuration of existing assets, excluding security defenses like firewalls and EDRs"
  - "Developed by consensus between experts that include SMEs, security vendors, the CIS benchmarking team, and even the global security community via the CIS Workbench"
  - "While not a regulatory requirement, most prominent compliance frameworks point to CIS benchmarks as the industry standard"
- CIS benchmarks contain two levels
  - "Level 1 is designed to rapidly minimize the attack surface of an organization without hindering usability or business functionality. These standards can be considered the minimum level of security and compliance that all organizations should aim to meet or exceed."
  - "Level 2 is a more stringent set of standards designed to maximize an organization’s security posture through ‘defense in depth’. These standards are intended for environments where security is essential, and are more costly and labor intensive to implement."

---

<!-- .element class="title-and-subtitle" -->
# AWS AMI Hardening

## Applying CIS Benchmarks to the Cloud

---

<!-- .element class="split-screen-with-title" -->
# AWS AMIs

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->An **Amazon Machine Image (AMI)** provides the information required to launch an instance.
  - Similar to OVAs in VirtualBox <!-- .element: class="fragment" data-fragment-index="2" -->
  - Customizable <!-- .element: class="fragment" data-fragment-index="3" -->
- AWS Marketplace <!-- .element: class="fragment" data-fragment-index="4" -->
- Community AMIs <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/04_04.png)
Source: Wunderwelt.de

</div>

</div>

NOTE:

- What is an AMI?
  - An Amazon Machine Image (AMI) provides the information required to launch an instance. It can be roughly compared to how OVA files are used for VirtualBox.
  - AMIs can be customized. "You can launch an instance from an existing AMI, customize the instance (for example, install software on the instance), and then save this updated configuration as a custom AMI.
  - Instances launched from this new custom AMI include the customizations that you made when you created the AMI."

---

<!-- .element class="split-screen-with-title" -->
# AMI Hardening

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**AMI hardening** involves configuring AMIs to prioritize security over mere convenience
  - What are pre-hardened CIS AMIs? <!-- .element: class="fragment" data-fragment-index="2" -->
  - These are AMIs that have already been configured to meet CIS standards. <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**AWS Config** is a "service that enables you to assess, audit, and evaluate the configurations of your AWS resources."
  - Must be enabled in order to run CIS benchmark assessments in Security Hub. <!-- .element: class="fragment" data-fragment-index="5" -->
  - Pricing based on changes recorded <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/04_05.png)
Source: Wikimedia

</div>

</div>

NOTE:

- What is AMI hardening and why is it important?
  - AMI hardening involves configuring AMIs to prioritize security over mere convenience
- What are prehardened CIS AMIs?
- These are AMIs that have already been configured to meet CIS standards.

---

<!-- .element class="split-screen-with-title" -->
# AWS Security Hub

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**AWS Security Hub** provides you with a comprehensive view of your security state in AWS and helps you check your environment against security industry standards and best practices."
  - Free 30-day trial <!-- .element: class="fragment" data-fragment-index="2" -->
  - Takes 2 hours to spin up <!-- .element: class="fragment" data-fragment-index="3" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/04_02.png)
Source: CIS

</div>

NOTE:

- AWS Security Hub capabilities:
  - Centralized Insights: AWS Security Hub offers a centralized view of security findings from multiple sources.
  - Continuous Monitoring: It provides ongoing monitoring for security risks and alerts organizations about vulnerabilities and misconfigurations.
  - Standards and Best Practices: Aligns with industry standards and offers guidance on security configurations.
  - Automated Recommendations: Provides automated insights and recommendations for improving security.
  - Integration with Tools: Integrates with AWS and third-party security tools for streamlined operations.
  - Customizable Dashboards: Create tailored dashboards to visualize security findings and metrics.
  - Security Automation: Supports automation and orchestration for efficient incident response.

---

<!-- .element class="split-screen-with-title" -->
# Security Controls

<div>

<div>

- How can I audit my AWS EC2 instances against CIS benchmarks?
  - Enable AWS Config
  - Enable AWS Security Hub
- CIS standards are listed by OS

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-04/slides/assets/04_02.png)
Source: CIS

</div>

</div>

NOTE:

- What is AWS Config?

  - AWS Config is a "service that enables you to assess, audit, and evaluate the configurations of your AWS resources."
  - AWS Config needs to be enabled in order to run CIS benchmark assessments in Security Hub.
  - Pricing based on changes recorded

---

<!-- .element class="main-title" -->
# Demo

NOTE:

DO:

- AMI Hardening
  - Deploy a Windows 10 instance to AWS EC2
  - Open the CIS benchmark list and select Windows 10
  - Select one of the standards and manually configure it using the Windows 10 GUI; test and verify it took the change
  - Automate the change in PowerShell by referring to PowerShell documentation to help you write a basic shell script; test it in the instance
- Introduce AWS Config
- Introduce AWS Security Hub
