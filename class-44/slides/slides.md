<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 44

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

- **Module 8** - Web Application Security

- &shy;<!-- .element style="color: red;" -->**Module 9** - Penetration Testing

- **Module 10** - Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-29/slides/assets/0_01.png)
<!-- .element style="width: 100%"-->

</div>

</div>

---

<!-- .element class="title-with-text" -->
## Module 9 Labs

### Penetration Testing

<div align="left" style="font-size: 45px">

- **Class 41** - Reconnaissance with Maltego

<br>

- **Class 42** - Pass the Hash with Mimikatz

<br>

- **Class 43** - Traffic Sniffing with Ettercap

<br>

- &shy;<!-- .element style="color: red;" -->**Class 44** - Pentest Practice 1 of 2

<br>

- **Class 45** - Pentest Practice 2 of 2

</div>

---

<!-- .element class="split-screen-with-title" -->
## Module 9 Challenges

<div>

<div align="left" style="font-size: 35px">

- **Class 41** - Attack Tools Part 1 of 3

<br>

- **Class 42** - Attack Tools Part 2 of 3

<br>

- **Class 43** - Attack Tools Part 3 of 3

<br>

- &shy;<!-- .element style="color: red;" -->**Class 44** - Create a Port Scanner

<br>

- **Class 45** - Create a Banner Grabber

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/3_0.png)

---

<!-- .element class="main-title" -->
# Review: Lab & Ops Challenge

---

<!-- .element class="split-screen-with-title" -->
# HTTPS Decryption

<div>

<div>

- HTTPS (port 443)
  - Not considered vulnerable to MITM
  - If encryption key is obtained, checkmate!
- How can HTTPS keys be obtained?
  - Option 1: Session Keys Log file
    - Web browser must be configured to dump keys to a log file
    - Requires a foothold on the target PC
  - Option 2: Private Key of the Web Server

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-44/slides/assets/4_0.png)
Source: StackExchange

</div>

</div>

NOTE:
“Option 1: Session Keys Log file

You can decrypt HTTPS traffic in a quite simple way by using the Session Keys log file written by Firefox or other browsers. For that, the browser needs to be configured to dump those encryption keys to a log file, and you need to get that log file. And, to clarify: I'm talking about the web browser of the person you want to steal the password from. Now, if you're talking about decrypting your own HTTPS traffic, that strategy will work, e.g. following this tutorial.

If you're trying to decrypt HTTPS traffic of other users without valid access to their computers, it won't work. You'd have to steal their session key file from their hard drive (which is illegal, by the way) after reconfiguring their web browser to store the encryption keys to disk in the first place (unless they did that themselves, which is highly unlikely, and if they are, they're probably better at network captures than you are), and then somehow grab their traffic at a location you should most likely not have access to.

TL;DR: if you try to decrypt HTTPS sessions of other users, the session key log file method won't work for you.

Option 2: Private Key of the Web Server

The other option requires you to have access to the private key of the web server, which allows you to decrypt all connections to that server. Most security professionals reading the last sentence will now mutter something under their breath along the lines of “yeah, like THAT'S going to happen…” or “good luck with that…”.

Just to give you an idea how likely it is for you to get a hold on the private SSL/TLS encryption keys to the Facebook servers let me ask you one thing: can you get a copy of the original recipe for Coca Cola? No? Why not? Right – for the same reason why you won't get the private crypto keys from Facebook. They just don't want anyone to be able to decrypt ALL the traffic except for the parties involved, just like Coca Cola doesn't want you to have their most valuable secret.”
 -Blog

---

<!-- .element class="split-screen-with-title" -->
# DNS Cache Poisoning

<div>

<div>

- DNS cache poisoning is the act of entering false information into a DNS cache, so that DNS queries return an incorrect response and users are directed to the wrong websites
  - Incorrect DNS information remains in cache until the time to live (TTL) expires, or until it is removed manually

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/15_0.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/15_1.png)
Source: CloudFlare

</div>

</div>

NOTE:

- DO: Draw this out and explain, then quickly demonstrated a successfully poisoned victim PC ARP cache versus a healthy ARP cache

---

<!-- .element class="split-screen-with-title" -->
# ARP Poisoning

<div>

<div>

- Address resolution protocol (ARP) translates Internet Protocol (IP) addresses to a Media Access Control (MAC) address, and vice versa
  - Devices use ARP to contact the router or gateway for internet access
- In address resolution protocol (ARP) poisoning, also known as ARP spoofing, attacker changes a MAC address associated with the impersonated IP by altering targeted computer's ARP cache with a forged ARP request and reply message

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/16_0.png)
Source: BlogSpot

</div>

</div>

NOTE:

- DO: Draw this out and explain, then quickly demonstrated a successfully poisoned victim PC ARP cache versus a healthy ARP cache

---

<!-- .element class="main-title" -->
# Pentesting Tools

---

<!-- .element class="split-screen-with-title" -->
# OSCP

<div>

<div>

- Offensive Security Certified Practitioner (OSCP) is an industry certification offered by the creators of Kali Linux
  - Most popular offensive security certification recognized in the industry and demanded in job listings; think "the CISSP of pentesters"
  - 24-hour time limit
  - Hands-on penetration test
  - Isolated network
  - Points are awarded for each compromised host, based on host difficulty and level of access obtained

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-44/slides/assets/8_0.png)
Source: Hacktips

<div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# OpenVPN

<div>

<div>

- OpenVPN is the main client VPN software you'll use to connect to pentesting networks.
- Pentesting traffic MUST be constrained to encrypted VPN connections - Keep yourself out of trouble!
- Server Message Block (SMB) is typically used with NetBIOS over TCP/IP over UDP ports 137, 138 or TCP 137, 139
  - Version 1, 2, and 3
  - Multiple versions selectable in Windows 10 but legacy SMB disabled by default, e.g. SMBv1

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-44/slides/assets/9_0.png)
Source: DigitalOcean

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# OpenVPN

<div>

<div>

- NetBIOS is a legacy small network protocol
  - Name service for name registration and resolution (ports: 137/udp and 137/tcp)
  - Datagram distribution service for connectionless communication (port: 138/udp)
  - Session service for connection-oriented communication (port: 139/tcp)

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-44/slides/assets/10_0.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-44/slides/assets/10_1.png)
Source: Wikipedia, Wiki

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Noise Simulation

<div>

<div>

- What can I do to simulate "noisy" attacks on a network? How do I know if I'm being discreet?
  - This is where you'll need to bring concepts together from earlier in the course
  - Setup threat detection controls on a lab environment to look for your attacks
  - Watch SIEM, IDS while you perform noisy attacks, and you'll observe alerts

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-44/slides/assets/11_0.png)
Source: Suricata

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Autorecon

<div>

<div>

- Autorecon is a custom scanner tool designed to save you precious time during the enumeration phase of pentesting
  - If noise is not a concern, use it to expedite CTFs or noisy pentests
  - Probably not a great idea if you're trying to be discreet
- Is Autorecon allowed on the OSCP?
  - Yes! Automated enumeration tools are allowed
  - Automated exploit tools, however, are NOT allowed

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-44/slides/assets/12_0.png)
Source: GitHub

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Remmina

<div>

<div>

- Remmina is a software that allows Linux systems to utilize Microsoft Remote Desktop Protocol (RDP) out to other systems
  - Similar tools include VNC, etc.
- Use Remmina if you need to RDP from a Linux box to a Windows box during the final project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-44/slides/assets/13_0.png)
Source: TecMint

</div>

</div>

---

<!-- .element class="main-title" -->
# Demo
