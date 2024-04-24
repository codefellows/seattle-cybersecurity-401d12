<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 43

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

- &shy;<!-- .element style="color: red;" -->**Class 43** - Traffic Sniffing with Ettercap

<br>

- **Class 44** - Pentest Practice 1 of 2

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

- &shy;<!-- .element style="color: red;" -->**Class 43** - Attack Tools Part 3 of 3

<br>

- **Class 44** - Create a Port Scanner

<br>

- **Class 45** - Create a Banner Grabber

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/3_0.png)

---

<!-- .element class="main-title" -->
# Review: Lab & Ops Challenge

---

<!-- .element class="split-screen-with-title" -->
# Windows Authentication

<div>

<div>

- Windows authenticates its users via Local Security Authority (LSA) which performs a negotiation process during authentication
  - Out of the box, LSA will use NTLM
  - If DC is properly configured, LSA prefers to use Kerberos when available

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/11_0.png)
Source: StackExchange

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Kerberos

<div>

<div>

- Windows prefers to use Kerberos when it's available for authentication processes.
- Originally developed by MIT in the late 80s, Kerberos is a computer network security protocol that authenticates service requests between two or more trusted hosts across an untrusted network
  - Uses secret-key cryptography and a trusted third party for authenticating client-server applications and verifying users' identities.

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/16_0.png)
Source: Hades Gamepedia

</div>

</div>

---

---

<!-- .element class="split-screen-with-title" -->
# Lateral Movement

<div>

<div>

- TA0008: Lateral Movement is a post-exploitation tactic used to maneuver deeper into a network in search of sensitive data or high-value assets
  - In T1550: Use Alternate Authentication Material, adversaries use alternate authentication material, such as password hashes, Kerberos tickets, and application access tokens, in order to move laterally within an environment

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/20_0.png)
Source: Fire Eye

</div>

</div>

---

<!-- .element class="main-title" -->
# Traffic Sniffing with Ettercap

---

<!-- .element class="split-screen-with-title" -->
# Traffic Sniffing

<div>

<div>

- Man-in-the-middle attacks occur when the adversary positions themselves between multiple network devices to perform either network sniffing or transmitted data manipulation
  - MITRE ATT&CK technique T1557, under tactic Credential Access
  - Abuses common networking protocols that facilitate network traffic flow
  - Can be used to deny traffic, resulting in a denial of service attack

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/8_0.png)
Source: Tutorialspoint

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Traffic Sniffing

<div>

<div>

- Goals
  - Information gathering
  - Ideal - Gather admin credentials
- Sniffing is the process of monitoring and capturing all the packets passing through a network using tools
  - In passive sniffing traffic is observed but not altered
  - In active sniffing traffic may also be altered to suit the attack technique
- Difference: Hub vs switch?
  - Collision domains determine what ports can see your traffic

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/9_0.png)
Source: Tutorialspoint

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Vulnerable Protocols

<div>

<div>

- Vulnerable protocols
  - HTTP (port 80)
    - Hypertext transfer protocol is used at layer 7 of the OSI model and lacks encryption to ensure confidentiality
    - HTTPS (port 443) instead encrypts traffic as it leaves layer 7
  - TELNET (port 23)
    - Unencrypted predecessor to SSH

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/10_0.png)
Source: Greyshell

</div>

</div>

NOTE:
“Protocols vulnerable to sniffing attacks

As we are aware that the network follows a layered approach, each layer has a dedicated task that the next layer adds up to it. Till now we have not discussed that on what layer sniffing attacks happen. Sniffing attacks work on various layers depending on the motive of the attack. Sniffers can capture the PDU's from various layers but layer 3 (Network) and 7 (Application) are of key importance. Out of all the protocols, some are susceptible to sniffing attacks. Secured version of protocols are also available but if some systems are still using the unsecured versions then the risk of information leakage becomes considerable. Let's discuss some of the protocols that are vulnerable to sniffing attacks.

1) HTTP:
Hypertext transfer protocol is used at layer 7 of the OSI model. This is an application layer protocol that transmits the information in plain text. This was fine, when there were static websites or websites that did not required any input from the user. Anyone can set up a MITM proxy in between and listen to all the traffic or modify that traffic for personal gains. Now when we have entered into the web 2.O world, we need to ensure that the user's interaction is secured. This is ensured by using the secured version of HTTP i.e. HTTPS. Using https, the traffic is encrypted as soon as it leaves layer 7.

2) TELNET:
Telnet is a client-server protocol that provides communication facility through virtual terminal. Telnet does not encrypt the traffic by default. Anyone having access to a switch or hub that connects the client and the server can sniff the telnet traffic for username and password. SSH is used as an alternate to the unsecured telnet. SSH uses cryptography to encrypt the traffic and provides confidentiality and integrity to the traffic.

3) FTP:
FTP is used to transfer files between client and server. For authentication FTP used plain text username and password mechanism. Like telnet, an attacker can sniff the traffic to gain credentials and access all the files on the server. FTP can be secured by sung SSL/TLS or can be replaced by a more secured version called SFTP (SSH file transfer protocol).

4) POP:
It stands for Post office protocol and is used by email clients to download the emails form the mail server. It also used plain text mechanism for communication hence it is also vulnerable to sniffing attacks. POP is followed by POP2 and POP3 which are little bit more secure than the original version.

5) SNMP:
Simple network management protocol is used for communication with managed network devices on the network. SNMP uses various messages for communication and community strings for performing client authentication. Community strings in effect are just like password that is transmitted in clear text. SNMP has been superseded by SNMPV2 and V3, v3 being the latest and most secure.” -GreyCampus

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

![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/10_0.png)
Source: Greyshell

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

<!-- .element class="text-only" -->
# Vulnerable Protocols

- Vulnerable protocols (ctd.)
  - FTP
    - TCP port 20, 21
    - Plaintext username and password authentication
    - Unencrypted data in motion
    - Securable using SSL/TLS or its successor, SSH file transfer protocol (SFPT)

NOTE:
“Protocols vulnerable to sniffing attacks

As we are aware that the network follows a layered approach, each layer has a dedicated task that the next layer adds up to it. Till now we have not discussed that on what layer sniffing attacks happen. Sniffing attacks work on various layers depending on the motive of the attack. Sniffers can capture the PDU's from various layers but layer 3 (Network) and 7 (Application) are of key importance. Out of all the protocols, some are susceptible to sniffing attacks. Secured version of protocols are also available but if some systems are still using the unsecured versions then the risk of information leakage becomes considerable. Let's discuss some of the protocols that are vulnerable to sniffing attacks.

1) HTTP:
Hypertext transfer protocol is used at layer 7 of the OSI model. This is an application layer protocol that transmits the information in plain text. This was fine, when there were static websites or websites that did not required any input from the user. Anyone can set up a MITM proxy in between and listen to all the traffic or modify that traffic for personal gains. Now when we have entered into the web 2.O world, we need to ensure that the user's interaction is secured. This is ensured by using the secured version of HTTP i.e. HTTPS. Using https, the traffic is encrypted as soon as it leaves layer 7.

1) TELNET:
Telnet is a client-server protocol that provides communication facility through virtual terminal. Telnet does not encrypt the traffic by default. Anyone having access to a switch or hub that connects the client and the server can sniff the telnet traffic for username and password. SSH is used as an alternate to the unsecured telnet. SSH uses cryptography to encrypt the traffic and provides confidentiality and integrity to the traffic.

1) FTP:
FTP is used to transfer files between client and server. For authentication FTP used plain text username and password mechanism. Like telnet, an attacker can sniff the traffic to gain credentials and access all the files on the server. FTP can be secured by sung SSL/TLS or can be replaced by a more secured version called SFTP (SSH file transfer protocol).

1) POP:
It stands for Post office protocol and is used by email clients to download the emails form the mail server. It also used plain text mechanism for communication hence it is also vulnerable to sniffing attacks. POP is followed by POP2 and POP3 which are little bit more secure than the original version.

1) SNMP:
Simple network management protocol is used for communication with managed network devices on the network. SNMP uses various messages for communication and community strings for performing client authentication. Community strings in effect are just like password that is transmitted in clear text. SNMP has been superseded by SNMPV2 and V3, v3 being the latest and most secure.” -GreyCampus

---

<!-- .element class="split-screen-with-title" -->
# Vulnerable Protocols

<div>

<div>

- Vulnerable protocols (ctd.)
  - POP
    - TCP port 110
    - Post office protocol uses plaintext communications
    - Succeeded by POP2 and POP3 which introduce additional security

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/13_0.png)
Source: Wikimedia

</div>

</div>

NOTE:
“Protocols vulnerable to sniffing attacks

As we are aware that the network follows a layered approach, each layer has a dedicated task that the next layer adds up to it. Till now we have not discussed that on what layer sniffing attacks happen. Sniffing attacks work on various layers depending on the motive of the attack. Sniffers can capture the PDU's from various layers but layer 3 (Network) and 7 (Application) are of key importance. Out of all the protocols, some are susceptible to sniffing attacks. Secured version of protocols are also available but if some systems are still using the unsecured versions then the risk of information leakage becomes considerable. Let's discuss some of the protocols that are vulnerable to sniffing attacks.

1) HTTP:
Hypertext transfer protocol is used at layer 7 of the OSI model. This is an application layer protocol that transmits the information in plain text. This was fine, when there were static websites or websites that did not required any input from the user. Anyone can set up a MITM proxy in between and listen to all the traffic or modify that traffic for personal gains. Now when we have entered into the web 2.O world, we need to ensure that the user's interaction is secured. This is ensured by using the secured version of HTTP i.e. HTTPS. Using https, the traffic is encrypted as soon as it leaves layer 7.

2) TELNET:
Telnet is a client-server protocol that provides communication facility through virtual terminal. Telnet does not encrypt the traffic by default. Anyone having access to a switch or hub that connects the client and the server can sniff the telnet traffic for username and password. SSH is used as an alternate to the unsecured telnet. SSH uses cryptography to encrypt the traffic and provides confidentiality and integrity to the traffic.

3) FTP:
FTP is used to transfer files between client and server. For authentication FTP used plain text username and password mechanism. Like telnet, an attacker can sniff the traffic to gain credentials and access all the files on the server. FTP can be secured by sung SSL/TLS or can be replaced by a more secured version called SFTP (SSH file transfer protocol).

4) POP:
It stands for Post office protocol and is used by email clients to download the emails form the mail server. It also used plain text mechanism for communication hence it is also vulnerable to sniffing attacks. POP is followed by POP2 and POP3 which are little bit more secure than the original version.

5) SNMP:
Simple network management protocol is used for communication with managed network devices on the network. SNMP uses various messages for communication and community strings for performing client authentication. Community strings in effect are just like password that is transmitted in clear text. SNMP has been superseded by SNMPV2 and V3, v3 being the latest and most secure.” -GreyCampus

---

<!-- .element class="split-screen-with-title" -->
# Vulnerable Protocols

<div>

<div>

- Vulnerable protocols (ctd.)
  - SNMP (UDP ports 161, 162)
    - Simple network management protocol is used for managing network devices
    - Traps are used to capture SNMP communications
    - SNMPv1 uses community strings for performing client authentication which act as passwords sent in plaintext
    - Use the latest version, SNMPv3, for encryption

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/14_0.png)
Source: Wikipedia

</div>

</div>

NOTE:
“Protocols vulnerable to sniffing attacks

As we are aware that the network follows a layered approach, each layer has a dedicated task that the next layer adds up to it. Till now we have not discussed that on what layer sniffing attacks happen. Sniffing attacks work on various layers depending on the motive of the attack. Sniffers can capture the PDU's from various layers but layer 3 (Network) and 7 (Application) are of key importance. Out of all the protocols, some are susceptible to sniffing attacks. Secured version of protocols are also available but if some systems are still using the unsecured versions then the risk of information leakage becomes considerable. Let's discuss some of the protocols that are vulnerable to sniffing attacks.

1) HTTP:
Hypertext transfer protocol is used at layer 7 of the OSI model. This is an application layer protocol that transmits the information in plain text. This was fine, when there were static websites or websites that did not required any input from the user. Anyone can set up a MITM proxy in between and listen to all the traffic or modify that traffic for personal gains. Now when we have entered into the web 2.O world, we need to ensure that the user's interaction is secured. This is ensured by using the secured version of HTTP i.e. HTTPS. Using https, the traffic is encrypted as soon as it leaves layer 7.

2) TELNET:
Telnet is a client-server protocol that provides communication facility through virtual terminal. Telnet does not encrypt the traffic by default. Anyone having access to a switch or hub that connects the client and the server can sniff the telnet traffic for username and password. SSH is used as an alternate to the unsecured telnet. SSH uses cryptography to encrypt the traffic and provides confidentiality and integrity to the traffic.

3) FTP:
FTP is used to transfer files between client and server. For authentication FTP used plain text username and password mechanism. Like telnet, an attacker can sniff the traffic to gain credentials and access all the files on the server. FTP can be secured by sung SSL/TLS or can be replaced by a more secured version called SFTP (SSH file transfer protocol).

4) POP:
It stands for Post office protocol and is used by email clients to download the emails form the mail server. It also used plain text mechanism for communication hence it is also vulnerable to sniffing attacks. POP is followed by POP2 and POP3 which are little bit more secure than the original version.

5) SNMP:
Simple network management protocol is used for communication with managed network devices on the network. SNMP uses various messages for communication and community strings for performing client authentication. Community strings in effect are just like password that is transmitted in clear text. SNMP has been superseded by SNMPV2 and V3, v3 being the latest and most secure.” -GreyCampus

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

<!-- .element class="split-screen-with-title" -->
# ARP Poisoning

- Example of a successful ARP poisoning attack:
  - Addresses

    ![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/17_1.png)

  - Before

    ![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/17_2.png)

  - After

    ![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/17_0.png)

    Source: OpenManiak

</div>

</div>

NOTE:

- DO: Draw this out and explain, then quickly demonstrated a successfully poisoned victim PC ARP cache versus a healthy ARP cache

---

<!-- .element class="split-screen-with-title" -->
# Ettercap

<div>

<div>

- Ettercap is a comprehensive toolkit for man-in-the-middle attacks
  - Sniffing of live connections
  - Content filtering
  - Active & passive protocol dissection
  - Network and host analysis capabilities
- Sniffing tool has two modes:
  - In unified mode (default), Sniffs packets that pass through a single interface
  - In bridged mode, it uses two network interfaces and forward the traffic from one to the other while performing sniffing and content filtering

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-43/slides/assets/18_0.png)
Source: Charles Reid

</div>

</div>

NOTE:
    - UNIFIED (default) Sniffs packets that pass through a single interface.
    - BRIDGED, it uses two network interfaces and forward the traffic from one to the other while performing sniffing and content filtering. This sniffing method is totally stealthy since there is no way to find that someone is in the middle on the cable. You can look at this method as a mitm attack at layer 1. You will be in the middle of the cable between two entities.

---

<!-- .element class="main-title" -->
# Demo
