<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 19

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 19 - Cloud Detective Controls

- Course Overview<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - Cloud Logging and Monitoring
- Lecture
  - Cloud Detective Controls
- Demo

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/00_01.png)
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

- &shy;<!-- .element style="color: red;" -->**Class 19** - Cloud Detective Controls

<br>

- **Class 20** - Midterm Project Kickoff

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

- &shy;<!-- .element style="color: red;" -->**Class 19** - Mock Interviews

<br>

- **Class 20** - N/A

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Review:

## Cloud Logging and Monitoring

---

<!-- .element class="image-and-title" -->
# AWS CloudTrail

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/18_05.png)

Source: AWS CloudTrail Documentation

---

<!-- .element class="split-screen-with-title" -->
# Amazon CloudWatch

<div>

<div>

- &shy; <!-- .element: class="fragment" data-fragment-index="1" -->**Amazon CloudWatch**
  - A monitoring and observability service for AWS resources and applications <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Key functions include:**
  - Infrastructure monitoring and troubleshooting <!-- .element: class="fragment" data-fragment-index="3" -->
  - Resource optimization <!-- .element: class="fragment" data-fragment-index="4" -->
  - Application monitoring <!-- .element: class="fragment" data-fragment-index="5" -->
  - Log analytics <!-- .element: class="fragment" data-fragment-index="6" -->
  - Alerting <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/18_06.png)

</div>

</div>

NOTE:

- What is AWS CloudWatch?
  - "Amazon CloudWatch is a monitoring and observability service built for DevOps engineers, developers, site reliability engineers (SREs), and IT managers." Key functions include:
    - Infrastructure monitoring and troubleshooting
    - Resource optimization
    - Application monitoring
    - Log analytics

---

<!-- .element class="split-screen-with-title" -->
# VPC Flow Logs

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What are VPC Flow Logs?**
  - VPC Flow Logs enable you to capture information about the IP traffic going to and from network interfaces in your VPC <!-- .element: class="fragment" data-fragment-index="1" -->
  - Flow log data can be published to Amazon CloudWatch Logs or Amazon S3. <!-- .element: class="fragment" data-fragment-index="2" -->
  - After you've created a flow log, you can retrieve and view its data in the chosen destination <!-- .element: class="fragment" data-fragment-index="3" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/18_07.png)

</div>

</div>

NOTE:

- What are VPC flow logs?
  - VPC Flow Logs is a feature that enables you to capture information about the IP traffic going to and from network interfaces in your VPC.
  - Flow log data can be published to Amazon CloudWatch Logs or Amazon S3.
  - After you've created a flow log, you can retrieve and view its data in the chosen destination."

In the following example, you create a flow log (fl-aaa) that captures accepted traffic for the network interface for instance A1 and publishes the flow log records to an Amazon S3 bucket. You create a second flow log that captures all traffic for subnet B and publishes the flow log records to Amazon CloudWatch Logs. The flow log (fl-bbb) captures traffic for all network interfaces in subnet B. There are no flow logs that capture traffic for instance A2's network interface.

---

<!-- .element class="main-title" -->
# Event-Driven Security

---

<!-- .element class="split-screen-with-title" -->
# Learning Objectives

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is event-driven architecture?**
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**How can we use events to automate incident response in the cloud?**
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**What is serverless code?**
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**How can I programmatically respond to changes in the cloud?**
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**What should I use for threat detection in the cloud?**
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Do I have access to CTI to improve the quality of threat detection?**

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/19_01.png)

</div>

</div>

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/19_01.png)

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

<!-- .element class="image-and-title" -->
# Event-Driven Architecture

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/19_02.png)

NOTE:
Here's an example of an event-driven architecture for an e-commerce site. This architecture enables the site to react to changes from a variety of sources during times of peak demand, without crashing the application or over-provisioning resources.

Event-driven architectures are ideal for improving agility and moving quickly. They're commonly found in modern applications that use microservices, or any application that has decoupled components. When adopting an event-driven architecture, you may need to rethink the way you view your application design. To set yourself up for success, consider the following:

• The durability of your event source. Your event source should be reliable and guarantee delivery if you need to process every single event.

• Your performance control requirements. Your application should be able to handle the asynchronous nature of event routers.

• Your event flow tracking. The indirection introduced by an event-driven architecture allows for dynamic tracking via monitoring services, but not static tracking via code analysis.

• The data in your event source. If you need to rebuild state, your event source should be deduplicated and ordered.

---

<!-- .element class="split-screen-with-title" -->
# Event-Driven Security

<div>

<div>

- With an event-driven response system, a detective mechanism triggers a responsive mechanism to automatically remediate the event <!-- .element: class="fragment" data-fragment-index="1" -->
  - Reduce detection to response time <!-- .element: class="fragment" data-fragment-index="2" -->
  - Raise alerts automatically <!-- .element: class="fragment" data-fragment-index="3" -->
  - Run code in response to events with AWS Lambda <!-- .element: class="fragment" data-fragment-index="4" -->
- AWS Lambda allows you to run serverless functions in response to events <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/19_01.png)

NOTE:

With an event-driven response system, a detective mechanism triggers a responsive mechanism to automatically remediate the event. You can use event-driven response capabilities to reduce the time-to-value between detective mechanisms and responsive mechanisms. To create this event-driven architecture, you can use AWS Lambda, which is a serverless compute service that runs your code in response to events and automatically manages the underlying compute resources for you.
For example, assume that you have an AWS account with the AWS CloudTrail service enabled. If AWS CloudTrail is ever disabled (through the cloudtrail:StopLogging API), the response procedure is to enable the service again and investigate the user that disabled the AWS CloudTrail logging. Instead of performing these steps manually in the AWS Management Console, you can programmatically enable the logging again (through the cloudtrail:StartLogging API). If you implement this with code, your response objective is to perform this task as quickly as possible and notify the responders that the response was performed.

---

<!-- .element class="split-screen-with-title" -->
# Serverless Code

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is AWS Lambda?**
  - A compute service that runs code without the need for provisioning or managing servers (serverless) <!-- .element: class="fragment" data-fragment-index="1" -->
  - Code is executed on cloud compute infrastructure (no instances necessary) <!-- .element: class="fragment" data-fragment-index="2" -->
  - Functions in Lambda are triggered by events <!-- .element: class="fragment" data-fragment-index="3" -->
    - State changes in a S3 bucket <!-- .element: class="fragment" data-fragment-index="4" -->
    - Respond to security concerns automatically <!-- .element: class="fragment" data-fragment-index="5" -->
    - Messages from other AWS services <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/19_03.png)

</div>

</div>

NOTE:

- What is AWS Lambda?
  - AWS Lambda is a compute service that runs code without the need for provisioning or managing servers (serverless)
  - Code is executed on cloud compute infrastructure (no instances necessary)
  - Run Lambda functions in response to events
    - Example, state changes in a S3 bucket
    - Respond to security concerns automatically
    - Alternatively, developers can build serverless applications with Lambda

---

<!-- .element class="split-screen-with-title" -->
# Serverless Code

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Getting started with AWS Lambda**
  - AWS Lambda webpage <!-- .element: class="fragment" data-fragment-index="2" -->
  - AWS Lambda Developer Guide <!-- .element: class="fragment" data-fragment-index="3" -->
    - Getting Started <!-- .element: class="fragment" data-fragment-index="4" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Security purposes**
    - CloudTrail integration <!-- .element: class="fragment" data-fragment-index="6" -->
    - CloudWatch Events integration <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/19_03.png)

</div>

</div>

NOTE:

https://docs.aws.amazon.com/lambda/latest/dg/welcome.html
https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html
https://docs.aws.amazon.com/lambda/latest/dg/with-cloudtrail.html
https://docs.aws.amazon.com/lambda/latest/dg/services-cloudwatchevents.html

# To configure CloudWatch Events to invoke your function

- Open the Functions page on the Lambda console.
- Choose a function
- Under Function overview, choose Add trigger.
- Set the trigger type to EventBridge(CloudWatch Events).
- For Rule, choose Create a new rule.
- Configure the remaining options and choose Add.

---

<!-- .element class="split-screen-with-title" -->
# Canary in the Coal Mine

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->The **"canary in the coal mine"** term originates from coal mining, where canaries were used to detect toxic gases.
- In security, it refers to indicators or events that serve as early warnings of potential threats, breaches, or vulnerabilities. <!-- .element: class="fragment" data-fragment-index="2" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Examples:**
  - Intrusion detection systems <!-- .element: class="fragment" data-fragment-index="4" -->
  - Honeypots <!-- .element: class="fragment" data-fragment-index="5" -->
  - Anomaly detection tools <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/19_04.png)
Source: Wikimedia Commons, Smithsonian

</div>

</div>

NOTE:

- What is the canary in the coal mine all about?
  - Origins of “Canary in the coal mine”
  - From 1911 to 1986, coal miners brought caged canaries (birds) into coal mines to detect toxic gases
  - Upon detection, canary screeched (or died) and warned miners of danger
- Why a canary?
  - A “sentinel species” more sensitive to carbon monoxide and toxic gas
Later replaced with electronic sensor tools

---

<!-- .element class="split-screen-with-title" -->
# Serverless Code

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**“Canary in the coal mine”** as a detection technique
  - Execute a Lambda function at a regular scheduled interval to check the state of a resource <!-- .element: class="fragment" data-fragment-index="2" -->
  - Anomalies detected lead to CloudWatch alarms triggered <!-- .element: class="fragment" data-fragment-index="3" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/19_05.png)

---

<!-- .element class="split-screen-with-title" -->
# Threat Detection

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is Amazon GuardDuty?**
  - A continuous security monitoring service that continuously monitors for suspicious and malicious activity <!-- .element: class="fragment" data-fragment-index="2" -->
  - Generates real-time alerts and findings when it detects potential security issues <!-- .element: class="fragment" data-fragment-index="3" -->
  - Comes integrated with up-to-date threat intelligence feeds from <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/19_06.png)

</div>

</div>

NOTE:

- What is Amazon GuardDuty?
  - Amazon GuardDuty analyzes selected logs using machine learning models and threat intelligence to produce observable records of suspicious activities, referred to as "findings."
  - Log sources
    - AmazonVPC Flow Logs
    - AWS CloudTrail
    - DNS queries
  - Automatically gathers info from these services without configuration, such as creating a trail in CloudTrail
  - Components
    - A detector consumes information and generates findings within a specific AWS account and region.
    - Findings
      - Archivable using suppression rules
  - Where GuardDuty sends events

---

<!-- .element class="split-screen-with-title" -->
# Threat Detection

- Amazon GuardDuty workflow overview

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/19_07.png)

Source: InfoQ

NOTE:

- Account-level threat detection - accurately detect an account compromise with continuous monitoring in near real-time.
- Continuous monitoring across AWS accounts — monitor and analyze all AWS account and workload event data found on AWS CloudTrail, VPC Flow Logs, and DNS Logs without additional security software or infrastructure.
- Threat detections developed and optimized for the cloud - built-in detection techniques are specifically developed and optimized for the cloud.
- GuardDuty also has integrated threat intelligence with industry-leading third-party security partners, such as Proofpoint and CrowdStrike.
- Threat severity levels for efficient prioritization — features low, medium, and high threat severity levels so customers can respond accordingly.

---

<!-- .element class="image-and-title" -->
# Threat Detection

![Image](/ops-401-cybersecurity-guide/curriculum/class-19/slides/assets/19_08.png)

Source: YouTube - Online Tech Talks

---

<!-- .element class="main-title" -->
# Demo

NOTE:

DO:

- AWS Lambda
  - Demonstrate the canary lambda function deployment
    - https://docs.aws.amazon.com/lambda/latest/dg/services-cloudwatchevents-tutorial.html
- Cloud Detective Controls
  - Demonstrate how to activate and pilot Amazon GuardDuty.
