<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 17

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 17 - Cloud Network Security

- Course Overview<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Warmup
- Ops Challenge
- Review
  - IAM with AWS
- Lecture
  - Cloud Network Security
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

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/00_01.png)
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

- &shy;<!-- .element style="color: red;" -->**Class 17** - Cloud Network Security

<br>

- **Class 18** - Cloud Logging and Monitoring

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

- &shy;<!-- .element style="color: red;" -->**Class 17** - Brute Force Attack Tool Pt. 2 of 3

<br>

- **Class 18** - Brute Force Attack Tool Pt. 3 of 3

<br>

- **Class 19** - Mock Interviews

<br>

- **Class 20** - N/A

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Warmup

---

<!-- .element class="main-title" -->
# Review:

## Lab & Ops Challenge

---

<!-- .element class="main-title" -->

# Ops Challenge

NOTE:

DO: Refer to DEMO.md to show today's demo code

---

<!-- .element class="main-title" -->
# Review:

# Cloud IAM

---

<!-- .element class="image-and-title" -->
# AWS IAM

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/16_05.png)
Source: Medium

---

<!-- .element class="split-screen-with-title" -->
# AWS IAM Policies

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Inline policy**
  - A policy that's embedded in an IAM identity (a user, group, or role)
  - Policy is an inherent part of the identity <!-- .element: class="fragment" data-fragment-index="2" -->
  - Specific to a single identity and can't be detached or reused <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**AWS managed policy**
  - A standalone policy that is created and administered by AWS <!-- .element: class="fragment" data-fragment-index="5" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->Standalone policies have their own **Amazon Resource Name (ARN)** that includes the policy name

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/16_09.png)
Source: AWS Documentation

</div>

</div>

NOTE:

“Inline policies are useful if you want to maintain a strict one-to-one relationship between a policy and the identity that it's applied to. For example, you want to be sure that the permissions in a policy are not inadvertently assigned to an identity other than the one they're intended for.”

“This diagram illustrates inline policies. Each policy is an inherent part of the user, group, or role. Notice that two roles include the same policy (the DynamoDB-books-app policy), but they are not sharing a single policy; each role has its own copy of the policy.”

- Policy documents
  - Identity-based policies
    - Inline Policy
    - Customer-Managed Policy
    - AWS-Managed Policy
  - S3 Policies
    - ACL
    - Bucket

---

<!-- .element class="split-screen-with-title" -->
# Interacting with AWS

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**How can a user interact with AWS?**
  - AWS Management Console <!-- .element: class="fragment" data-fragment-index="2" -->
  - AWS Command Line Interface (CLI) <!-- .element: class="fragment" data-fragment-index="3" -->
    - Supports script execution <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Free tier**
  - Review how free tier works <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/16_13.png)
Source: AWS Documentation

</div>

</div>

NOTE:

---

<!-- .element class="main-title" -->
# Cloud Network Security

---

<!-- .element class="split-screen-with-title" -->
# Learning Objectives

<div>

<div>

- &shy;**What exactly is a VPC on AWS?**
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**How can we design secure VPC architectures?**
  - &shy;<!-- .element: class="fragment" data-fragment-index="3" -->Implement network segmentation for enhanced security
  - Configure security groups and NACLs for traffic control<!-- .element: class="fragment" data-fragment-index="4" -->
  - Apply security best practices within your VPC <!-- .element: class="fragment" data-fragment-index="5" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**How can we monitor VPC traffic?**

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/17_01.png)

</div>

</div>

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/17_02.png)

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
# Regions and Zones

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" --> **Availability Zones**
  - Isolated data centers within an AWS region <!-- .element: class="fragment" data-fragment-index="2" -->
  - Independent power, cooling, and networking <!-- .element: class="fragment" data-fragment-index="3" -->
  - Failures in one AZ do not impact resources in others <!-- .element: class="fragment" data-fragment-index="4" -->
  - Represented by adding a letter identifier to the region code <!-- .element: class="fragment" data-fragment-index="5" -->
    - &shy;<!-- .element: class="fragment" data-fragment-index="6" -->Example: us-west-2**a**

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/17_03.png)

</div>

</div>

NOTE:

- What are AWS Availability Zones?
  - An AWS Availability Zone (AZ) is the logical building block that makes up an AWS Region.
  - There are currently 69 AZs, which are isolated locations— data centers — within a region.
  - Each region has multiple AZs and when you design your infrastructure to have backups of data in other AZs you are building a very efficient model of resiliency, i.e. a core concept of cloud computing.
  - When you launch an instance, you can select an Availability Zone or let us choose one for you.
  - If you distribute your instances across multiple Availability Zones and one instance fails, you can design your application so that an instance in another Availability Zone can handle requests.
  - You can also use Elastic IP addresses to mask the failure of an instance in one Availability Zone by rapidly remapping the address to an instance in another Availability Zone.
  - An Availability Zone is represented by a Region code followed by a letter identifier; for example, us-east-1a.
  - To ensure that resources are distributed across the Availability Zones for a Region, we independently map Availability Zones to names for each AWS account. For example, the Availability Zone us-east-1a for your AWS account might not be the same location as us-east-1a for another AWS account.
  - To coordinate Availability Zones across accounts, you must use the AZ ID, which is a unique and consistent identifier for an Availability Zone. For example, use1-az1 is an AZ ID for the us-east-1 Region and it has the same location in every AWS account.

---

<!-- .element class="split-screen-with-title" -->
# Regions and Zones

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Local Zone**
  - Acts as an extension of a parent AWS region <!-- .element: class="fragment" data-fragment-index="2" -->
  - Located in metropolitan areas for minimal latency <!-- .element: class="fragment" data-fragment-index="3" -->
  - Used for applications like real-time gaming and trading <!-- .element: class="fragment" data-fragment-index="4" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->Represented by an AWS Region code followed by an identifier that indicates the location
    - Example: us-west-2-**lax-1a**.

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/17_03.png)

NOTE:

- A Local Zone is an extension of an AWS Region in geographic proximity to your users
- Local Zones have their own connections to the internet and support AWS Direct Connect, so that resources created in a Local Zone can serve local users with low-latency communications.
- A Local Zone is represented by a Region code followed by an identifier that indicates the location, for example, us-west-2-lax-1a.
- To use a Local Zone, you must first enable it. For more information, see Opt in to Local Zones. Next, create a subnet in the Local Zone.
- Finally, launch any of the following resources in the Local Zone subnet, so that your applications are close to your end users:
  - Amazon EC2 instances
  - Amazon EBS volumes
  - Amazon ECS
  - Amazon EKS
- In addition to the above list, the following resources are available in the Los Angeles Local Zones.
  - Amazon FSx file servers
  - Elastic Load Balancing
  - Amazon EMR
  - Amazon ElastiCache
  - Amazon Relational Database Service
  - Dedicated Hosts
Source: Amazon EC2 User Guide for Linux Instances

---

<!-- .element class="split-screen-with-title" -->
# VPC Basics

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Virtual Private Cloud (VPC)**
  - Create logically isolated network environments in AWS <!-- .element: class="fragment" data-fragment-index="2" -->
  - Allows definition of custom IP address ranges <!-- .element: class="fragment" data-fragment-index="2" -->
  - Segments resources into public and private subnets <!-- .element: class="fragment" data-fragment-index="3" -->
  - VPCs are specific to an AWS region <!-- .element: class="fragment" data-fragment-index="4" -->
- Next, we will take a look at some example use cases of a VPC: <!-- .element: class="fragment" data-fragment-index="5" -->
  - Public subnet  <!-- .element: class="fragment" data-fragment-index="6" -->
  - Public and private subnet <!-- .element: class="fragment" data-fragment-index="7" -->
  - Public and private subnet connected to corporate LAN <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/17_04.png)

</div>

</div>

NOTE:

- An Amazon Virtual Private Cloud (Amazon VPC) enables you to launch AWS resources into a virtual network that you've defined
  - Resembles a traditional LAN except with access to scalability of AWS

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/17_05.png)

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
# VPC - Public Subnet

<div>

<div>

- A company hosting only public services, such as a web app, might only need a single public subnet in its VPC <!-- .element: class="fragment" data-fragment-index="1" -->
  - Example: <!-- .element: class="fragment" data-fragment-index="2" -->
    - Code 401 student project <!-- .element: class="fragment" data-fragment-index="3" -->
    - Web application server <!-- .element: class="fragment" data-fragment-index="4" -->
    - Public file server <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/17_06.png)

</div>

</div>

NOTE:

- A public subnet hosts public-facing services like a web site or file server.
  - An internet gateway is a gateway that you attach to your VPC to enable communication between resources in your VPC and the internet

---

<!-- .element class="split-screen-with-title" -->
# VPC - Public & Private Subnet

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Network Address Translation (NAT) Gateways**
  - Perform network address translation for resources in private subnets <!-- .element: class="fragment" data-fragment-index="2" -->
  - Enable instances in private subnets to initiate outbound traffic to the internet <!-- .element: class="fragment" data-fragment-index="3" -->
- NAT gateways charge for use; be sure to delete yours at end of lab time <!-- .element: class="fragment" data-fragment-index="2" -->
- Traffic can be monitored with CloudWatch <!-- .element: class="fragment" data-fragment-index="3" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/17_07.png)

</div>

</div>

NOTE:

This diagram illustrates the architecture of a VPC with a NAT gateway. The main route table sends internet traffic from the instances in the private subnet to the NAT gateway. The NAT gateway sends the traffic to the internet gateway using the NAT gateway's Elastic IP address as the source IP address.

---

<!-- .element class="split-screen-with-title" -->
# Hybrid Cloud via VPN

<div>

<div>

- On-prem corporate networks can extend into the cloud using an IPsec VPN tunnel <!-- .element: class="fragment" data-fragment-index="1" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**The VPC can still have a private and public subnet**
  - Put web servers in the public subnet front end <!-- .element: class="fragment" data-fragment-index="3" -->
  - Put private systems in the private subnet backend <!-- .element: class="fragment" data-fragment-index="4" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Private AWS resources may include**
  - ERP software <!-- .element: class="fragment" data-fragment-index="6" -->
  - Databases <!-- .element: class="fragment" data-fragment-index="7" -->
  - Internal web servers <!-- .element: class="fragment" data-fragment-index="8" -->
  - File servers <!-- .element: class="fragment" data-fragment-index="9" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/17_08.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# VPC Security Controls

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Security groups**
  - Act as a virtual firewall controlling inbound and outbound traffic
  - Act at the instance level, not the subnet level <!-- .element: class="fragment" data-fragment-index="2" -->
  - By default, Security Groups deny all inbound traffic <!-- .element: class="fragment" data-fragment-index="3" -->
  - They are stateful, so if you allow outbound traffic, inbound response traffic is automatically allowed <!-- .element: class="fragment" data-fragment-index="4" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/17_09.png)

NOTE:

- If you associate an IPv6 CIDR block with your VPC and subnets, you must add separate rules to your WebServerSG and DBServerSG security groups to control inbound and outbound IPv6 traffic for your instances.
- In this scenario, the web servers will be able to receive all internet traffic over IPv6, and SSH or RDP traffic from your local network over IPv6. They can also initiate outbound IPv6 traffic to the internet.
- The database servers cannot initiate outbound IPv6 traffic to the internet, so they do not require any additional security group rules.
- The following are the IPv6-specific rules for the WebServerSG security group (which are in addition to the rules listed above).

---

<!-- .element class="split-screen-with-title" -->
# VPC Security Controls

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Network Access Controls List (ACL)**
  - Act as stateless, virtual network firewalls at the subnet level <!-- .element: class="fragment" data-fragment-index="2" -->
  - Associated with subnets and apply to all resources in that subnet <!-- .element: class="fragment" data-fragment-index="3" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-17/slides/assets/17_10.png)

---

<!-- .element class="text-only" -->
# VPC Security Best Practices

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Least Privilege:** Apply the principle of least privilege to security groups and NACL rules
- &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Security Group Restrictions:** Restrict inbound traffic to only necessary ports and sources.
- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Private Subnets:** Place sensitive resources in private subnets inaccessible from the internet
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Network Segmentation:** Use subnets and route tables for network segmentation and access control
- &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Remote Connectivity:** Remote networks should connect to VPCs using either:
  - AWS Virtual Private Network (VPN)
  - AWS Direct Connect
- &shy;<!-- .element: class="fragment" data-fragment-index="6" -->**Monitoring and Logging:** Implement VPC Flow Logs for network monitoring and CloudWatch for logging

NOTE:

---

<!-- .element class="main-title" -->
# Demo

NOTE:

DO:

- Demo 1: Cloud Network Security
  - Today we'll be demonstrating the following operations:
    - Create a VPC
    - Create a public and a private subnet
    - Create a security group
    - Create an internet gateway
    - Create a NAT gateway
    - Deploy an Ubuntu Server instance in EC2 to the VPC in the public subnet
  - Preparing the VPC and associated objects
    - Login to your AWS Management Console and pick a region (us-west-2 for this example)
    - Access VPC service in your AWS Management Console, then go to Your VPCs
    - Create VPC (don't use the VPC Wizard)
      - Name tag: class-demo
      - IPv4 CIDR block: 192.168.0.0/16
    - Review the newly-created VPC's four tabs:
      - Details
        - Note that this is NOT the default VPC
      - CIDRs
      - Flow logs (we'll be learning more this week on this)
      - Tags
    - Create a public subnet
      - Associate to the class-demo VPC
      - Select Availability Zone us-west-2a; discuss Availability Zones if you need to
      - Select an IPv4 CIDR block that is within the scope of the VPC's overall network.
        - Let's do 192.168.1.0/27 (say we need room for exactly 32 host addresses).
      - Create a Key with Name = subnet-demo-public; discuss why keys are important if necessary
    - Create a private subnet
      - Associate to the class-demo VPC
      - Challenge students to select a workable CIDR addressing scheme for this subnet
    - Create an internet gateway and associate it to your VPC
    - Create a NAT gateway
    - View how to edit routes
