<!-- Slide number: 1 -->

![](Picture2.jpg)

![](Picture6.jpg)
# 7021SCN – Software Security
Threat Modelling

Created by Jeffrey Ting
Modified by Olalekan Lanihun

![](Picture3.jpg)

### Notes:
It’s the process of thinking about what could go wrong, before it goes wrong

<!-- Slide number: 2 -->

![Security](Picture2.jpg)
https://xkcd.com/538/

### Notes:
The 'crypto nerd' on the left is thinking about a purely technical attack, brute-forcing encryption. The attacker on the right knows it's much, much easier to use a $5 wrench.
This is a physical threat, or you could even call it a form of social engineering. The point is, attackers don't follow our rules. They look for the easiest path, not the most technically clever one.
Our job as secure developers is to think like the person on the right. We have to consider all the threats, not just the ones that fit neatly into our technical diagrams. Threat modelling is the structured way we do that.

<!-- Slide number: 3 -->
Lecture outline and aims
We will consider what we mean when we talk about threat modelling
We will look at why we want to do threat modelling
We will look at the STRIDE and DREAD methodologies

<!-- Slide number: 4 -->
Threat modelling
Threat modelling is a core element of the Security Development Lifecycle
It’s an engineering technique one can use to identify threats, attacks, vulnerabilities, and countermeasures that could affect an application
We can use threat modelling:
to shape an application's design
to meet the company's security objectives
to reduce risk.

### Notes:
threat modelling is a core part of any good Security Development Lifecycle, or SDL. It’s an engineering technique we use to systematically identify all the things that could go wrong with our application. We're looking for:
Threats: Things a 'bad guy' might want to do (e.g., "steal user data").
Attacks: The method they might use (e.g., "SQL injection").
Vulnerabilities: The weakness in our code that lets the attack happen (e.g., "un-sanitised user input").
Countermeasures: What we're going to do about it (e.g., "use parameterised queries").
We do this to shape the application's design right from the start , to make sure we're meeting our company's security goals , and, ultimately, to reduce risk

<!-- Slide number: 5 -->
# The 'When' and 'Who' of Threat Modelling
When:
at the design stage, before you've even written a line of code.
Who:
Architects who know the high-level design.
Developers who know the code-level details.
Testers (QAs) who are brilliant at thinking of edge cases.
Product Owners who understand what the data is and why it's valuable.

### Notes:
This isn't something you just 'do once' at the end. Threat modelling is most effective when you start early, at the design stage, before you've even written a line of code. It's much, much cheaper and easier to fix a design flaw on a whiteboard than it is to re-architect an entire system that's already in production.
And it's not a job for one 'security person' in a dark room. The best threat modelling sessions involve everyone

<!-- Slide number: 6 -->
Microsoft Security Development
Lifecycle (SDL)

![](object4.jpg)

### Notes:

<!-- Slide number: 7 -->
# Diagram
Map your system
A DFD shows how data moves around.
External Entities: Users, other systems, anything outside your application that sends or receives data.
Processes: The 'brains' of your app. Things that take data, change it, and send it on.
Data Stores: Anywhere data is saved. Think databases, log files, or even temporary memory.
Data Flows: The arrows that connect everything, showing where data is moving.
Trust Boundaries.
These are lines you draw on your diagram anywhere data crosses from a 'less trusted' environment to a 'more trusted' one.

### Notes:
Before you can find threats, you need to know what you're protecting. This step is all about mapping out your system. The most common way to do this is with a Data Flow Diagram (DFD).
A DFD shows how data moves around. You'll draw:
External Entities: Users, other systems, anything outside your application that sends or receives data.
Processes: The 'brains' of your app. Things that take data, change it, and send it on.
Data Stores: Anywhere data is saved. Think databases, log files, or even temporary memory.
Data Flows: The arrows that connect everything, showing where data is moving.
Crucially, you must also draw Trust Boundaries. These are lines you draw on your diagram anywhere data crosses from a 'less trusted' environment to a 'more trusted' one. The biggest one, of course, is the line between the public internet and your web server. Every time data crosses one of these boundaries, it's a potential hotspot for threats."

<!-- Slide number: 8 -->
# Identify
You point at every single part of your DFD
every process,
every data store,
every data flow
and you ask the STRIDE questions.
'Could someone Spoof this process?',
'Could this data flow be Tampered with?',
'Is there a risk of Information Disclosure from this data store?'
This is how you systematically brainstorm threats instead of just guessing.

<!-- Slide number: 9 -->
# Mitigate
Redesign/Fix:
This is the best one. Change the design to remove the threat completely. (e.g., "We won't store that sensitive data at all.")
Apply a Countermeasure:
You can't remove the threat, so you add a control to protect against it. (e.g., "We'll add encryption to this data flow" or "We'll add input validation on that form.")
Accept the Risk:
This is a business decision. You might find a threat that is very unlikely to happen and would cost a fortune to fix. The business might formally decide to accept that risk. The key is that it's a conscious, documented choice, not an accident.

<!-- Slide number: 10 -->
# Validate
Now you need to check two things:
Did our fix actually work?
Did our fix introduce any new threats? (This happens all the time!)
This is a loop.
You validate your fixes, which might mean updating your diagram, which leads to identifying new threats, and so on.
It's a continuous process, not a one-off task.

<!-- Slide number: 11 -->
Do we REALLY need to follow the
SDL?
Developers must address security threats
Customers require trustworthy and secure software
Companies who address security threats more effectively will gain competitive advantage in the marketplace
Privacy demands attention
blocked deployments, litigation, negative media coverage, and mistrust

### Notes:

<!-- Slide number: 12 -->
The SDL pillars
Three elements of SDL:
best practices
process improvements
metrics
The ultimate goals:
to minimize security-related vulnerabilities in the design, code, and documentation
to detect and eliminate vulnerabilities as early as possible in
the development lifecycle

<!-- Slide number: 13 -->
Apps and Services that required to
adhere to the SDL
ANY software release that:
commonly used or deployed within any organization
stores, processes, or communicates sensitive information
attractive to/target children
connected to the Internet or other networks
(always online/designed to be online/exposed online)
automatically downloads updates
accepts or processes data from an unauthenticated source
(i.e. virtually everything that you write)

<!-- Slide number: 14 -->
STRIDE
A simple way of categorising threats to help with the modelling
Spoofing Identity – can an attacker pretend to be who they are not? Includes machines as well as people and doesn't have to rely on authentication information being understood
Tampering with data – can an attacker maliciously manipulate data?
Repudiation – can an attacker carry out an activity and later deny having done it? In other words, how good is the traceability / accountability of the system?
Information disclosure – can an attacker gain access to information that they were not meant to know?

<!-- Slide number: 15 -->
STRIDE
Denial of service – can an attacker use a DoS (or DdoS) to deny service to other users?
Elevation of privilege – can an attacker gain more access to the system than they should be allowed (Note – different from Information Disclosure in that disclosure is about data, elevation is about processes)
NB Many of the threats can fall into multiple categories

<!-- Slide number: 16 -->
# Spoofing Identity
What it is?
Pretending to be someone or something you're not. This could be a person or even a machine.
Examples:
Phishing Email: An attacker sends an email that looks like it's from your bank.
IP Spoofing: A server fakes its IP address to look like it's a trusted machine on an internal network.
Fake Website: An attacker sets up paypa1.com hoping you'll type your password in.
Common Mitigations:
Authentication: The classic! Passwords, multi-factor authentication (MFA), client certificates. Anything that proves you are who you say you are.
Digital Signatures: Cryptography that proves a message came from a specific sender and hasn't been changed.

<!-- Slide number: 17 -->
# Tampering with Data
What it is: Maliciously changing data. This could be data 'in transit' (as it's flying over the network) or data 'at rest' (sitting in your database).
Examples:
Man-in-the-Middle (MITM) Attack: An attacker on a public Wi-Fi intercepts your network traffic and changes a request from "transfer £10" to "transfer £1,000".
URL Manipulation: A user changes a value in the web address, like .../viewOrder?id=123 to .../viewOrder?id=124 to see someone else's order.
Modifying a config file: An attacker gets onto your server and changes a setting to disable logging.
Common Mitigations:
Access Controls (ACLs): Stop people from touching files they shouldn't.
Hashing & Digital Signatures: A hash proves the data hasn't been changed.
Strong Validation: Never trust user input. Check that id=124 actually belongs to the logged-in user.
Encryption (in transit): Using HTTPS (SSL/TLS) stops MITM attacks.

### Notes:

<!-- Slide number: 18 -->
# Repudiation
What it is: The ability for an attacker to do something and then later deny they ever did it.
Examples:
"I never authorised that £5,000 bank transfer!" If the bank has no proof, that's a repudiation threat.
"I never received that order confirmation!"
An admin making a change in the system and then deleting the log files to cover their tracks.
Common Mitigations:
Secure Audit Trails: Logging who did what, when.
Digital Signatures: When you digitally sign something, it's very hard to deny you did it. This is called non-repudiation.
Timestamps: Securely logging the time of an event.

<!-- Slide number: 19 -->
# Information Disclosure
What it is: An attacker gaining access to information they're not supposed to see.
Examples:
Verbose Error Messages: An error page that shows a full database connection string or a stack trace.
Directory Traversal: An attacker uses ../../etc/passwd in a URL to read system files.
Weak Encryption: Storing passwords in plain text (or with weak, reversible encryption).
Common Mitigations:
Encryption (at rest & in transit): Encrypt data in the database and when it's sent over the network.
Access Controls: Make sure only authorised people can see the data.
Proper Error Handling: Show users a generic "Something went wrong" message, but log the detailed error on the server for your developers

<!-- Slide number: 20 -->
# Denial of Service (DoS)
What it is: An attacker preventing legitimate users from using the system.
Examples:
Network Flood: The classic Distributed Denial of Service (DDoS) attack, overwhelming a server with junk traffic.
Resource Exhaustion: An attacker finds a slow, database-heavy search query and runs it 10,000 times to tie up your database.
Account Lockout: An attacker tries to log in to your account with the wrong password 10 times, locking you out of your own account.
Common Mitigations:
Throttling & Rate Limiting: Only allow a user (or IP address) to perform an action (like 'login') a few times per minute.
Quotas: Limit the amount of disk space or CPU a user can consume.
Firewalls & Load Balancers: Can filter out obvious flood traffic.

<!-- Slide number: 21 -->
# Elevation of Privilege (EoP)
What it is: An attacker with a low level of access (like a normal user) finding a way to get a higher level of access (like becoming an administrator).
Examples:
Buffer Overflow: A classic attack where an attacker sends too much data to a program, overflowing its memory and tricking it into running the attacker's own code.
Broken Access Control: A user finds they can just visit the URL /admin and the system lets them in, without checking if they're an admin.
Common Mitigations:
Principle of Least Privilege: This is the big one. Every user and every process should only have the absolute minimum permissions they need to do their job. Your web server probably doesn't need 'root' or 'Administrator' rights.
Input Validation: Properly check all data from the user to prevent things like buffer overflows.

<!-- Slide number: 22 -->
DREAD
Damage Potential – how great is the damage if this threat is successful? 1 if it just allows the user to change their background, 10 if it allows complete system access. May take into account data value
Reproducibility – some bugs involve complex race conditions and are difficult to get right (score 1), some work every time (score 10)
Exploitability -  How much knowledge and resources are required for a successful attack. 10 if it can be done by a script kiddie, 1 if it requires the resources of MI5
Affected Users – how many users would be affected. Can roughly use percentage but need to consider importance and number of users
Discoverability – how easy it is to discover the vulnerability? Safest to assume 10!

### Notes:
DREAD is another mnemonic. You give each threat a score (say, 1-10) for each of these categories:
Damage Potential: How bad is it if this happens? (1 = changes a background colour, 10 = full system compromise)
Reproducibility: How easy is it to make the attack work again? (1 = a one-in-a-million race condition, 10 = works every single time)
Exploitability: How much skill or resource does the attacker need? (1 = needs the resources of a nation-state, 10 = a 'script kiddie' can do it with a simple tool)
Affected Users: How many people will be impacted? (1 = just one user, 10 = every user on the system)
Discoverability: How easy is it to find this vulnerability? (The slide rightly says it's safest to assume 10 for this! )
You can then average these scores ( (D+R+E+A+D) / 5 ) to get a single risk number. Your '10/10' threats are what you fix first.
It's worth knowing that DREAD is a bit subjective, and even Microsoft, who created it, have moved to other models. But it is a brilliant tool for getting you to think about the different factors that make a threat serious.

<!-- Slide number: 23 -->
Threat Trees
Hardware experts use fault trees to model when a system might fail – we can use a similar approach to model threats
We can use our threat categorisations to classify parts of our application model that might be vulnerable to certain types of threat.
We can then model those threats using a threat tree
A threat tree is the processes an attacker might go through to compromise that part of our application
Note – trees are a nice way to initially sketch the threat, but a pseudo code approach is sometimes easier to use when you have large numbers of threat trees

### Notes:
Threat Tree. This is just like the fault trees that engineers use.
You start with the attacker's main goal at the top—the 'root' of the tree. In this example, the goal is 'Get password'.
Then you break that goal down into the 'OR' branches. How could they get the password?
They could Guess it.
OR they could use Social Engineering.
OR they could Spy for it.
You keep breaking each branch down until you get to the 'leaf' nodes—the specific, actionable attack.
To 'Guess offline' , an attacker needs to (AND) 'Get Encrypted Password' (AND) 'Perform a Dictionary Attack'.
To 'Spy' , they could use a camera or a microphone , which, as the other diagram shows, might require physical access.
Your job as the defender is to 'prune' these branches. If you enforce a strong password policy, you make 'Dictionary Attack' much harder. If you add account lockouts, you make 'Guess Online' almost impossible. You find the cheapest, easiest way to make the attacker's life difficult."

<!-- Slide number: 24 -->
A simple login threat tree

![](Picture2.jpg)

<!-- Slide number: 25 -->
A simple login threat tree
1) User can get password
	1.1) Guess Password
		1.1.1) Guess Online
		1.1.2) Guess Offline
			1.1.2.1) Get Encrypted Password (AND)
			1.1.2.2) Dictionary Attack
	1.2) Social Engineering
		1.2.1) Ask Administrator
	1.3) Spy password
		1.3.1) In person
		1.3.2) With camera
		1.3.3) With microphone

<!-- Slide number: 26 -->
A simple login threat tree (extended)

![](Picture3.jpg)

<!-- Slide number: 27 -->
Recording threats
Put threats into a table – this will help with the triaging

![](Picture4.jpg)

### Notes:
When you find a threat, you must record it properly. A simple table like this is perfect.
Give it a Title.
Note the Threat Target (which part of your DFD is affected).
List the Threat type (STRIDE).
Give it a Risk (maybe from your DREAD score).
Describe the Mitigation (what you're going to do).
And, if you use a bug tracker like Jira, log the Bug number! This makes sure the fix actually gets scheduled and doesn't get forgotten."

<!-- Slide number: 28 -->
Threat Modelling Tools
Threat Modelling Tools:
MS TMT, see https://aka.ms/threatmodelingtool
Cairis, see https://cairis.org/
IriusRisk, see https://www.iriusrisk.com/
OWASP Threat Dragon, see https://owasp.org/www-project-threat-dragon/
Threat Modelling Frameworks:
MITRE ATT&CK, See https://attack.mitre.org/
OWASP top 10, see https://owasp.org/Top10/
MITRE Common Weakness Enumeration (CWE), see https://cwe.mitre.org/

<!-- Slide number: 29 -->
# Tools
Tools are applications that help you do the modelling:
MS TMT (Threat Modelling Tool):
This is a free tool from Microsoft. It's fantastic for beginners. You draw your DFD in it, and it will auto-generate a list of potential STRIDE threats for you to think about.
OWASP Threat Dragon:
This is an open-source tool from OWASP. It's a bit more modern and designed to fit well into agile development.

<!-- Slide number: 30 -->
# Frameworks
Frameworks are bodies of knowledge that inform your modelling:
OWASP Top 10: This isn't a modelling technique, it's a list of the 10 most common web application vulnerabilities (like SQL Injection, Broken Access Control, etc.). It's a brilliant checklist to use during your 'Identify' phase.
MITRE ATT&CK: This is a massive, amazing knowledge base of real-world attacker tactics. It's less about finding design flaws and more about understanding how attackers behave once they are already inside your network. It's incredibly useful for security operations teams.
MITRE CWE (Common Weakness Enumeration): This is a giant dictionary of all the different types of software weaknesses. It's much, much more detailed than the OWASP Top 10."

<!-- Slide number: 31 -->
# Summary
Think Like an Attacker:
Threat modelling is about being proactive and finding weaknesses before the 'bad guys' do. Remember the $5 wrench.
It's a Structured Process:
Don't just guess. Use a clear, repeatable process: Diagram (DFD), Identify (STRIDE), Mitigate (Fix/Accept), and Validate (Check).
Start Early, and Involve the Team:
This is a design-stage activity, and it's a team sport.
Prioritise Your Fixes:
You can't fix everything. Use a model like DREAD to find the scariest threats and fix those first.
It's an Iterative Loop:
Security isn't 'done'. Your application will change, and new threats will appear. You need to keep revisiting your model."

<!-- Slide number: 32 -->
MS TMT
Security Briefs - Getting Started With The SDL Threat Modeling Tool - https://learn.microsoft.com/en-us/archive/msdn-magazine/2009/january/security-briefs-getting-started-with-the-sdl-threat-modeling-tool
Getting started with the Threat Modelling Tool (2022 version) - https://learn.microsoft.com/en-us/azure/security/develop/threat-modeling-tool-getting-started
Threat Modeling Security Fundamentals (MS Learning path) - https://learn.microsoft.com/en-us/training/paths/tm-threat-modeling-fundamentals/
