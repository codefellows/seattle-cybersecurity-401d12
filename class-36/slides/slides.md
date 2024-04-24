<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 36

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

- &shy;<!-- .element style="color: red;" -->**Class 36** - XSS with w3af, DVWA

<br>

- **Class 37** - Automated AppSec with OWASP ZAP

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

- &shy;<!-- .element style="color: red;" -->**Class 36** - Web App Fingerprinting Part 1 of 3

<br>

- **Class 37** - Web App Fingerprinting Part 2 of 3

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
# Ops Challenge: Banner Grabbing

---

<!-- .element class="split-screen-with-title" -->
# Banner Grabbing

<div>

<div>

- Computers love to talk!
  - We can use this to our advantage anytime we are snooping for vulnerabilities
  - **Banner grabbing** is a technique used by hackers and security teams to gain information about a computer system on a network and services running on its open ports

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-36/slides/assets/9_0.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Banner Grabbing

<div>

<div>

- The NetCat utility is a versatile UNIX tool that can interact with TCP, UDP, or UNIX-domain sockets
  - Open TCP connections
  - Send UDP packets
  - Listen on arbitrary TCP and UDP ports
  - Do port scanning
  - Supports both IPv4 and IPv6.
- Invoked in Linux with `nc`

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-36/slides/assets/9_0.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Ops Challenge Demo

---

<!-- .element class="main-title" -->
# Web Applications

---

<!-- .element class="split-screen-with-title" -->
# Web Applications

<div>

<div>

- Web applications are programs allowing better communication between businesses and their customers by way of a web browser interface
  - Frontend is usually created using languages like HTML, CSS, and Javascript supported by major browsers.
  - Backend uses a programming stack
    - LAMP, MEAN, etc.
  - Unlike mobile apps, there is no specific SDK for developing web applications

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-36/slides/assets/36_01.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Web Application Security

---

<!-- .element class="split-screen-with-title" -->
# Web Application Security

<div>

<div>

- Careers in web application security
  - Application Security Engineer
  - Web Application Pentester
  - Web Security Specialist

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-36/slides/assets/10_0.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# OWASP

---

<!-- .element class="split-screen-with-title" -->
# OWASP Top 10

<div>

<div>

- **Open Web Application Security Project® (OWASP)** is an international non-profit organization dedicated to web application security, most known for its list of top ten web application vulnerabilities.
- The **OWASP Top 10** is a regularly-updated report outlining security concerns for web application security including the 10 most critical risks
  - Extremely common in security interviews!
  - Memorize and be able to explain how they work

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-36/slides/assets/10_0.png)

</div>

</div>

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

---

<!-- .element class="main-title" -->
# Cross-Site Scripting

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

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-36/slides/assets/36_02.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Cross-Site Scripting

<div>

<div>

- **Reflected XSS**
  - malicious code is included in a URL or other input that is sent to the server and then reflected back to the user in response.
  - The attacker then tries to convince the user to click on the link
- **Stored XSS** - malicious code is stored on the server and then executed when the user views the affected page
- **DOM-Based XSS**
  - malicious code is executed on the client-side, instead of the server-side.
  - Happens when the client-side script takes input form the URL and then writes it directly to the page without proper sanitization


</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-36/slides/assets/36_03.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Web Security Dojo

<div>

<div>

- “**Web Security Dojo** is a free open-source self-contained training environment for Web Application Security penetration testing”
- For learning and practicing web app security testing techniques
- Self-teaching and skill assessment in self-contained environment
  - Tools, targets, and documentation.

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-36/slides/assets/11_0.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# DVWA

<div>

<div>

- **Damn Vulnerable Web App (DVWA)** is a web application deliberately designed for training purposes
  - DVWA comes preinstalled on Web Security Dojo
- W3AF is a Web Application Attack and Audit Framework
  - The project’s goal is to create a framework to help you secure your web applications by finding and exploiting all web application vulnerabilities
  - W3AF comes preinstalled on Web Security Dojo

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-36/slides/assets/12_0.png)
![Image](/ops-401-cybersecurity-guide/curriculum/class-36/slides/assets/13_0.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Demo
