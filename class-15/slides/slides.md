<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 15

NOTE:
This slide deck is used to introduce the day's class in the context of the overall course. Use this deck to facilitate the daily discussion of what we did yesterday, what we're about to do today, and what we'll be doing in the next class.

---

<!-- .element class="title-and-subtitle" -->
# Agenda

## Class 15 - Career Coaching Workshop 3

- CCW3 <!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->
- Review
  - Intrusion Detection and Prevention Systems
- Lecture
  - Brute Force Attacks
- Ops Challenge Demo

---

<!-- .element class="split-screen-with-title" -->
## Course Overview: Modules

<div>

<div align="left" style="font-size: 40px">

- **Module 1** - Governance, Risk and Compliance (GRC)

- **Module 2** - Data Security

- &shy;<!-- .element: class="fragment highlight-current-red" data-fragment-index="1" -->**Module 3** - Security Operations

- **Module 4** - Cloud Security

- **Module 5** - Midterm Project

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/00_01.png)
<!-- .element style="width: 100%"-->
Source: [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Kali-dragon-icon.svg)

</div>

</div>

---

<!-- .element class="title-with-text" -->
# Module 3 Labs

### Security Operations

<div align="left" style="font-size: 45px">

- **Class 11** - Foundational SIEM Operations

<br>

- **Class 12** - Log Analysis with Splunk

<br>

- **Class 13** - Reconstructing a Cloud Attack

<br>

- **Class 14** - Intrusion Detection

<br>

- &shy;<!-- .element style="color: red;" -->**Class 15** - CCW3: Networking

</div>

---

<!-- .element class="split-screen-with-title" -->
# Module 3 Challenges

<div>

<div align="left" style="font-size: 38px">

- **Class 11** - Network Security Tool Pt. 1 of 3

<br>

- **Class 12** - Network Security Tool Pt. 2 of 3

<br>

- **Class 13** - Network Security Tool Pt. 3 of 3

<br>

- **Class 14** - Mock Interviews

<br>

- &shy;<!-- .element style="color: red;" -->**Class 15** - Brute Force Attacks

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/00_02.png)

</div>

</div>

---

<!-- .element class="main-title" -->
# Review:

## Intrusion Detection

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What's the purpose of an IDS?**
  - Detect and prevent intrusions in real time on a network <!-- .element: class="fragment" data-fragment-index="2" -->
  - Allows defenders to customize defensive detection rules <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**When should an IDS be deployed?**
  - Private networks with high value assets <!-- .element: class="fragment" data-fragment-index="5" -->
  - Adequate SecOps coverage to configure rules and respond to IDS alerts <!-- .element: class="fragment" data-fragment-index="6" -->

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/14_02.png)

NOTE:

- Why use IDS, IPS, or HIDS?
  - Detect and/or prevent intrusions in real time on a network
  - Allows defenders to customize defensive detection rules

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is a host-based intrusion detection system (HIDS)?**
  - An IDS capable of monitoring and analyzing the internals of a computing system as well as the network packets on its network interfaces.
  - Ideally deployed in conjunction with a NIDS to capture traffic that slipped past the NIDS <!-- .element: class="fragment" data-fragment-index="2" -->
  - Example Product: OSSEC <!-- .element: class="fragment" data-fragment-index="3" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/14_05.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/14_06.png)

</div>

</div>

NOTE:

- What is HIDS?
  - A host-based intrusion detection system (HIDS) is an IDS capable of monitoring and analyzing the internals of a computing system as well as the network packets on its network interfaces.
  - Ideally deployed in conjunction with a NIDS to capture traffic that slipped past the NIDS
  - Example: OSSEC
    - Open source HIDS
    - Log-based IDS
    - Rootkit and malware detection
    - Active response
    - Compliance auditing
    - File integrity monitoring
    - System inventory
  - https://www.ossec.net/

---

<!-- .element class="split-screen-with-title" -->
# Intrusion Detection

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**How does Snort work?**
  - Detects network baseline traffic <!-- .element: class="fragment" data-fragment-index="2" -->
  - Uses rules to detect network anomalies <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**Network topology**
  - Snort requires a span port (traffic mirroring) for its sniffer interface <!-- .element: class="fragment" data-fragment-index="5" -->
  - PfSense supports traffic mirroring, as implemented in Ops 301 <!-- .element: class="fragment" data-fragment-index="6" -->
  - Keep this lab long term as a threat detection ecosystem for learning <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/14_07.png)

---

<!-- .element class="main-title" -->
# Brute Force Attacks

---

<!-- .element class="title-and-subtitle" -->
# Agenda

- Today we'll be discussing: <!-- .element: class="fragment" data-fragment-index="1" -->
  - Rainbow Tables <!-- .element: class="fragment" data-fragment-index="2" -->
  - Salt <!-- .element: class="fragment" data-fragment-index="3" -->
  - Dictionaries <!-- .element: class="fragment" data-fragment-index="4" -->
  - Social media fails <!-- .element: class="fragment" data-fragment-index="5" -->
  - Hydra <!-- .element: class="fragment" data-fragment-index="6" -->
  - Medusa <!-- .element: class="fragment" data-fragment-index="7" -->

---

<!-- .element class="split-screen-with-title" -->
# Password Files

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Password files** in operating systems store username in plaintext and password as its derived hash value
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Hash dumping** is the act of exfiltrating the hash values and their usernames

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/15_01.png)

Source: Bowne Consultant

---

<!-- .element class="split-screen-with-title" -->
# Brute Force Attacks

<div>

<div>

- Brute force attacks attempt to guess the correct password using automated, repeated authentication attempts <!-- .element: class="fragment" data-fragment-index="1" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Online**
    - Slow <!-- .element: class="fragment" data-fragment-index="3" -->
    - Accounts will lock you out <!-- .element: class="fragment" data-fragment-index="4" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Offline**
    - Obtain list of users and hashes <!-- .element: class="fragment" data-fragment-index="6" -->
    - Determine a password hash and compare to stored hash <!-- .element: class="fragment" data-fragment-index="7" -->
    - Raw computer horsepower <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/15_02.png)
Source: Timetoast

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Rainbow Tables

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is a rainbow table?**
  - A precomputed dictionary of plaintext passwords and their corresponding hash values
  - Can be used to find out what plaintext password produces a particular hash <!-- .element: class="fragment" data-fragment-index="2" -->
  - Much faster to query <!-- .element: class="fragment" data-fragment-index="3" -->
  - Hashing methods determine table type <!-- .element: class="fragment" data-fragment-index="4" -->
  - Don't work on “salted” hashes <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/15_03.png)
Source: Wikipedia - Rainbow Table

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Salting

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is Salting?**
  - Salting is a cryptographic technique that protects passwords against rainbow tables by adding random characters to the plaintext prior to hashing. <!-- .element: class="fragment" data-fragment-index="2" -->
  - Generates a totally different hash <!-- .element: class="fragment" data-fragment-index="3" -->
  - Each user should have a unique salt value <!-- .element: class="fragment" data-fragment-index="4" -->
  - Salt is generated by a cryptographically secure pseudo-random number generator <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/15_04.png)
Source: Guiding Tech

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Dictionary Attacks

<div>

<div>

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**What is a dictionary attack?**
  - A type of brute force attack where an intruder attempts to crack a password-protected security system with a “dictionary list” of common words and phrases <!-- .element: class="fragment" data-fragment-index="2" -->
  - Increase odds of success by playing towards human tendencies in password creation <!-- .element: class="fragment" data-fragment-index="3" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/15_05.png)
Source: The Guardian

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Password Lists

<div>

<div>

- Password lists are data samples <!-- .element: class="fragment" data-fragment-index="1" -->
- Data samples facilitate AI automation <!-- .element: class="fragment" data-fragment-index="2" -->
- Better more complete data samples = Better AI <!-- .element: class="fragment" data-fragment-index="3" -->
- &shy;<!-- .element: class="fragment" data-fragment-index="4" -->**RockYou**
  - Founded in 2005 <!-- .element: class="fragment" data-fragment-index="5" -->
  - Data breach in December 2009 resulted in 32 million user accounts exposed <!-- .element: class="fragment" data-fragment-index="6" -->
    - Plaintext passwords <!-- .element: class="fragment" data-fragment-index="7" -->
    - Use of special characters disallowed <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/15_06.png)

</div>

</div>

NOTE:
- What is RockYou password list? Ref. [Wikipedia](https://en.wikipedia.org/wiki/RockYou)
  - Once upon a time in 2005, a company called RockYou was founded that built widgets for social media pages.
  - "Data breach: In December 2009, the company experienced a data breach resulting in the exposure of over 32 million user accounts. The company used an unencrypted database to store user account data, including plaintext passwords (as opposed to password hashes) for its service, as well as passwords to connected accounts at partner sites (including Facebook, Myspace, and webmail services). RockYou would also e-mail the password unencrypted to the user during account recovery. They also did not allow using special characters in the passwords. The hackers used a 10-year-old SQL vulnerability to gain access to the database. The company took days to notify users after the incident, and initially incorrectly reported that the breach only affected older applications when it actually affected all RockYou users."
  - Their loss is our gain! Now we have access to a VERY useful password list in rockyou.txt.

---

<!-- .element class="split-screen-with-title" -->
# Password Lists

<div>

<div>

- Get me some lists! <!-- .element: class="fragment" data-fragment-index="1" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="2" -->**Kali Linux word lists repo**
    - Pre-installed on Kali <!-- .element: class="fragment" data-fragment-index="3" -->
    - `/usr/share/wordlist/` <!-- .element: class="fragment" data-fragment-index="4" -->
  - &shy;<!-- .element: class="fragment" data-fragment-index="5" -->**Daniel Miessler's SecLists**
    - Study resources for beginners <!-- .element: class="fragment" data-fragment-index="6" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/15_07.png)

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/15_08.png)

</div>

</div>

NOTE:
https://gitlab.com/kalilinux/packages/wordlists
https://github.com/danielmiessler/SecLists
Also, link students to his tutorial blogs https://danielmiessler.com/study/

---

<!-- .element class="split-screen-with-title" -->
# THC Hydra

<div>

<div>

- THC Hydra is a rapid online password cracking tool capable of targeting over 50 remote authentication protocols and supports the use of password lists <!-- .element: class="fragment" data-fragment-index="1" -->
  - Command line only <!-- .element: class="fragment" data-fragment-index="2" -->
  - Included in Kali Linux <!-- .element: class="fragment" data-fragment-index="3" -->
  - Tool repo <!-- .element: class="fragment" data-fragment-index="4" -->
  - Cheat sheet <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/15_09.png)

</div>

</div>

NOTE:
https://github.com/vanhauser-thc/thc-hydra
https://noxtal.com/cheatsheets/2020/07/24/hydra-cheatsheet/

---

<!-- .element class="split-screen-with-title" -->
# THC Hydra

<div>

<div>

# Syntax

`hydra [OPTIONS] IP`

# Useful flags

- `-h`: see the help menu
- `-l` <LOGIN>: Pass single username/login
- `-L` <FILE>: Pass multiple usernames/logins
- `-p` <LOGIN>: Pass single known password
- `-P` <FILE>: Pass a password list or wordlist (ex.: rockyou.txt)
- `-s` <PORT>: Use custom port
- `-f`: Exit as soon as at least one a login and a password combination is found
- `-R`: Restore previous session (if crashed/aborted)

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-15/slides/assets/15_09.png)
Source: Hydra Cheat Sheet

</div>

</div>

NOTE:
https://github.com/vanhauser-thc/thc-hydra
https://noxtal.com/cheatsheets/2020/07/24/hydra-cheatsheet/

---

<!-- .element class="text-only" -->
# THC Hydra

- &shy;<!-- .element: class="fragment" data-fragment-index="1" -->**Example: Bruteforce SSH credentials**

  `hydra -f -l user -P /usr/share/wordlists/rockyou.txt $IP -t 4 ssh` <!-- .element: class="fragment" data-fragment-index="2" -->

- &shy;<!-- .element: class="fragment" data-fragment-index="3" -->**Example: Bruteforce RDP**

  `hydra -f -l administrator -P /usr/share/wordlists/rockyou.txt rdp://$IP` <!-- .element: class="fragment" data-fragment-index="4" -->

NOTE:

https://github.com/vanhauser-thc/thc-hydra
https://noxtal.com/cheatsheets/2020/07/24/hydra-cheatsheet/

---

<!-- .element class="main-title" -->
# Demo

NOTE:

- Show students how to set a hilariously weak password in their target SSH server.
  - Create a profile in the Ubuntu "users" panel.
  - In command line use sudo passwd [username] to set a terrible password.
  - Show hydra brute force attack.

    `hydra -t 10 -V -f -l ubuntu -x 6:6:a ssh://192.168.0.237`

  - This will take a while! Next, show where rockyou.txt is stored in Kali.

    `cd /usr/share/wordlist/`

  - Unzip it first.

    `sudo gzip -d /usr/share/wordlists/rockyou.txt.gz`

  - Now you should have a rockyou.txt file ready to go. Take a peek inside!

    `vim rockyou.txt`

  - Pass rockyou.txt into Hydra and perform a dictionary attack.

    `hydra -t 4 -V -f -l notahacker -P rockyou.txt ssh://192.168.0.237`

- From ref:
  - `-t 4` - This sets the number of tasks that can run parallel together in this example I have used 4 which will send 4 logins at a time. RDP does not like too many connections at the same time so try and keep it at a maximum of 4. It is sometimes worth adding a -w to your command to add a wait between attempts.
  - `-V` - Verbose this shows you which usernames and passwords on screen as it’s working.
  - `-f` - Quits once you have found a positive Username and Password match.
  - `-l` - administrator – Use the username administrator to attempt to login.
  - `-P` - rockyou.txt– This is the word list that we will be pulling passwords from.
  - `ssh://192.168.34.16` - This is the service we want to attack and the IP address.
