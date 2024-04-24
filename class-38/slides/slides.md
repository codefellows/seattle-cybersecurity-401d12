<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 38

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

- &shy;<!-- .element style="color: red;" -->**Class 38** - Attacking Juice Shop with Burp Suite

<br>

- **Class 39** - SQLi with Burp Suite, Web Goat

<br>

- **Class 40** - N/A

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

- &shy;<!-- .element style="color: red;" -->**Class 38** - Web App Fingerprinting Part 3 of 3

<br>

- **Class 39** - Mock Interviews

<br>

- **Class 40** - Vulnerability Scanning with Nessus

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-32/slides/assets/2_0.png)<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="main-title" -->
# Review: Lab & Ops Challenge

---

<!-- .element class="split-screen-with-title" -->
# WebSocket

<div>

<div>

- WebSocket is a computer communications protocol, providing full-duplex communication channels over a single TCP connection
  - Enables interaction between web browser and web server over TCP 443 or 80
  - Separate protocol from HTTP but both on layer 7, reliant on TCP at layer 4.
  - All popular browsers support WebSocket

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/12_0.png)
Source: Wikipedia

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Exploration

<div>

<div>

- How do I use ZAP?
  - First, perform web app exploration procedures
    - The Traditional Spider (Crawler) discovers the HTML resources (hyperlinks etc) in the web application
    - The Ajax Spider works better if the application heavily relies with Ajax calls
    - Proxy Regression / Unit Tests are good for security regression testing
      - Use if you already have a test suite or unit tests in place
    - OpenAPI/SOAP Definition works if you have a well defined OpenAPI definition.

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/17_0.png)

</div>

</div>

NOTE:

- First, you should perform a web app exploration procedure with ZAP against the target so that you have more to test against ("enumeration" stage). Here are some methods you can use:
  - Traditional Spider (Crawler): Use this approach to crawl the HTML resources (hyperlinks etc) in the web application.
  - Ajax Spider: Use this feature if the application heavily relies with Ajax calls.
  - Proxy Regression / Unit Tests This is the recommended approach for security regression testing. Use this approach to explore the application, if you already have a test suite or unit tests in place.
  - OpenAPI/SOAP Definition: Use this approach if you have a well defined OpenAPI definition. The OpenAPI plugin can be downloaded via the marketplace.

---

<!-- .element class="main-title" -->
# OWASP Top Ten

---

<!-- .element class="split-screen-with-title" -->
# OWASP Top 10

<div>

<div>

- OWASP Top 10 Web Application Security Risks (November 2021)
  - Broken Access Control
  - Cryptographic Failures
  - Injection
  - Insecure Design
  - Security Misconfiguration
  - Vulnerable and Outdated Components
  - Identification and Authentication Failures
  - Software and Data Integrity Failures
  - Security Logging and Monitoring Failures
  - Server-Side Request Forgery (SSRF)

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-36/slides/assets/10_0.png)

</div>

</div>

NOTE:
<https://owasp.org/www-project-top-ten/>

We'll deep dive into a few of these this week. (Instructor reference below notes if questions asked)

Top 10 Web Application Security Risks

- A1:2021-Broken Access Control
  - Exploitation of Access Control
  - Lack of access control
  - Common because of lack of good functional testing

- A2:2021-Cryptographic Failures
  - Previously known as Sensitive Data Exposure
  - Sensitive Data like credit cards, tax IDs, and authentication credentials are not properly protected
  - Attackers can steal or modify sensitive data to do things like credit card fraud, identity theft, etc.

- A3:2021-Injection
  - Things like SQL, OS and LDAP injection
  - Untrusted data is sent to an interpreter as part of a command or query
  - Tricks the interpreter into executing unintended commands or accessing data without authorization

- A4:2021-Insecure Design
  - Focused on risks related to design and architectural flaws
  - Call of more use of threat modeling, secure design patterns, and reference architectures

- A5:2021-Security Misconfiguration
  - Missing appropriate security hardening
  - Improperly configured permissions
  - Default accounts and passwords

- A6:2021-Vulnerable and Outdated Components
  - Software is vulnerable, unsupported or out of date
  - Vulnerable dependencies, etc.

- A7:2021-Identification and Authentication Failures
  - Vulnerable to things like credential stuffing, brute force and other automated attacks
  - Uses plain text, encrypted or weakly hashed password data stores
  - No MFA

- A8:2021-Software and Data Integrity Failures
  - Focuses on software updates, critical data and CI/CD pipelines without verifying integrity
  - Think questionable or vulnerable plugins, libraries, or modules from untrusted sources, etc.
  - Auto update functionalities

- A9:2021-Security Logging & Monitoring Failures
  - Without logging and monitoring, breaches cannot be detected
  - No accountability, visibility, incident alerting and forensics

- A10:2021-Server-Side Request Forgery (SSRF)
  - Allows an attacker to make the server-side application to make HTTP requests to a domain of the attacker's choosing
  - For example, attacker might try to connect to an internal only services within the organization's infrastructure
  - Can result in unauthorized actions or access to data within the organization

---

<!-- .element class="split-screen-with-title" -->
# OWASP Top 10

- Changes from 2017 to 2021 editions

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/8_1.png)

---

<!-- .element class="split-screen-with-title" -->
# OWASP Top Ten

<div>

<div>

- What OWASP Top 10 concepts are needed for today's lab?
  - Injection
  - Broken authentication
  - Sensitive data exposure
  - Broken access control
  - XSS

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/9_0.png)
Source: OWASP

</div>

</div>

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

---

<!-- .element class="split-screen-with-title" -->
# OWASP Top Ten

<div>

<div>

- Broken authentication occurs when Application functions related to authentication and session management are implemented incorrectly
  - Attackers can compromise passwords, keys, or session tokens, or to exploit other implementation flaws to assume other users' identities (temporarily or permanently)
  - Session hijacking occurs when the attacker takes over a legitimate web session
    - Let's hijack John Smith's session

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/11_0.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/11_1.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/11_2.png)
Source: OWASP, Troy Hunt

</div>

</div>

NOTE:
In this example, John Smith is logging in normally to the web app. What if we capture John's cookie and reuse it in the URL in a different session? If the web app has broken authentication, it will let us into John's session.

---

<!-- .element class="split-screen-with-title" -->
# OWASP Top Ten

<div>

<div>

- Many web applications and APIs do not properly protect sensitive data, such as financial, healthcare, and PII, thus resulting in Sensitive data exposure.
  - Attackers may steal or modify such weakly-protected data to conduct credit card fraud, identity theft, or other crimes
  - Sensitive data may be compromised without extra protection, such as encryption at rest or in transit, and requires special precautions when exchanged with the browser

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/12_0.png)
Source: OWASP, Troy Hunt

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# OWASP Top Ten

<div>

<div>

- Broken access control occurs when restrictions on what authenticated users are allowed to do are often not properly enforced
  - Attackers can exploit these flaws to access unauthorized functionality and/or data, such as access other users' accounts, view sensitive files, modify other users' data, change access rights, etc.
  - Check your IAM fundamentals
    - Construct an access control matrix (ACM)

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/13_0.png)

</div>

</div>
---

<!-- .element class="split-screen-with-title" -->
# OWASP Top Ten

<div>

<div>

- Cross-Site Scripting (XSS) flaws occur whenever an application includes untrusted data in a new web page without proper validation or escaping, or updates an existing web page with user-supplied data using a browser API that can create HTML or JavaScript. XSS allows attackers to execute scripts in the victim's browser which can hijack user sessions, deface web sites, or redirect the user to malicious sites.

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/14_0.png)
Source: Blog, OWASP

</div>

</div>

---

<!-- .element class="main-title" -->
# Burp Suite

---

<!-- .element class="split-screen-with-title" -->
# Burp Suite

<div>

<div>

- Burp Suite is a popular commercial web application security tool
  - Pause HTTP requests using Burp Intercepter
  - Professional Edition
  - Community Edition
- Developed by Portswigger
  - Portswigger Academy is a free source of labs and appsec training

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/16_0.png)
Source: Hack Players

</div>

</div>

---

<!-- .element class="main-title" -->
# Juice Shop

---

<!-- .element class="split-screen-with-title" -->
# Juice Shop

<div>

<div>

- Juice Shop is an awareness, training, demonstration and exercise tool for security risks in modern web applications
  - Open-source project hosted by the non-profit Open Web Application Security Project® (OWASP) and is developed and maintained by volunteers
  - Hidden scoreboard tracks your progress
  - Book guides you towards the challenges
  - Built into Web Security Dojo but requires manual launch command

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/18_0.png)
Source: LinuxSecrets

</div>

</div>

NOTE:
Share the book link: <https://pwning.owasp-juice.shop/>

---

<!-- .element class="main-title" -->
# Demo
