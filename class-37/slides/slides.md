<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 37

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

Image source: BlogSpot
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

- &shy;<!-- .element style="color: red;" -->**Class 37** - Automated AppSec with OWASP ZAP

<br>

- **Class 38** - Attacking Juice Shop with Burp Suite

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

- &shy;<!-- .element style="color: red;" -->**Class 37** - Web App Fingerprinting Part 2 of 3

<br>

- **Class 38** - Web App Fingerprinting Part 3 of 3

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
# HTTP Cookies

- How do cookies work?

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/5_0.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/5_1.png)

Source: Ssup Blog

NOTE:

- Why should we study vulnerabilities as it relates to our entering the security field?
  - If I steal your cookie, I can buy whatever I want online and use YOUR identity, including your credit card and so forth
    - Profitable
  - Large companies that face constant cyber attacks use vulnerability assessments to proactively identify weaknesses in their defenses

---

<!-- .element class="split-screen-with-title" -->
# Cross-Site Scripting

<div>

<div>

- **Cross-site scripting (XSS)** vulnerabilities allow an attacker to inject malicious code into a web page viewed by other users.
- Usually happen when a web application fails to properly sanitize user input before displaying it on a web page
- The goal is to steal the other user’s identity data – cookies, session tokens, etc.
  - Cookies help us to login automatically.
  - Therefore with stolen cookies, the attacker can login with your identity.
  - This is one of the reasons, why this attack is considered as one of the riskiest attacks.

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/6_0.png)

---

<!-- .element class="main-title" -->
# AJAX & WebSocket

---

<!-- .element class="split-screen-with-title" -->
# AJAX

<div>

<div>

- What is AJAX?
  - AJAX, or Asynchronous JavaScript And XML, uses a combination of:
    - A browser built-in XMLHttpRequest object (to request data from a web server)
    - JavaScript and HTML DOM (to display or use the data)
  - Key features
    - Read data from a web server - after a web page has loaded
    - Update a web page without reloading the page
    - Send data to a web server - in the background

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/8_0.png)

</div>

</div>

NOTE:
What is AJAX?
AJAX = Asynchronous JavaScript And XML.

AJAX is not a programming language.

AJAX just uses a combination of:

A browser built-in XMLHttpRequest object (to request data from a web server)
JavaScript and HTML DOM (to display or use the data)

---

<!-- .element class="split-screen-with-title" -->
# AJAX

<div>

<div>

- How does AJAX work?
  - An event occurs in a web page (the page is loaded, a button is clicked)
  - An XMLHttpRequest object is created by JavaScript
  - The XMLHttpRequest object sends a request to a web server
  - The server processes the request
  - The server sends a response back to the web page
  - The response is read by JavaScript
  - Proper action (like page update) is performed by JavaScript

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/9_0.png)
Source: W3Schools

</div>

</div>

---

<!-- .element class="image-only" -->
# AJAX

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/10_0.png)
Source: W3Schools

NOTE:
The HTML page contains a <div> section and a <button>.

The <div> section is used to display information from a server.

The <button> calls a function (if it is clicked).

---

<!-- .element class="image-only" -->
# AJAX

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/11_0.png)
Source: W3Schools

NOTE:
The function requests data from a web server and displays it:

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

<!-- .element class="main-title" -->
# Zed Attack Proxy

---

<!-- .element class="split-screen-with-title" -->
# Zed Attack Proxy

<div>

<div>

- OWASP Zed Attack Proxy (ZAP) is a web application security test tool that acts as a MITM proxy.
  - Features include:
    - Intercepting Proxy
    - Active and Passive Scanners
    - Traditional and Ajax Spiders
    - Brute Force Scanner
    - Port Scanner
    - Web sockets

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/14_0.png)
Source: HackerWebSecurity

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Proxy Server

<div>

<div>

- Traditionally, a proxy server acts as a gateway between your PC and the internet.
  - A separate computer with its own IP.
  - Historically, on-prem enterprises used proxies to secure traffic into and out of the company LAN.
- We can setup ZAP as a "proxy" to Mozilla Firefox
  - All web traffic will be routed to and from ZAP, which will make the final decisions regarding when traffic will pass through

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/15_0.png)
Source: HackerWebSecurity

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Zed Attack Proxy

<div>

<div>

- Why use ZAP to perform web app security assessments?
  - Automated CI/CD testing via ZAP API
  - More "experimental" than the traditional go-to Burp
  - Free and open source flagship active OWASP project
  - No rate throttling brute force attacks; simpler to use, don't have to pass to Hydra
  - Automatic scanning
  - Drawbacks VS Burp
    - Less "mature"
    - Somewhat less popular

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/16_0.png)

</div>

</div>

NOTE:

- Why use OWASP ZAP to perform web app security assessments?
  - Automated CI/CD testing via ZAP API
  - More "experimental" than the traditional go-to Burp
  - Free and open source flagship active OWASP project
  - No rate throttling brute force attacks; simpler to use, don't have to pass to Hydra
  - Automatic scanning
- Drawbacks VS Burp
  - Less "mature" and tends to be more experimental/buggy
  - Somewhat less [popular](https://www.reddit.com/r/oscp/comments/jpp4m2/owasp_zap_vs_burp_suite/) but many people use **both** ZAP and Burp

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

<!-- .element class="split-screen-with-title" -->
# Performing Scans

<div>

<div>

- Next, scan for vulnerabilities
- In a passive scan, all requests proxied through ZAP or initialized by Spider are passively scanned
  - Passive scanning does not change or modify requests
- Active scans are attacks against the target URL.
  - View status
  - View results
  - Stop active scanning
- Getting results
  - Security vulnerabilities are displayed as alerts sorted by priority (risk)

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/18_0.png)
Source: Hamichlol

</div>

</div>

NOTE:
    - After the web app is explored, you're ready to scan for security vulnerabilities
      - Passive scan
        - All request proxied through ZAP or initialized by Spider are passively scanned (automatically scanned)
        - Passive scanning does not change or modify requests
      - Active scan
        - Active scans are attacks against the target URL.
      - View status
      - View results
      - Stop active scanning
        - Getting results
          - Security vulnerabilities are displayed as alerts sorted by priority (risk)

---

<!-- .element class="split-screen-with-title" -->
# Authenticated Scans

<div>

<div>

- ZAP is able to perform authenticated scans against the target
  - Form-based authentication
  - Script-based authentication
  - JSON-based authentication
  - HTTP/NTLM based authentication
- General steps
  - Step 1. Define a context
  - Step 2. Set the authentication mechanism
  - Step 3. Define your auth parameters
  - Step 4. Set relevant logged in/out indicators
  - Step 5. Add a valid user and password
  - Step 6. Enable forced user mode (Optional)

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-37/slides/assets/19_0.png)

</div>

</div>

NOTE:
      - Getting authenticated
        - Many web apps don't show all content to the general anonymous user. ZAP supports web app authentication to help facilitate in-depth scanning.
          - Form-based authentication
          - Script-based authentication
          - JSON-based authentication
          - HTTP/NTLM based authentication
        - General steps
          - Step 1. Define a context
          - Step 2. Set the authentication mechanism
          - Step 3. Define your auth parameters
          - Step 4. Set relevant logged in/out indicators
          - Step 5. Add a valid user and password
          - Step 6. Enable forced user mode (Optional)

---

<!-- .element class="main-title" -->
# Demo
