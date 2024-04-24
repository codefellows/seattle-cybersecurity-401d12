<!-- .element class="main-title" -->
# Ops 401: Cybersecurity Engineering

<br>

## Class 39

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

- &shy;<!-- .element style="color: red;" -->**Class 39** - SQLi with Burp Suite & Web Goat

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

- **Class 38** - Web App Fingerprinting Part 3 of 3

<br>

- &shy;<!-- .element style="color: red;" -->**Class 39** - Mock Interviews

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

- Changes from 2017 to 2021 editions

![Image](/ops-401-cybersecurity-guide/curriculum/class-38/slides/assets/8_1.png)

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

<!-- .element class="main-title" -->
# Database 101

---

<!-- .element class="split-screen-with-title" -->
# Databases

<div>

<div>

- A database (DB) is an organized collection of structured information stored electronically in a computer system
- A database system has three elements
  - Database management system (DBMS)
  - Data
  - Associated applications
    - Example: Web application
- Databases have two types
  - Relational
  - Non-relational

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-39/slides/assets/8_0.png)
Source: Wikiversity

</div>

</div>

NOTE:

- Non-relational databases
  - The non-relational database, or NoSQL database, stores data. However, unlike the relational database, there are no tables, rows, primary keys or foreign keys.  Instead, the non-relational database uses a storage model optimized for specific requirements of the type of data being stored.
  - Some of the more popular NoSQL databases are MongoDB, Apache Cassandra, Redis, Couchbase and Apache HBase.
- Relational databases
  - relational database works by linking information from multiple tables through the use of “keys.”
  - A key is a unique identifier which can be assigned to a row of data contained within a table.
  - This unique identifier, called a “primary key,” can then be included in a record located in another table when that record has a relationship to the primary record in the main table

---

<!-- .element class="split-screen-with-title" -->
# Databases

<div>

<div>

- **Structured Query Language (SQL)** is a non-procedural, domain-specific programming language used by nearly all relational databases to query, manipulate, define data, and provide access control
  - Tables
  - Primary keys
  - Queries
    - Example: `SELECT * FROM TableName`

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-39/slides/assets/9_0.png)
Source: Wikiversity

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Databases

<div>

<div>

- Is SQL a programming language?
  - What it CAN do
    - Communicate with databases
  - What it CANNOT do
    - Build a web page or create an application
  - SQL is "domain-specific" language
    - Python is a "general-purpose" programming language

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-39/slides/assets/10_0.png)
Source: Wikiversity

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Databases

<div>

<div>

- SQL is still the predominant language used when querying large databases
- Scale of SQL ranges from small SQL Express deployments to massive Oracle PL/SQL DBs that fuel enterprise systems like ERPs or eCommerce sites
- A SQL injection attack requires very little to be effective:
  - Web browser
  - Basic SQL knowledge
  - Internet connection

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-39/slides/assets/11_0.png)
Source: Wikiversity

</div>

</div>

---

<!-- .element class="main-title" -->
# Basic SQL Commands

---

<!-- .element class="split-screen-with-title" -->
# Basic SQL Commands

<div>

<div>

- SELECT statements operate in read-only mode to fetch information from the specified table
`SELECT (column_name_1, column_name_2)
FROM your-table-name`
- INSERT statements allow us to add new records to a table
`INSERT INTO "your-table-name" (column_name_1, column_name_2)
VALUES (value_for_column_name_1, value_for_column_name_2)`

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-39/slides/assets/13_0.png)
Source: Wikiversity

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Basic SQL Commands

<div>

<div>

- UNION returns results of two or more SELECT statements
  - Each SELECT statement within UNION must have the same number of columns
  - The columns must also have similar data types
  - The columns in each SELECT statement must also be in the same order
`SELECT column_name(s) FROM table1 UNION SELECT column_name(s) FROM table2;`

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-39/slides/assets/14_0.png)
Source: Wikiversity

</div>

</div>

---

<!-- .element class="split-screen-with-title" -->
# Basic SQL Commands

<div>

<div>

- UPDATE will revise existing data
`UPDATE Products SET column_name_2 = new_value WHERE Column_name_1 = some_value`
- These are normal SQL commands used every day by DBAs all the way down to your junior dev/analyst

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-39/slides/assets/15_0.png)
Source: Wikiversity

</div>

</div>

---

<!-- .element class="main-title" -->
# Injection

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

<!-- .element class="split-screen-with-title" -->
# Injection

<div>

<div>

- How can organizations protect themselves against SQL injection attacks?
  - Web application firewalls (WAFs) configured to detect SQLi
  - Improving database access controls
  - On the web dev side, input sanitization is the process of checking data input by users before processing it on the backend

</div>

<div>

![Image](/ops-401-cybersecurity-guide/curriculum/class-39/slides/assets/18_0.png)
Source: OWASP, 9Lessons

</div>

</div>

---

<!-- .element class="main-title" -->
# Demo
