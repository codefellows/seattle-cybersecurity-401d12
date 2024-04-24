<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 42

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

- &shy;<!-- .element style="color: red;" -->**Class 42** - Pass the Hash with Mimikatz

<br>

- **Class 43** - Traffic Sniffing with Ettercap

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

- &shy;<!-- .element style="color: red;" -->**Class 42** - Attack Tools Part 2 of 3

<br>

- **Class 43** - Attack Tools Part 3 of 3

<br>

- **Class 44** - Create a Port Scanner

<br>

- **Class 45** - Create a Banner Grabber

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/3_0.png)

---

<!-- .element class="main-title" -->
# Review: Lab & Challenge

---

<!-- .element class="split-screen-with-title" -->
# Phase 1: Plan & Recon

<div>

<div>

- Planning
  - How will we approach this pentest?
  - What does the client need from us?
    - Report deliverables
      - Offensive Security Pentest Report
- Scope of work
  - Rules of engagement dictate in clear, unambiguous terms the limits to the pentest engagement
    - Example: Allowed to access a system but not change it or damage it

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/18_0.png)
Source: Finsmes

</div>

</div>

NOTE:
Take a look at the sample pentest report and emphasize that pentesting isn't all about showing off your offensive security skills. It's mostly reporting; 80% of your time is spent writing reports. Share this link with class.

---

<!-- .element class="split-screen-with-title" -->
# Penetration Testing

<div>

<div>

- Pentest stages (Imperva version)
  - Phase 1: Planning & Reconnaissance
    - Define scope and goals of test
    - Gather intelligence on target
  - Phase 2: Scanning
    - How will a target application respond
      - Static analysis
      - Dynamic analysis
    - Enumeration

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/15_0.png)
Source: Cyberseek.org, Odiseageek, Hacker Web Security

</div>

</div>

NOTE:
Disclaimer: You'll see different variations on the stages of a pentest depending on who you ask.

---

<!-- .element class="split-screen-with-title" -->
# Penetration Testing

<div>

<div>

- Pentest stages (Imperva version ctd.)
  - Phase 3: Gaining Access
    - Social engineering
    - Web app attacks
  - Phase 4: Maintaining Access
    - Achieving persistence = APT
  - Phase 5: Analysis
    - Compile results of testing into reports
      - Vulnerabilities discovered and exploited
      - Sensitive data/systems accessed

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-41/slides/assets/16_0.png)
Source: Cyberseek.org, Odiseageek, Hacker Web Security

</div>

</div>

---

<!-- .element class="main-title" -->
# Linux Passwords

---

<!-- .element class="split-screen-with-title" -->
# Linux Passwords

<div>

<div>

- Security professionals should always know how popular operating systems store user credentials
- The /etc/passwd directory contains information necessary for user login
- cat /etc/passwd reveals the image here
  - Username
  - Password
  - User ID (UID)
  - Group ID (GID)
  - Information about User ID
  - Home directory
  - Command/shell

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/8_0.png)
Source: Linux Hint

</div>

</div>

NOTE:
“Username: Field one represents the user's name. The length of the username field is defined between 1-32 characters. This is used when a user logs in into the system. In the above example, ‘khuzdar' is the username.
Password: In the above example, the “x” character shows that password is stored in encrypted form in the /etc/shadow file.
User ID (UID): User ID must be separately assigned to each user. The UID zero is assigned to the root user, and User IDs from 1-99 are assigned to predefined or standard accounts. The further UIDs from 100-999 are assigned to system administrative accounts or groups. In the above screenshot, the user ID is 1001.
Group ID (GID): The next field represents the group ID. The GID is stored into /etc/group file. Based on the above example, the user belongs to the group id 1001.
Information about User ID: The following field is intended for comments. In this field, you can add some additional information about the specified user, such as the user's full name, phone number, etc. However, in the above example, no phone number is provided by the user.
Home directory: This field shows the location of the home directory that is assigned to the current user. If the specified directory does not exist, then it will display “/”. The above image shows the location of the highlighted user in the home directory, which is home/kbuzdar.
Command//shell: The default absolute path of a shell or command is /bin/bash. This is known as the shell. For example, sysadmin using the nologin shell. It behaves as the replacement shell for the system user accounts. If the shell is located at the path to /sbin/nologin and the user wants to log in directly to the Linux system, the /sbin/nologin shell will close or disable the connection.”

- Source: Linux Hint

---

<!-- .element class="main-title" -->
# Windows Passwords

---

<!-- .element class="split-screen-with-title" -->
# Windows Users

<div>

<div>

- Windows user privileges
  - Typically, user accounts can be assigned into the administrators group to receive those privileges. Remember RBAC?
  - Windows maintains a hidden Administrator account that is the final authority and has even higher privileges than a administrator-classed user

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/10_0.png)
Source: Sysnet

</div>

</div>

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
# NTLM

<div>

<div>

- NT (New Technology) LAN Manager (NTLM) uses a challenge-response protocol to avoid sending user passwords in plaintext
  - Released with Windows NT 4.0
  - NTLM credential
    - Domain name
    - User name
    - One-way hash of the user's password

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/12_0.png)
Source: StackExchange

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# SAM

<div>

<div>

- The Security Account Manager (SAM) is a database file in Windows that stores user passwords as NTLM Hashes
  - SAM registry entry located in registry hive HKEY_LOCAL_MACHINE
  - SAM file located in C:\Windows\System32\config
- SAM file targeted by hash dumping tools
  - Old logic: Who cares if my password hashes get stolen?
  - New logic: Rainbow tables

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/13_0.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/13_1.png)

</div>

</div>

---

<!-- .element class="image-and-text" -->
# Ophcrack

<div>

- Ophcrack (image below) is a Windows password cracking tool that can hash dump from encrypted SAM and attempt to crack the dumped hashes using rainbow tables

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/14_0.png)
Source: Sysnet

---

<!-- .element class="main-title" -->
# Kerberos

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

<!-- .element class="split-screen-with-title" -->
# Kerberos

<div>

<div>

- Components of the Kerberos workflow
  - Client
  - Server
  - Authentication Server (AS)
  - Key Distribution Center (KDC)
  - Ticket Granting Server (TGS)
- Secret keys used by Kerberos workflow
  - Client/user
  - TGS secret key
  - Server secret key

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/17_0.png)
Source: Hades Gamepedia

</div>

</div>

NOTE:
Kerberos Protocol Flow Overview
Let's take a more detailed look at what Kerberos authentication is and how it works by breaking it down into its core components.

Here are the principal entities involved in the typical Kerberos workflow:

- Client. The client acts on behalf of the user and initiates communication for a service request
- Server. The server hosts the service the user wants to access
- Authentication Server (AS). The AS performs the desired client authentication. If the authentication happens successfully, the AS issues the client a ticket called TGT (Ticket Granting Ticket). This ticket assures the other servers that the client is authenticated
- Key Distribution Center (KDC).
  - In a Kerberos environment, the authentication server logically separated into three parts:
    - A database (db)
    - the Authentication Server (AS)
    - the Ticket Granting Server (TGS)
  - These three parts, in turn, exist in a single server called the Key Distribution Center
- Ticket Granting Server (TGS). The TGS is an application server that issues service tickets as a service

Now let's break down the protocol flow.

First, there are three crucial secret keys involved in the Kerberos flow. There are unique secret keys for the client/user, the TGS, and the server shared with the AS.

- Client/user. Hash derived from the user's password
- TGS secret key. Hash of the password employed in determining the TGS
- Server secret key. Hash of the password used to determine the server providing the service.

---

<!-- .element class="split-screen-with-title" -->
# Kerberos

<div>

<div>

- Kerberos protocol flow:
  - Initial client authentication request
  - KDC verifies the client's credentials
  - The client decrypts the message
  - The client uses TGT to request access
  - The KDC creates a ticket for the file server
- Requires a domain controller
  - Must install Kerberos certificate software
  - Configuration

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/18_0.png)
Source: Hades Gamepedia

</div>

</div>

NOTE:
Step 1: Initial client authentication request. The user asks for a Ticket Granting Ticket (TGT) from the authentication server (AS). This request includes the client ID.

Step 2: KDC verifies the client's credentials. The AS checks the database for the client and TGS's availability. If the AS finds both values, it generates a client/user secret key, employing the user's password hash.

The AS then computes the TGS secret key and creates a session key (SK1) encrypted by the client/user secret key. The AS then generates a TGT containing the client ID, client network address, timestamp, lifetime, and SK1. The TGS secret key then encrypts the ticket.

Step 3: The client decrypts the message. The client uses the client/user secret key to decrypt the message and extract the SK1 and TGT, generating the authenticator that validates the client's TGS.

Step 4: The client uses TGT to request access. The client requests a ticket from the server offering the service by sending the extracted TGT and the created authenticator to TGS.

Step 5: The KDC creates a ticket for the file server. The TGS then uses the TGS secret key to decrypt the TGT received from the client and extracts the SK1. The TGS decrypts the authenticator and checks to see if it matches the client ID and client network address. The TGS also uses the extracted timestamp to make sure the TGT hasn't expired.

---

NOTE:

- Draw Kerberos process

---

<!-- .element class="main-title" -->
# Lateral Movement

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

<!-- .element class="split-screen-with-title" -->
# Pass the Hash

<div>

<div>

- Mimikatz is a post-exploitation tool used to perform lateral movement on Windows systems
- A pass the hash attack is a lateral movement technique where the password hash from one computer is used to authenticate into another
- Mimikatz exploits a vulnerability in the WDigest feature
  - Mimikatz goes into Windows' debugging mode and abuses a loophole using WDigest to authenticate into another computer

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/21_0.png)
Source: Sysnet

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# WDigest Vulnerability

- HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\SecurityProviders\WDigest
  - If the UseLogonCredential value is set to 0, WDigest will not store credentials in memory.
  - If the UseLogonCredential value is set to 1, WDigest will store credentials in memory.
- Value set to 1 = vulnerable

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/22_0.png)

Source: Sysnet

NOTE:
Source: Microsoft

---

<!-- .element class="split-screen-with-title" -->
# Mimikatz

<div>

<div>

- C:\Tools\mimikatz\x64\mimikatz.exe runs Mimikatz
- sekurlsa::logonPasswords
  - Dump passwords, NTLM tokens
- Mimikatz does not require a successful crack, but can pass the hash to another computer instead

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/23_0.png)

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Mimikatz

<div>

<div>

- What else can Mimikatz do?
  - Pass-the-Ticket
  - Over-Pass the Hash (Pass the Key)
  - Kerberos Golden Ticket
  - Kerberos Silver Ticket
  - Pass-the-Cache

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-42/slides/assets/24_0.png)

</div>

</div>

NOTE:

- “Pass-the-Hash: Windows used to store password data in an NTLM hash. Attackers use Mimikatz to pass that exact hash string to the target computer to login. Attackers don't even need to crack the password, they just need to use the hash string as is. It's the equivalent of finding the master key to a building on the floor. You need that one key to get into all the doors.

- Pass-the-Ticket: Newer versions of windows store password data in a construct called a ticket.  Mimikatz provides functionality for a user to pass a kerberos ticket to another computer and login with that user's ticket. It's basically the same as pass-the-hash otherwise.

Over-Pass the Hash (Pass the Key): Yet another flavor of the pass-the-hash, but this technique passes a unique key to impersonate a user you can obtain from a domain controller.

- Kerberos Golden Ticket: This is a pass-the-ticket attack, but it's a specific ticket for a hidden account called KRBTGT, which is the account that encrypts all of the other tickets. A golden ticket gives you domain admin credentials to any computer on the network that doesn't expire.

- Kerberos Silver Ticket: Another pass-the-ticket, but a silver ticket takes advantage of a feature in Windows that makes it easy for you to use services on the network. Kerberos grants a user a TGS ticket, and a user can use that ticket to log into any services on the network. Microsoft doesn't always check a TGS after it's issued, so it's easy to slip it past any safeguards.


- Pass-the-Cache: Finally an attack that doesn't take advantage of Windows! A pass-the-cache attack is generally the same as a pass-the-ticket, but this one uses the saved and encrypted login data on a Mac/UNIX/Linux system.” -Varonis

---

<!-- .element class="main-title" -->
# Demo
