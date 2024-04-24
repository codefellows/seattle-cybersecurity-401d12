<!-- .element class="main-title" -->
# Career Coaching Workshop

<br>

## CCW6: Presentations

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

Daily TODOs

- Update the class number for each video recording
- Move the dragon icon to the current day
- Hide/unhide slides to show as necessary
- Toggle presentation mode on and screen share this first slide when you initialize recording on Zoom to indicate class number

---

<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 40

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

Daily TODOs

- Update the class number for each video recording
- Move the dragon icon to the current day
- Hide/unhide slides to show as necessary
- Toggle presentation mode on and screen share this first slide when you initialize recording on Zoom to indicate class number

---

<!-- .element class="split-screen-with-title" -->

## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- **Module 6** - Threat Modeling & Analysis

- **Module 7** - Threat Hunting

- &shy;<!-- .element style="color: red;" -->**Module 8** - Web Application Security

- **Module 9** - Penetration Testing

- **Module 10** - Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/0_01.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-with-text" -->

## Module 8 Labs

### Web Application Security

<div align="left" style="font-size: 45px">

- **Class 36** - XSS with w3af, DVWA

<br>

- **Class 37** - Automated AppSec with OWASP ZAP

<br>

- **Class 38** - Attacking Juice Shop with Burp Suite

<br>

- **Class 39** - SQLi with Burp Suite & Web Goat

<br>

- &shy;<!-- .element style="color: red;" -->**Class 40** - N/A

</div>

---

<!-- .element class="split-screen-with-title" -->
## Module 8 Challenges

<div>

<div align="left" style="font-size: 35px">

- **Class 36** - Web App Fingerprinting Part 1 of 3

<br>

- **Class 37** - Web App Fingerprinting Part 2 of 3

<br>

- **Class 38** - Web App Fingerprinting Part 3 of 3

<br>

- **Class 39** - Mock Interviews

<br>

- &shy;<!-- .element style="color: red;" -->**Class 40** - Vulnerability Scanning with Nessus

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/2_0.png)<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="main-title" -->
# Review: SQLi

---

<!-- .element class="split-screen-with-title" -->
# OWASP Top Ten

<div>

<div>

- Injection such as SQL, NoSQL, OS, and LDAP injection, occur when untrusted data is sent to an interpreter as part of a command or query
  - Attacker's hostile data tricks interpreter into executing unintended commands or accessing data without proper authorization

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/10_0.png)
Source: OWASP, 9Lessons

</div>

</div>

NOTE:

- The most common and successful injection attack technique
- Happens when attackers inject SQL queries directly into the input form
  - Bypassing the front end and executing directly on the database on the backend
- This can also be tried on the URL itself - passing authentication credentials by changing the URL

- Three main categories
  - In-band SQL Injection
    - Attacker uses the same communication channel to perform and retrieve the results of the attack
    - Most common type
  - Out-of-band SQL Injection
    - Use different communication channels for the attack and results
    - Harder to pull of
  - Blind/Inferential
    - Attacker knows the db is vulnerable to injection
    - Error messages and screen returns don't come back to the attacker
    - More trial and error
    - Takes longer to pull off

---

<!-- .element class="split-screen-with-title" -->
# Injection

<div>

<div>

- Structured Query Language (SQL) Injection is a code injection technique used to modify or retrieve data from SQL databases by inserting specialized SQL statements into a typeable field on the front end of a web application
  - Example: `SELECT * FROM Users WHERE UserId = 105 OR 1=1;`
  - `1=1` will always result in true, so condition is satisfied resulting in execution of SELECT * FROM Users

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-39/slides/assets/17_0.png)
Source: OWASP, 9Lessons

</div>

</div>

---

<!-- .element class="main-title" -->
# Finding Vulnerabilities

---

<!-- .element class="split-screen-with-title" -->
# Vulnerability Analyst

<div>

<div>

A vulnerability analyst security professional that detects weaknesses in networks and then takes measures to help the organization correct and strengthen the system's security levels.

- Develops risk-based mitigation strategies for networks, operating systems, and applications
- Organize network-based scans to identify possible network security attacks and host-based scans to identify vulnerabilities in workstations, servers, and other network hosts.
- Salary range: $75,000-92,600
- Demand: From 2016 to 2026, CompTIA projects an increase of 19 percent with 17,917 net new jobs expected during that 10-year period.

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-40/slides/assets/9_0.png)
Source: Technofaq.org

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Vulnerability Assessments

<div>

<div>

- A vulnerability is a weakness in an information system, system security procedures, internal controls, or implementation that could be exploited or triggered by a threat source
  - Important to differentiate vulnerability, exploit, and risk.
  - Not all vulnerabilities are likely to be exploited or high risk.
  - Prioritize your vulnerabilities.
- Common Weakness Enumeration (CWE) is a community-developed list of software and hardware weakness types

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-40/slides/assets/10_0.png)
Source: CodedX

</div>

</div>

NOTE:
Apart from these misconfigurations, when running a vulnerability assessment on your network you might find several security issues with a wide range of software and hardware including:
Default passwords on certain devices
Unnecessary services running on some devices
Running web services that contain known vulnerabilities
Dangerous applications such as peer-to-peer applications
Third-party applications that are a vulnerability to known exploits.

---

<!-- .element class="split-screen-with-title" -->
# Vulnerability Assessments

<div>

<div>

- May employ vulnerability analysts or contract third party assessments
- Vulnerability assessments help with:
  - Unnecessary open shares
  - Unused user accounts
  - Unnecessary open ports
  - Rogue devices connected to your systems
  - Dangerous script configurations
  - Servers allowing use of dangerous protocols
  - Incorrect permissions on important system files
  - Running of unnecessary, potentially dangerous services.

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-40/slides/assets/11_0.png)
Source: CodedX

</div>

</div>

NOTE:
Apart from these misconfigurations, when running a vulnerability assessment on your network you might find several security issues with a wide range of software and hardware including:
Default passwords on certain devices
Unnecessary services running on some devices
Running web services that contain known vulnerabilities
Dangerous applications such as peer-to-peer applications
Third-party applications that are a vulnerability to known exploits.

---

<!-- .element class="split-screen-with-title" -->
# Vulnerability Assessments

<div>

<div>

- Tenable's Nessus is a commercial vulnerability scanning software
  - Free for non-enterprise use
  - “As part of the Nessus family, Nessus® Essentials (formerly Nessus Home) allows you to scan your environment (up to 16 IP addresses per scanner) with the same high-speed, in-depth assessments and agentless scanning convenience that Nessus subscribers enjoy.”

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-40/slides/assets/12_0.png)
Source: Security-Database

</div>

</div>

NOTE:
Apart from these misconfigurations, when running a vulnerability assessment on your network you might find several security issues with a wide range of software and hardware including:
Default passwords on certain devices
Unnecessary services running on some devices
Running web services that contain known vulnerabilities
Dangerous applications such as peer-to-peer applications
Third-party applications that are a vulnerability to known exploits.

---

<!-- .element class="split-screen-with-title" -->
# Vulnerability Assessments

<div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-40/slides/assets/13_0.png)

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-40/slides/assets/13_1.png)
Source: Security-Database

</div>

</div>

---

<!-- .element class="main-title" -->
# Demo
