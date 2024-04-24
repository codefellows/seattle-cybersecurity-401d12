<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 18

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 18 - Cloud Logging and Monitoring

- Course Overview<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - Cloud Network Security
- Lecture
  - Cloud Logging and Monitoring
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/00_01.png)
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

- &shy;<!-- .element style="color: red;" -->**Class 18** - Cloud Logging and Monitoring

<br>

- **Class 19** - Cloud Detective Controls

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

- &shy;<!-- .element style="color: red;" -->**Class 18** - Brute Force Attack Tool Pt. 3 of 3

<br>

- **Class 19** - Mock Interviews

<br>

- **Class 20** - N/A

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Review:

# Lab & Ops Challenge

---

<!-- .element class="main-title" -->

# Ops Challenge

---

<!-- .element class="main-title" -->
# Review:

# Cloud Network Security

---

<!-- .element class="split-screen-with-title" -->
# Regions and Zones

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Three categories of locations:**
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Regions**
    - A geographic area where AWS operates data centers <!-- .element: class="fragment" data-fragment-index="3" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Availability Zones**
    - An isolated data center within a region <!-- .element: class="fragment" data-fragment-index="5" -->
    - They are physically isolated from each other <!-- .element: class="fragment" data-fragment-index="6" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="7" -->**Local Zones**
    - Located in metropolitan areas, so they are physically closer to specific users or data sources <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/17_02.png)

</div>

</div>

NOTE:

- What are AWS Regions?
  - AWS Regions are separate geographic areas that AWS uses to house its infrastructure.
  - These are distributed around the world so that customers can choose a region closest to them in order to host their cloud infrastructure there.
  - The closer your region is to you, the better, so that you can reduce network latency as much as possible for your end-users.
  - You want to be near the data centers for fast service.
- Best practices for choosing AWS RegionsIn general, try to follow these best practices when you choose a region, to help ensure top performance and resilience:
  - Proximity: Choose a region closest to your location and your customers’ location to optimize network latency.
  - Services: Try and think about what are your most needed services.
    - Usually, the newest services start on a few main regions then pop up in other regions later.
  - Cost: Certain regions will cost more than others, so use built-in AWS calculators to do rough cost estimates to inform your choices.
  - Service Level Agreement (SLA): Just as with cost, your SLA details will vary by region, so be sure to be aware of what your needs are and if they’re being met
  - Compliance: You may need to meet regulatory compliance needs such as GDPR by hosting your deployment in a specific — or multiple regions.

---

<!-- .element class="split-screen-with-title" -->
# VPC Concepts

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->A **subnet** is a range of IP addresses in your VPC, much like a traditional LAN subnet.
  - Must fit within the scope of your VPC <!-- .element: class="fragment" data-fragment-index="2" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Example: **192.168.0.0/16** as a VPC would support a **192.168.1.0/24** subnet.
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->A **public subnet** hosts public-facing services like a web site or file server.
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->A **private subnet** is instead meant for internal resources and does not allow access from outside the VPC

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/17_05.png)

</div>

</div>

NOTE:

- A subnet is a range of IP addresses in your VPC, much like a traditional LAN subnet.
  - Must fit within the scope of your VPC
  - Example: 192.168.0.0/16 as as VPC would support a 192.168.1.0/24 subnet.
  - A public subnet hosts public-facing services like a web site or file server.
  - An internet gateway is a gateway that you attach to your VPC to enable communication between resources in your VPC and the internet.
  - A private subnet does not allow access to resources from outside the VPC, and is instead meant for internal resources.
  - You can use a network address translation (NAT) gateway to enable instances in a private subnet to connect to the internet or other AWS services, but prevent the internet from initiating a connection with those instances.

---

<!-- .element class="split-screen-with-title" -->
# VPC Security Controls

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Security groups**
  - Act as a virtual firewall controlling inbound and outbound traffic
  - Act at the instance level, not the subnet level <!-- .element: class="fragment" data-fragment-index="2" -->
  - By default, Security Groups deny all inbound traffic <!-- .element: class="fragment" data-fragment-index="3" -->
  - They are stateful, so if you allow outbound traffic, inbound response traffic is automatically allowed <!-- .element: class="fragment" data-fragment-index="4" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/17_09.png)

NOTE:

- If you associate an IPv6 CIDR block with your VPC and subnets, you must add separate rules to your WebServerSG and DBServerSG security groups to control inbound and outbound IPv6 traffic for your instances.
- In this scenario, the web servers will be able to receive all internet traffic over IPv6, and SSH or RDP traffic from your local network over IPv6. They can also initiate outbound IPv6 traffic to the internet.
- The database servers cannot initiate outbound IPv6 traffic to the internet, so they do not require any additional security group rules.
- The following are the IPv6-specific rules for the WebServerSG security group (which are in addition to the rules listed above).

---

<!-- .element class="main-title" -->
# Resources for AWS Study

---

<!-- .element class="split-screen-with-title" -->
# AWS Study Resources

<div>

<div>

- AWS Blog <!-- .element: class="fragment" data-fragment-index="1" -->
- AWS Podcast <!-- .element: class="fragment" data-fragment-index="2" -->
- AWS Certifications <!-- .element: class="fragment" data-fragment-index="3" -->

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/18_01.png)

NOTE:

AWS Blog
AWS Podcast
AWS Certifications

---

<!-- .element class="main-title" -->
# Why do we care about cloud?

---

<!-- .element class="split-screen-with-title" -->
# Cloud Security

<div>

<div>

- If there is a 50% increase in a market there will be a parallel increase in the amount of staffing and hiring in that market. <!-- .element: class="fragment" data-fragment-index="1" -->
- Job postings looking for Azure and AWS talent have skyrocketed in the past year and are continuing to trend upwards. <!-- .element: class="fragment" data-fragment-index="2" -->

</div>

<div>

# 2022 CSP <!-- .element: class="fragment" data-fragment-index="3" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/18_02.png) <!-- .element: class="fragment" data-fragment-index="4" -->

Source: Statista <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

</div>

NOTE:

- David's story: "I previously worked with an ITAR-compliant company that needed to keep its data out of the hands of foreign nationals. We ended up adopting AWS GovCloud."

---

<!-- .element class="main-title" -->
# Cloud Logging and Monitoring

---

<!-- .element class="split-screen-with-title" -->
# Learning Objectives

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**How can we achieve governance, compliance, and auditing of our cloud?**
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**How can we collect event logs in the cloud?**
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**What tooling helps us analyze event log data?**
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**How can the cloud react to security concerns as they occur?**
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**How can we monitor and protect our VPCs?**

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/18_03.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# AWS CloudTrail

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is AWS CloudTrail?**
  - A service that enables governance, compliance, operational auditing, and risk auditing of your AWS account.
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**CloudTrail logs includes the following:**
  - The service <!-- .element: class="fragment" data-fragment-index="3" -->
  - The name of API action performed <!-- .element: class="fragment" data-fragment-index="4" -->
  - Region resource located in <!-- .element: class="fragment" data-fragment-index="5" -->
  - Response elements <!-- .element: class="fragment" data-fragment-index="6" -->
  - Principal that made the request <!-- .element: class="fragment" data-fragment-index="7" -->
  - Date and time of the request <!-- .element: class="fragment" data-fragment-index="8" -->
  - IP address of the requester <!-- .element: class="fragment" data-fragment-index="9" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/18_04.png)

</div>

</div>

NOTE:

- What is AWS CloudTrail?
  - AWS CloudTrail is a service that enables governance, compliance, operational auditing, and risk auditing of your AWS account.
  - Each CloudTrail log includes the following parameters:
    - The service
    - The name of API action performed
    - Region resource located in
    - Response elements
    - Principal that made the request
    - Date and time of the request
    - IP address of the requester
  - Maintains event history of account activity, including CLI
- Important part of AWS cloud threat detection
- Pricing
  - "You can view, filter, and download the most recent 90 days of your account activity for all management events in supported AWS services free of charge."
- What types of events are handled by AWS CloudTrail?
  - CloudTrail event classification:
    - API vs Non-API
    - Management vs Data Events

---

<!-- .element class="image-and-title" -->
# AWS CloudTrail

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/18_05.png)

Source: AWS CloudTrail Documentation

---

<!-- .element class="split-screen-with-title" -->
# AWS CloudTrail

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**CloudTrail logs perform the following:**
  - Provides a detailed view of AWS activities, including CLI <!-- .element: class="fragment" data-fragment-index="2" -->
  - Important part of AWS cloud threat detection <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Pricing**
  - You can view, search, and download the most recent 90-day history <!-- .element: class="fragment" data-fragment-index="5" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**What types of events are handled by AWS CloudTrail?**
  - API vs Non-API <!-- .element: class="fragment" data-fragment-index="7" -->
  - Management vs Data Events <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/18_04.png)

</div>

</div>

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/18_06.png)

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
# Amazon CloudWatch

<div>

<div>

- CloudWatch Alarms can be set to automatically respond to changes in metrics, triggering notifications or actions when thresholds are breached <!-- .element: class="fragment" data-fragment-index="1" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Key components include:**
  - Alarms <!-- .element: class="fragment" data-fragment-index="3" -->
  - Dashboards <!-- .element: class="fragment" data-fragment-index="4" -->
  - Logs <!-- .element: class="fragment" data-fragment-index="5" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**CloudWatch Logs can aggregate logs from:**
  - Route 53 DNS query logs <!-- .element: class="fragment" data-fragment-index="7" -->
  - VPC flow logs <!-- .element: class="fragment" data-fragment-index="8" -->
  - CloudTrail logs <!-- .element: class="fragment" data-fragment-index="9" -->
  - Non-AWS sources <!-- .element: class="fragment" data-fragment-index="10" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/18_06.png)

</div>

</div>

NOTE:

- "Amazon CloudWatch enables you to set alarms and automate actions based on either predefined thresholds, or on machine learning algorithms that identify anomalous behavior in your metrics"
- Key components of CloudWatch include:
  - Alarms
  - Dashboards
  - Logs
  - CloudWatch Logs is a log aggregation service that supports ingestion of both AWS and non-AWS sources
  - Example supported logs:
    - Route 53 DNS query logs
    - VPC flow logs
    - CloudTrail logs
  - Logs from the same source are organized into a single log stream
  - Retention can be as short as 1 day or as long as 10 years
  - Archivable to S3 bucket
- Metric filters
- Events

---

<!-- .element class="split-screen-with-title" -->
# Amazon CloudWatch

<div>

<div>

- Logs from the same source are organized into a single log stream <!-- .element: class="fragment" data-fragment-index="1" -->
- Retention can be as short as 1 day or as long as 10 years <!-- .element: class="fragment" data-fragment-index="2" -->
- Archivable to S3 bucket <!-- .element: class="fragment" data-fragment-index="3" -->
  - Metric filters <!-- .element: class="fragment" data-fragment-index="4" -->
  - Events <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/18_06.png)

</div>

</div>

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-18/slides/assets/18_07.png)

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
# Demo

NOTE:

DO:

- Demo 1: CloudTrail & CloudWatch
  - Demonstrate how to setup AWS CloudTrail and initiate log capturing
  - Point out that an S3 bucket is created to store the logs
  - Navigate to S3 service and show the bucket that was created
  - Demonstrate how to send CloudTrail logs to CloudWatch
  - Highlight the creation of a role that gives the CloudTrail service permission to write to the CloudWatch Log groupCome back to this in a few minutes to show that logs are being ingested. Continue to the next portion of the demo for now.
  - Do not highlight the rule creation process, leave this to students to work through
  - Simply point to where they would go to create rules.
- Demo 2: VPC Flow Logs
  - Navigate to VPC service
  - Demonstrate how to create a VPC flow log
  - Highlight the options of sending to CloudWatch or to an S3 bucket
  - Highlight the use of the need for a role in order for VPC Flow logs to write to the CloudWatch Log group
