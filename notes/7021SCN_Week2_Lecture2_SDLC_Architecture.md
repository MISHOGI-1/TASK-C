<!-- Slide number: 1 -->

![](Picture2.jpg)

![](Picture6.jpg)
# 7021SCN Software Security
Software Security Architecture and Secure Software
 Development Lifecycle
Created by Jeffrey Ting
Modified by Olalekan Lanihun

(Based on source material by Mia Mohac)

![](Picture3.jpg)

### Notes:

<!-- Slide number: 2 -->
# Content
System Threats, Vulnerabilities and Risks
Secure architecture and its importance in system development
What design principles are
Achieving security through secure design principles
Explain the core security principles applied to system design
Consideration of Human Factors in System security
Usable security, psychology of security and insider threat
Secure Software Development Lifecycle

2

### Notes:
We'll break down the key terms you’ll hear all the time: System Threats, Vulnerabilities and Risks. Understanding the difference between these is essential before we can talk about how to defend against them.
Once we've got the basics down, we’ll look at the bigger picture with secure architecture and its importance in system development. This is all about planning for security from the outset, rather than trying to add it on as an afterthought.
That naturally leads us to the core of today's talk. We'll quickly define what design principles are in this context, and then we'll spend most of our time on the main event: achieving security through secure design principles.
We’ll go through the core set of rules and ideas that help us build stronger, more resilient systems.
And finally, we'll tackle what is often the most important and unpredictable part of any system: the people.
We’ll finish with a consideration of Human Factors in System security. We'll touch on things like usable security, the psychology of security and the insider threat, because no matter how well we design the technology, we simply can't ignore the human element.

<!-- Slide number: 3 -->
# Learning Objectives
Identify cyber threats, vulnerabilities and risks
Understand the importance of designing secure architectures
Explain the different security principles that can be applied to system design and development to achieve the security requirements
Understand how to integrate security into different stages of software development lifecycle
3

### Notes:
By the end of this lecture, you should be able to identify cyber risks, understand why secure architecture matters, and explain how design principles enhance system security.

<!-- Slide number: 4 -->
# System Threat, Vulnerability and Risk
First, we introduce the definition of a system asset in cybersecurity in order to explain these concepts clearly.
"An asset is something valuable that we want to protect against potential threats. Generally, an asset could be a person, property or information."
 What is a threat?
"A threat usually refers to an event or factor that can potentially lead to a harmful state for a system. A threat to be "deployed" usually needs to find a vulnerability in a system."

### Notes:
We're going to start by looking at three of the most widely used terms in cybersecurity: Threat, Vulnerability, and Risk.
"But to understand those concepts clearly, we first need to talk about what we're actually trying to protect.
In security, we call this a system asset.
'An asset is something valuable that we want to protect against potential threats.'.
This could be physical property like a server, it could be information like a customer database, or it could even be a person. It's anything that has value to us.
'What is a threat?'.
'A threat usually refers to an event or factor that can potentially lead to a harmful state for a system.'. Think of it as the 'what' or 'who' that could cause damage. But here’s the crucial part: a threat on its own often isn't enough. For a threat to be successful, it usually 'needs to find a vulnerability in a system.'"

<!-- Slide number: 5 -->
# System Threat, Vulnerability and Risk
What is a system vulnerability?
"A vulnerability concerns the weaknesses or holes/gaps in a system. System weaknesses usually derive from a range of technical or non-technical issues."
Note: the more vulnerable a system is, the higher the risk of having asset losses.
What is a risk?
"Risk can be identified as a quantified unit that measures the impact that a threat can potentially have based on its probability to occur."
Mathematically, the risk is defined as:
risk = threat probability x potential loss/impact

### Notes:
we've just defined a threat as something that could cause harm, and we left off by saying that it needs to find a weakness to be successful. So, the obvious next question is...
"'What is a system vulnerability?'.
'A vulnerability concerns the weaknesses or holes/gaps in a system.'. It’s the unlocked window or the flimsy back door that an attacker could exploit. It’s important to remember that these weaknesses aren't always technical bugs; they can come from 'a range of technical or non-technical issues'—like a poor password policy or staff not being trained properly.
The more vulnerable a system is, the higher the risk of having asset losses.'. The more weaknesses you have, the more likely it is that a threat will find one.
"And that brings us neatly to our final key term: 'What is a risk?'.
'Risk' is something we can actually measure. It’s a way of figuring out the potential damage a threat could do, based on how likely it is to actually happen.
"We can even put this into a simple formula. 'Mathematically, the risk is defined as' the probability of a threat occurring, multipliedby the potential loss or impact.
So, that's risk=threat probability×potential loss/impact.
This helps us prioritise. A very unlikely event with a huge impact might be a similar risk to a very common event with a small impact."

<!-- Slide number: 6 -->
# Examples of Threat, Vulnerability and Risk
Assuming that the system considered in this example is a website and the specific system asset that we want to look at is its database.
What could be a threat for the database?
An SQL injection attack
What could make the database vulnerable?
A poor design or implementation of the authentication process of the website allowing SQL queries to be executed in user input fields
What could be a potential risk for the asset?
Unauthorised access, data loss/alteration, etc.

### Notes:
"For this scenario, let's assume the system we're talking about is a website, and the specific valuable asset we want to protect is its database.
Think of this as where all the important stuff, like customer details or user accounts, is stored.
"So, first question: 'What could be a threat for the database?'. A classic example is an SQL injection attack.
This is a specific method used by attackers to manipulate a database. So, the SQL injection attack is our threat.
"Next, as we've discussed, that threat needs a weakness to get through. So, 'What could make the database vulnerable?'.
In this case, the vulnerability could be a poor design or implementation of the authentication process of the website, specifically one that allows SQL queries to be run from a user input field like a search bar or login box. This weakness is the open door for our threat.
"Finally, if the threat gets through that vulnerability, what happens? 'What could be a potential risk for the asset?'.
The risk is the consequence—the bad outcome. In this case, it could be unauthorised access to sensitive data, the complete loss or alteration of that data, and so on. This is the impact of the threat being successful."

<!-- Slide number: 7 -->
# Mitigating Threats, Vulnerabilities and Risks
Apply security practices to all the stages of the System Development Life Cycle (SDLC)

![](Picture3.jpg)
Figure 1: Security in SDLC stages (adapted from SANS Institute)

### Notes:
we've defined what threats, vulnerabilities, and risks are. The question now is: how do we actually deal with them?
"The answer is that you have to apply security practices throughout the entire Development Life Cycle, or SDLC. Security isn't a final step you take just before release; it has to be a core part of the process from the very beginning.
"This diagram, which is adapted from the SANS Institute, shows exactly what that looks like in practice.
You can see it’s a cycle, with security built into every phase.
"It all starts with Step 1: Analysis and Design. Before a single line of code is written, you're already thinking about security.
This is where you do a high level risk assessment, identify the key Security Areas for the application, and make security a part of the fundamental design.
"Next, in Step 2: Develop, you're not just building features; you're actively building the security in.
This means you Develop the Security controls that you planned, create a security checklist, and follow secure coding guidelines to avoid creating vulnerabilities in the first place.
"Then we move to Step 3: Testing and Implementation. Here, you're actively trying to find weaknesses.
You're doing Threat Analysis, running specific Security Testing (which is different from just testing if a feature works), and performing Regression testing to make sure updates haven't introduced new security holes.
"Finally, at Step 4: Deployment, the system goes live. But it has to be done securely.
This involves a Secure Migration Process, Hardening requirements on Production systems—which means locking them down to make them more difficult to attack—and planning for Post Production security to handle issues that come up later."

<!-- Slide number: 8 -->
# Security Architecture?
In a very abstractive way, a security architecture could be defined as a framework that incorporates high-level design principles and decisions, which indicate whether certain security measures (or changes) can be applied or not, examining the potential impact on the security level of a system.
Note that a security architecture could also serve as a framework for secure design, as it considers the four classic stages of information security: protect, deter, detect, and react.
Thus, a general definition could be:
"Security Architecture is the process of selecting design elements and principles to match a defined security need."

### Notes:
At its core, a security architecture is a framework of high-level design principles and decisions.
The best way to think of it is as the master plan or the security blueprint for your system. It's not about the low-level, nitty-gritty details, but about the big picture.
This plan guides you when you're making changes, helping you assess the potential impact on the security level of a system.
"This framework also has to consider the four classic stages of information security.
Your architecture needs a plan for how you're going to protect your system, how you'll deter attackers, how you'll detect them if they do get in, and how you'll react when an incident happens. It covers the full lifecycle of a potential attack.
General definition: 'Security Architecture is the process of selecting design elements and principles to match a defined security need.'.
You first figure out what level of security you actually need, and then you choose the right building blocks and the right rules to achieve it. It's the thinking and planning that guides all your detailed security decisions later on.

<!-- Slide number: 9 -->
# Security Architecture (cont.)
Many system engineers think of it as a set of documents that specify the program organization, change of strategy, buy versus build decisions, major data structures, key algorithms, major objects and generic functionality issues.
It should NOT be confused with the policies or standards. Security policies and standards that define the rules about who can have access to what kinds of data, the testing procedures necessary, and so on.
A good security architecture should enable the engineer to apply it to a range of different systems.

### Notes:
"First, what does this blueprint actually contain? For many engineers, it's a set of documents that specify all the big-picture decisions. This includes things like the overall program organization, major 'buy versus build' decisions for security tools, and the key algorithms and data structures that will be used. It's the collection of all those foundational design choices.
"Now, this next point is crucial. A security architecture should NOT be confused with policies or standards. They are related, but they are not the same thing. The easiest way to think about it is this: the architecture is the blueprint for a house. The security policies and standards are the rules for living in that house—they define things like 'who can have access to what kinds of data' or the specific 'testing procedures' you must follow. So, architecture is the design, while policies are the rules you enforce within that design.
"And finally, what's a sign of a really good security architecture? It's not something that's so specific it only works for one project. A good security architecture should enable the engineer to apply it to a range of different systems. It's based on solid principles that are reusable and adaptable, not just a one-off solution."

<!-- Slide number: 10 -->
# Secure programming or programming for security?
Secure programming means fixing exploitable errors in code
Programming for security means incorporating security features such as crypto, password management etc.
Security features do not guarantee security

### Notes:
"First, we have 'Secure programming', which the slide says 'means fixing exploitable errors in code'. Think of this as the foundation. It's about writing high-quality, robust code that doesn't have bugs or loopholes that an attacker could exploit. It’s about not leaving the windows unlocked in the first place.
"Then you have 'Programming for security'. This is a bit different. This 'means incorporating security features such as crypto, password management etc.'. This is where you're actively adding things to your system to protect it—you're adding the alarm system, the CCTV, and the big bolt on the door.
"So, you might think if you do both, you're sorted. You've written perfect code and added lots of security features. But—and this is the most important point on the slide—'Security features do not guarantee security'.
You can have the best encryption in the world, but if a simple bug in your code allows an attacker to bypass it completely, then it's useless. Just adding a feature doesn't mean the system as a whole is secure. The real answer is that you need both: you need to build a solid, secure foundation and add the right features in a way that doesn't introduce new problems."

<!-- Slide number: 11 -->
# What about defensive programming?
Writing code always generates errors or bugs:
Syntax errors
Runtime errors
Logic errors

### Notes:
Defensive programming is about anticipating and handling errors—syntax, runtime, and logic errors. While helpful, it's not a silver bullet for security, especially if underlying vulnerabilities remain unaddressed.

<!-- Slide number: 12 -->
# What about defensive programming?
Syntax errors
Detected by compiler/interpreter
Punctuation, spelling, undefined variables
Not a security issue
Runtime errors
Computer instructed to do something it is incapable to do
E.g. divide by zero
Not a security issue as such except as DoS, info/memory leak…
Logic errors
Most difficult to detect
Possible security issues but not necessarily so

### Notes:
"First up, we have Syntax errors. These are the simple mistakes—things like spelling errors, bad punctuation, or using undefined variables. The good news is that these are almost always detected by the compiler or interpreter before your code can even run. Because of this, they are not a security issue.
"Next, we have Runtime errors. This is when your code is grammatically correct, but you've asked the computer to do something it is incapable to do. The classic example is trying to divide by zero. Your program will run, but it will crash at that point. On its own, this is not a security issue as such, but it can be exploited. An attacker might deliberately cause a runtime error to create a Denial of Service (DoS) or to make the program crash in a way that causes an info/memory leak.
"Finally, we have the trickiest ones: Logic errors. This is when your code is syntactically perfect and it runs without crashing, but it just doesn't do what you intended it to do. These are by far the most difficult to detect. And this is where we really start to worry, because logic errors can be possible security issues, although they aren't necessarily so in every case."

<!-- Slide number: 13 -->
# What about defensive programming?
Defensive programming is a strategy to address logic and runtime bugs or errors

But it is not a guarantee of secure coding.

### Notes:
we’ve just looked at the different types of programming errors, and we highlighted that runtime and logic errors are the trickiest ones to deal with.
"This is where defensive programming enters the picture.
'Defensive programming is a strategy to address logic and runtime bugs or errors'. It's all about anticipating what could go wrong.
A defensive programmer writes code that is designed to handle unexpected inputs and prevent crashes, making the software more stable and reliable. It's generally a very good thing to do.
"But—and this is the most important takeaway from this section—'it is not a guarantee of secure coding.'.
"This is a really critical point. Just because your code doesn't crash and it handles errors gracefully, it doesn't mean it's secure.
The main goal of defensive programming is to stop the program from breaking. The goal of secure coding is to stop a clever and malicious attacker from breaking in. Those are two very different objectives.
A program can be perfectly stable and still have a gaping security hole.

<!-- Slide number: 14 -->
# What about defensive programming?
Example in C/C++:

Null to arguments crashes the program
Void printMsg(FILE*, char* msg) { fprintf(file, msg);
}

### Notes:
"Here we have a very basic function in C or C++, called printMsg. Its job is incredibly simple: you give it a file and a message, and it uses the standard fprintf command to print that message to the given file.
"On the surface, it looks fine. But this is what we'd call 'happy path' programming—it assumes it will always be given valid inputs.
"The problem, as the note points out, is what happens when it's not. If a programmer accidentally passes a 'Null' value to either of the arguments—meaning the file doesn't exist or the message is empty—the function will try to use it anyway, and the entire program crashes.
"This is a classic runtime error. The code makes no attempt to validate its inputs or handle potential problems. It's fragile. A defensive programmer would look at this and know it needs to be fixed to prevent the crash.

<!-- Slide number: 15 -->
# What about defensive programming?
Example in C/C++:
Traps NULLs
Void printMsg(FILE*, char* msg) { if (file==NULL) {
logError("attempt to print message to null file");
} else if (msg==NULL) {
logError("attempt to print a null message");
} else { fprintf(file, msg);
No protection against malicious input
Attacker crafts format string msg
}
}

### Notes:
"You can see they've wrapped the core logic in if-else blocks. The code now checks if the file is NULL and if the msg is NULL before it tries to use them. As the first note says, it now 'Traps NULLs'. If it finds a null, it logs an error instead of crashing the whole program. From a reliability standpoint, this is much better. The code is no longer fragile.
"So, the defensive programmer has done their job. The code is now stable. But is it secure?
"This is the crucial part. Look at the else block where the fprintf function is still being called. While we've protected against null inputs, as the slide points out, there is still 'No protection against malicious input'.
"A defensive programmer is thinking about preventing accidental errors. A security-minded programmer is thinking about an active attacker. What if that msg string isn't just normal text? An 'Attacker crafts [a] format string msg'. This is a classic vulnerability. They could include special formatting characters in the message that fprintf will interpret as commands. This could allow them to read from the program's memory or even run their own code.
"So you can see the difference in mindset. The defensive fix stopped the crash, but it completely missed the security hole. The programmer's goal was to make the code stable, not to stop an attack.

<!-- Slide number: 16 -->
# What about defensive programming?
Example in C/C++:

Void printMsg(FILE*, char* msg) { if (file==NULL) {
logError("attempt to print message to null file");
} else if (msg==NULL) {
logError("attempt to print a null message");
} else {
fprintf(file, "%.128s",	msg);
}
Fixed format string constrains input
}

### Notes:
The crucial change is inside the else block, on the line with the fprintf function.
"If you look closely, you'll see the programmer is no longer just passing the msg variable directly. Instead, they've added a fixed format string: \"%.128s\".
"So what does this do? 'Fixed format string constrains [the] input'.
By providing our own format string, we are telling the fprintf function to always treat the msg variable as a plain string of text, up to a maximum of 128 characters. It will no longer interpret any special characters in the message as commands.
This completely shuts down the format string attack we talked about.
"And that small change perfectly illustrates the difference between defensive and secure coding.
The defensive programmer stopped the program from crashing.
The secure programmer stopped the attack. It requires a different mindset, you have to think about what a malicious person might try to do, not just what might go wrong by accident.
This is the kind of thinking that's needed to build genuinely secure systems."

<!-- Slide number: 17 -->
# What about defensive programming?
Defensive programming is NOT secure programming
It helps… but security is not its primary objective
It can also make the system less secure because it can trap errors which later will cause problems
It can disclose debugging information
It can encourage the developer to think that the system is secure when it isn’t

### Notes:
we need to be so clear about the difference between 'defensive' and 'secure' programming.
"The main takeaway is the first point: Defensive programming is NOT secure programming. It’s a bold statement, and it’s meant to be. We're not saying it's a bad practice; in fact, the next point clarifies that it helps... but security is not its primary objective. The main goal of defensive programming is to create reliable, stable software that doesn't crash when something unexpected happens. The main goal of secure programming is to stop a clever and malicious attacker from breaking your system. They're different jobs that require different mindsets.
"In fact, sometimes a purely defensive approach can backfire. The slide notes that it can also make the system less secure because it can trap errors which later will cause problems. For instance, imagine your code fails to apply a critical security setting. A defensive fix might be to catch that error, log it, and just continue running. The program doesn't crash, which is great for stability. But now it's running in an insecure state, and you've potentially opened up a huge vulnerability. The defensive code has hidden a dangerous failure.
"Another direct risk is that it can disclose debugging information. When defensive code catches an error, it often produces a very detailed error message. If an attacker can see that message—either on-screen or in a log file they can access—it can be a goldmine. It might tell them about your database tables, your server's file paths, or software versions you're using. You're basically giving them a map to help with their attack.
"And finally, perhaps the most subtle but dangerous issue is the false sense of security.
Defensive programming can encourage the developer to think that the system is secure when it isn’t.
After spending ages making their code robust and handling every possible error, a developer might think the code is 'bomb-proof'.
But as we saw in our fprintf example, they might have completely missed the security angle because they were focused on preventing accidents, not on stopping a deliberate attack."
"So, the bottom line is that defensive programming is an important part of writing good software, but it is not, and never will be, a substitute for a genuine security-first approach to development."

<!-- Slide number: 18 -->
# And quality program code?
It would be nice to think that good quality code, gauged by some predefined benchmarks would be secure code…
However, security has not always been high up the list of developer priorities:
http://www.codeexcellence.com/2012/05/8-must-have- characteristics-for-writing-quality-code/
Some characteristics help with secure code
But there is no requirement for security by design within various quality benchmarks

### Notes:
Okay, so we've seen that 'defensive' programming isn't the whole story. But that leads to another question: what if we just focus on writing excellent, high-quality code? If we follow all the industry best practices for quality, surely that will make our code secure, right?
"Well, 'it would be nice to think that good quality code, gauged by some predefined benchmarks would be secure code...'. It's a very appealing idea. You'd hope that if your code is well-structured, efficient, and maintainable, that security would just be a natural by-product of that quality.
"'However, security has not always been high up the list of developer priorities'. Historically, the main pressures on developers have been to deliver features, meet deadlines, and improve performance. Security was often seen as someone else's job, or something to be dealt with later.
"Now, to be clear, there is some overlap. 'Some characteristics' of high-quality code absolutely 'help with secure code'. For example, code that is simple, clean, and has good error handling is much easier to analyse for security flaws than a complex, tangled mess.
"But—and this is the critical takeaway—'there is no requirement for security by design within various quality benchmarks'. Most definitions of 'quality code' don't explicitly include things like 'resistance to attack' or 'threat modelling'. They're focused on functionality, reliability, and maintainability. You can have a beautifully engineered car with fantastic build quality, but if you've forgotten to design any locks for the doors, it's still not secure.
"So the conclusion here is that while writing high-quality code is a fantastic starting point, it is not a substitute for a deliberate and conscious focus on security. You have to design for security explicitly, which brings us to the core principles of how to do that."

<!-- Slide number: 19 -->
# Secure Design Principles

### Notes:

<!-- Slide number: 20 -->
# Definition of Secure Design Principles
What is a principle?
Cambridge Dictionary defines it as "a basic idea or rule that explains how something happens or works."

What are secure design principles then?
We could define them as "rules that are actually set to make security-related design decisions with respect to the system specification, which improves the system security."

### Notes:
Now, let’s talk about secure design principles. These are guiding rules for making design decisions that improve a system’s security posture. They help ensure that security is considered right from the design stage.

<!-- Slide number: 21 -->
# Secure Design Principles - Variations
There are different "standards" for the secure design process introduced by different organisations/persons, but none of them has been adopted as a universal standard yet.
Clifford J. Berg proposes around 180 security-related principles in his "High-Assurance Design: Architecting Secure and Reliable Enterprise Applications" book.
Open Web Application Security Project (OWASP) presents its top ten security principles used for the system design and development.
National Institute of Standards and Technology (NIST) considers over thirty different security principles met in design and development stages.
We are going to introduce some key principles, which are widely used to enhance the system security during the design stage.

### Notes:
"The main thing to know is that while there are different 'standards' for the secure design process introduced by different organisations, the key point is that none of them has been adopted as a universal standard yet.
There isn't one single, official rulebook that everyone in the world agrees on.
"And the number of principles these different standards suggest can vary wildly.
At one extreme, you have experts like Clifford J. Berg, who in his book on the topic proposes an incredibly detailed list of around 180 security-related principles.
"A bit more focused is the list from the US National Institute of Standards and Technology (NIST), which is a major authority in this area. They consider over thirty different security principles in their guidance.
"And then you have one of the most well-known groups in our field, the Open Web Application Security Project, or OWASP. They are fantastic at boiling things down to the essentials, and they present a top ten list of security principles.
"Now, we could spend all day debating the differences between these lists. But for our purposes, we are going to introduce some key principles. The principles we're about to cover widely used, they form the foundation of most of these other lists, and they are the most critical ones to understand during the design stage."

<!-- Slide number: 22 -->
# Key Secure Design Principles

Keep security simple
Audit security events
Fail Securely principle
Never rely on security by obscurity
Defence in depth principle
Do not use untested or your own security techniques
Detect and secure the weakest link of the system

### Notes:
These are the core principles we’ll cover: least privilege, separation of duties, simplicity, auditing, failing securely, avoiding obscurity, defence in depth, using trusted mechanisms, and securing the weakest link. Let’s break them down one by one.

<!-- Slide number: 23 -->
# Separation of Duties
This principle recommends that the responsibilities/duties and privileges should be separated and split across different users or services.
Why separation of duties?
Allowing one user to have all the responsibilities/duties and execute all or most of the system processes could end up being a huge vulnerability for it.
Decentralising the duties, you can have better control of the system operation, limit the impact of successful attacks and make attacks less attractive (e.g. insider threat)
Example: Changing systems and software typically requires a number of approvals, which require the involvement of more than one person. For example, implementing changes to firewall rules is separated from approving those changes as a basic security control.

### Notes:
our last principle was about limiting what any one person can do. Our next principle, Separation of Duties, builds on that idea by ensuring no single person can control a critical process all by themselves.
"As the slide says, the principle recommends that responsibilities/duties and privileges should be separated and split across different users or services. A classic real-world example is how many businesses handle money: you might have one person who is allowed to write the cheques, but a completely different person has to be the one to approve and sign them. You separate those duties to create a check-and-balance system.
"So why do we apply this to system security? Well, allowing one user to have all the responsibilities and control over a system from start to finish could end up being a huge vulnerability. It creates a single point of failure.
"By decentralising the duties, you get several big wins. You get better control over the system, you limit the impact of successful attacks because an attacker would need to compromise multiple accounts, and you make attacks less attractive, particularly when you're thinking about an insider threat. It’s much harder for one person to cause damage if they need someone else to approve their actions.
"The slide gives a perfect IT example: making changes to a firewall. A firewall is critical to network security. So, using separation of duties, you would have a system where one engineer has the ability to request and implement a change to the firewall rules, but a different person—like their manager—has to give the final approval before that change goes live. This basic security control ensures no single person can open up a dangerous hole in your network on their own.
"In short, if 'Least Privilege' is about giving each person the smallest key possible, 'Separation of Duties' is about making sure it always takes at least two different keys to unlock the most important doors."

<!-- Slide number: 24 -->
# Keep Security Simple
This principle suggests that a system should be design in a clear and simple way avoiding unnecessary features and functions. This will improve the understanding of the  system’s security requirements.
Why we should keep security simple?
Security requires good understanding of the system design. A complex design is rarely understood resulting in insufficient analysis and security of the system.
To avoid complex failure modes, implicit behaviour, etc.
Example: For instance, adding a new application to an old operating system could trigger possible system inconsistencies. Consider carefully whether the system needs that "additional" functioning feature that is added to it.

### Notes:
"The core idea is that a system should be design in a clear and simple way, avoiding unnecessary features and functions. Every feature, every option, every line of code you add to a system increases its complexity. As we'll see, that complexity is where security risks love to hide. A simpler system means it's easier for everyone on the team to understand the system's security requirements.
"So, why should we keep security simple?. There are two big reasons. Firstly, security requires good understanding of the system design. A complex design is rarely understood fully, even by the people who built it. If you don't understand all the moving parts and how they interact, you can't possibly secure it properly. You'll miss things, and attackers are experts at finding the things you've missed.
"Secondly, simplicity helps you avoid complex failure modes and implicit behaviour. The more complicated a system is, the more likely it is to behave in strange, unexpected ways when it's under stress. These unexpected behaviours are often where security vulnerabilities are found.
"The slide gives a good example: adding a new application to an old operating system could trigger possible system inconsistencies. You're bolting a new, complex thing onto an old, complex thing, and you can't be sure how they'll interact. It's why you should always consider carefully whether the system needs that 'additional' functioning feature before you add it. Every new feature has a 'security cost' because it adds complexity.
"Ultimately, it’s much easier to secure a small, well-understood cottage than it is to secure a giant, sprawling mansion with hundreds of doors and windows. Simplicity is a security feature in itself."

<!-- Slide number: 25 -->
# Audit Security Events
This principle suggests that a system needs to keep a record of the core and significant security events that occur during its operation.
Why we need an audit trail?
When there is a system failure, we need to know how it happened.
It can provide a log able to reconstruct the past.
It can act as a monitoring point and as a deterrent to people who are malicious.
Example: Record the changes to sensitive or confidential system files or even the changes that take place regarding the registered users of the system.

### Notes:
"The core idea is that a secure system needs to keep a record of the core and significant security events that occur during its operation. Think of it like a black box flight recorder on an aeroplane. You hope you'll never need it, but if something does go wrong, that record is absolutely essential for figuring out what happened. We call this record an audit trail.
"So, why do we need an audit trail?. Well, its most obvious use is for after an incident. When there is a system failure, we need to know how it happened, and a good log is often the only way we can reconstruct the past and piece together the sequence of events.
"But it's not just for looking backwards. A good audit trail is also a powerful tool for the here and now. It can act as a monitoring point to help you spot suspicious activity as it's happening. And just as importantly, it acts as a deterrent to people who are malicious. Just like a CCTV camera in a shop, if people know their actions are being logged, they are much less likely to do something they shouldn't.
"So what kind of events should we be logging? The slide gives a perfect example: we should record the changes to sensitive or confidential system files, or any changes that take place regarding the registered users of the system, like someone's permissions being changed or their password being reset. These are the significant events you'd absolutely need to know about if there was a security breach.
"In short, without a good audit trail, you're effectively flying blind. With one, you have the visibility you need to investigate incidents, monitor for threats, and deter bad behaviour."

<!-- Slide number: 26 -->
# Fail Securely
This principle suggests that when a system fails, it needs to do that securely.
Why we need a secure fail?
The confidentiality and integrity of a system should remain even though availability has been lost.
Attackers must not be permitted to gain access rights to privileged objects during a failure that are normally inaccessible.
Example: A failure related to the access control system of an operating system should "deny access to the users instead of granting it". This guarantees that unauthorised users will not gain access to it, benefiting from that failure.

### Notes:
our next principle is about what happens when your system breaks. It's a fact of life that systems fail, so we need to plan for it. The principle is called Fail Securely.
"The core idea is that when a system fails, it needs to do that securely. Think about a high-tech electronic lock on a secure server room. If the power fails, what should that lock do? Should it spring open, or should it remain locked? The 'fail secure' approach says it must remain locked, even if that means people can't get in for a while. The default position during a failure must be 'no', not 'yes'.
"So, why do we need a secure fail?. The first reason is about preserving what you can. When a system crashes, you've already lost its 'availability'. Failing securely ensures that the confidentiality and integrity of a system should remain even though availability has been lost. The system might be down, but at least the data is still safe and hasn't been tampered with.
"Secondly, and just as importantly, you have to assume that attackers are waiting to take advantage of any failure. We must make sure that attackers must not be permitted to gain access rights to privileged objects during a failure that are normally inaccessible. A system crashing shouldn't be a golden opportunity for a hacker.
"The slide gives a perfect example: think about the access control system of an operating system—the part that checks if you're allowed to open a file. If that system has an error, it should always default to 'deny access to the users instead of granting it'. If the system is confused and can't verify your permissions, the only safe answer is 'no'. This guarantees that unauthorised users will not gain access by benefiting from that failure.
"Ultimately, it's about choosing the lesser of two evils. It's far better to temporarily inconvenience a legitimate user by denying them access than it is to accidentally grant access to an attacker."

<!-- Slide number: 27 -->
# Security by Obscurity
This principle recommends that the security of key systems should not rely only upon keeping details hidden.
Why we should not rely on security by obscurity?
Security by obscurity is a weak security control, and nearly always fails when it is the only security control point.
Keeping information hidden does not imply that it is secure.
Example: The security of a software application that keeps its source code secret should not be the only security practice. Other practices like password policies, defence in depth and audit controls could also be considered for its security.

### Notes:
Security by Obscurity.
"So what is it? The principle recommends that the security of key systems should not rely only upon keeping details hidden. The really important word there is 'only'. This is the mistaken belief that your system is safe just because nobody knows its inner workings. A simple analogy is 'securing' your house by hiding the front door key under a plant pot. It might stop a casual visitor, but it won't stop a determined burglar who knows where to look.
"So why we should not rely on security by obscurity? Well, for starters, it is a weak security control, and nearly always fails when it is the only security control point. You must always assume that a determined attacker will eventually figure out your secrets. They have tools and techniques to discover how your system works.
"At the end of the day, just keeping information hidden does not imply that it is secure. As soon as your secret is discovered, your security is gone completely. Real security shouldn't rely on secrets.
A software company thinking its application is secure just because it keeps its source code secret. That's security by obscurity. A truly secure approach would involve adding other, much stronger practices like proper password policies, defence in depth and audit controls. These are real security controls that work even if the attacker has a full copy of your source code.
"So the big takeaway here is that obscurity is not security. You should always design your systems under the assumption that the attacker knows exactly how they are built. Your security should come from strong design and solid principles, not from hoping nobody finds your hidden key."

<!-- Slide number: 28 -->
# Defence in Depth
This principle suggests the application of multiple security layers that can prevent a single point of failure.
Why we need defence in depth?
Security is not massively affected by the failure of one security mechanism, as the other mechanisms may still provide the necessary security to protect the system.
Example: Assuming that the firewall of a network system is penetrated, defence in depth could utilise encryption to protect the data/information of the system.

### Notes:
"The main idea is the application of multiple security layers that can prevent a single point of failure. The easiest way to think about this is like defending a medieval castle. You don't just rely on a single high wall. You have a moat, then an outer wall, then archers, then an inner wall, and finally the castle keep itself. Each one is a different layer of defence. If the enemy gets past one layer, they immediately face another.
"So, why do we need defence in depth?. We need it because we have to assume that any single security control can, and eventually will, fail. No single defence is perfect. By having layers, the overall security is not massively affected by the failure of one security mechanism, because the other mechanisms may still provide the necessary security to protect the system.
"The slide gives a perfect modern example. Let's say your network firewall is penetrated. Your firewall is like the castle's outer wall—it's your first line of defence. If an attacker gets past it, you're not immediately defeated. With defence in depth, you might also utilise encryption to protect the data on your servers. The encryption is like a locked treasure chest inside the keep. Even though the attacker is inside the castle walls, they still can't get to the crown jewels because they're protected by a completely different type of security.
"So, the principle is simple: don't put all your security eggs in one basket. Use multiple, varied, and overlapping layers of defence, because any single one of them can fail."

<!-- Slide number: 29 -->
# Do not Invent Security Mechanisms
This principle suggests that you should not create and use your own security technology, try always to use a proven component.
Why we should not trust our security mechanisms?
Generation of security technology is a difficult task and it is usually a specialist job.
Use of our own mechanisms, instead of the industry security standards, could increase the system vulnerabilities.
Example: Do not use your own crypto methods to encrypt your data, since they could be proven unreliable and insecure. This could occur as they are not tested against powerful decryption tools or machines.

### Notes:
"The core principle suggests that you should not create and use your own security technology, but should try always to use a proven component that has been built and tested by experts. It's the same reason you wouldn't try to build your own parachute before going skydiving; you'd use one made by a company that has spent years testing and perfecting their design. The stakes are simply too high.
"So, why we should not trust our own security mechanisms?. Firstly, because the generation of security technology is a difficult task and it is usually a specialist job. The people who create these tools are often academics and specialist engineers who have spent their entire careers studying the incredibly subtle ways that security systems can fail.
"If you try to build your own, you're almost certain to miss something. And the use of our own mechanisms, instead of the industry security standards, could increase the system vulnerabilities. You might create something that looks secure to you, but an attacker will quickly find the flaw that you missed.
"The slide gives the most critical example of this: cryptography. You should not use your own crypto methods to encrypt your data. It might seem like a fun challenge to invent your own encryption algorithm, but it will be unreliable and insecure. Professional cryptographic standards have been publicly attacked and tested by thousands of the smartest people in the world for years. Your homemade version has not been tested against powerful decryption tools or machines and will almost certainly be broken very easily.
"The message here is to be humble. When it comes to fundamental security controls like encryption, don't reinvent the wheel. Use the boring, standard, and publicly-tested components that the whole industry relies on. It’s not about being clever; it’s about being secure."

<!-- Slide number: 30 -->
# Secure the Weakest Link
This principle suggests that you should repetitively inspect your system to find its weakest security point and strengthen it.
Why we should secure the weakest link of our system?
The system is as secure as its weakest link. This implies that known system vulnerabilities should be protected.
Minimise potential security threats related to the weakest link of the system
Example: Users can be the weakest link of your system as they are prone to social engineering attacks that utilise human manipulation techniques to be successful. A way to secure that weak link could be the training of these users.

### Notes:
"The core idea is that you should repetitively inspect your system to find its weakest security point and strengthen it. The best analogy is to think of your security as a chain. It doesn't matter if 99 of the links are made of solid steel; if one link is made of rusty tin, the entire chain is only as strong as that one rusty link. An attacker isn't going to waste their time on your strongest defences; they'll go straight for the weakest point.
"So why should we secure the weakest link of our system?. It's because of that simple truth: the system is as secure as its weakest link. Attackers will always follow the path of least resistance. Our job is to find that path before they do and make it stronger. By doing this, we minimise potential security threats related to the weakest link of the system.
"Now, the slide gives a brilliant example of a weak link that, very often, isn't a piece of technology at all—it's people. Users can be the weakest link of your system as they are prone to social engineering attacks that utilise human manipulation techniques to be successful. You can have the best firewall in the world and the most complex passwords, but if an attacker can simply phone an employee and trick them into revealing that password, all of your expensive technology is worthless.
"So how do you strengthen that human link? You can't patch a person like you patch software. A way to secure that weak link could be the training of these users. By making people aware of threats like phishing emails and social engineering, you make them a much stronger part of your overall security chain.
"In essence, this principle is all about prioritisation. It reminds us that security isn't just about building high walls; it's about making sure you haven't left any of the back doors unlocked."

<!-- Slide number: 31 -->
# And organisation behavioural issues
Organisations do not always respond to detected vulnerabilities e.g. Walmart/Asda
http://www.theregister.co.uk/2016/01/19/asda_severe_vuln/
Organisations still do not treat security seriously e.g. health apps formerly approved by UK NHS and US FDA
https://www.arxan.com/wp- content/uploads/2016/01/State_of_Application_Security_20 16_Healthcare_Report.pdf

### Notes:
common and dangerous organisation behavioural issues.
"The first major problem is that organisations do not always respond to detected vulnerabilities. It’s one thing for a bug to exist, but it's another thing entirely for a company to be told about a serious flaw and then do nothing about it.
"The slide gives the example of Walmart/Asda from a story back in 2016. The issue highlighted in the article wasn't just that a vulnerability was found, but the alleged delay in fixing it. This kind of behaviour can happen for many reasons: maybe the company doesn't take the report seriously, or it decides the fix is too expensive, or the internal process for fixing bugs is just too slow. Whatever the reason, the result is that customers are left exposed to a known risk.
"The second, and perhaps bigger, issue is that many organisations still do not treat security seriously from the very beginning. They might see it as a nuisance, a cost, or a box-ticking exercise, rather than a fundamental part of their responsibility to their users.
"A really concerning example of this is the case of health apps formerly approved by bodies like the UK NHS and US FDA. Given the incredibly sensitive medical data these apps handle, you would expect their security to be top-notch. However, the report linked here from 2016 suggested that many of them had basic, easy-to-find vulnerabilities. This points to an organisational failure where getting the app to market and getting it 'approved' was prioritised over the fundamental duty of protecting patient data.
"Now, it's true these examples are from a few years ago. But the underlying behaviours are timeless. The tension between the cost of security and other business priorities is still a huge issue today. It proves that you can have the best developers and the best tools, but if the company's culture doesn't truly value security, you will always have problems."

<!-- Slide number: 32 -->
# Human Factors in Security

### Notes:

<!-- Slide number: 33 -->
# Human Factors
Usable security:
Goal: Design and develop effective security mechanisms
Limitations: Behaviour of security mechanism is awkward, difficult or complicated
Psychology of Security:
Humans are the weakest link in security
Security should be built with respect to them and their behaviour, technical security is not always enough
Educate and train them against social engineering
33

### Notes:
the most critical and complex part of any system: the Human Factors.
"First up is the idea of Usable security. The goal for any security designer is, of course, to design and develop effective security mechanisms. But we've all come across systems where the security is just a nightmare to use. This is the limitation: the behaviour of [the] security mechanism is awkward, difficult or complicated.
"Think about a website that forces you to have a 20-character password with symbols, numbers, and uppercase letters, and then makes you change it every month. What's the result? People write the password on a sticky note and put it on their monitor. The security is so unusable that it forces people into insecure behaviours. That's the core problem that usable security tries to solve.
"This leads us directly into the broader topic of the Psychology of Security. You'll often hear people say that 'Humans are the weakest link in security'. And while that can be true, just blaming the user isn't very helpful.
"A much better approach is to recognise that security should be built with respect to them and their behaviour; technical security is not always enough. If your security system is fighting against human nature, human nature will win every time. The goal should be to make the most secure option the easiest and most obvious option for the user.
"So what's a practical step we can take? We need to educate and train them against social engineering. We can't 'patch' people, but we can make them aware of the psychological tricks that attackers use, like phishing emails designed to create a sense of panic. By training people to spot these tricks, we make them a much stronger part of our defences.
"Ultimately, we have to remember that we're designing systems for real people. We can't just throw technology at the problem and hope for the best. We have to make it usable and we have to provide training."

<!-- Slide number: 34 -->
# Human Factors
Insider Threat:
Definition: A current or former employee or other business partner who has or had authorised access to an organization's sensitive information and intentionally misused that access to damage the confidentiality, integrity or availability of that information
Identifying the Insider: There are some key behavioural indicators that can disclose a suspicious activity or intention. Such indicators are:
Remotely accesses the network while on vacation or at odd times, works odd hours without authorization, shows interest in matters outside of scope of his/her duties, has financial difficulties, involved in illegal activities, addicted to drugs or gambling, etc.
Preventing Insider Attacks: Use data/file encryption, data access monitoring, access control systems, system log analysis, intrusion detection systems, etc.
34

### Notes:
a specific and very challenging type of human risk: the Insider Threat.
"First, the definition. An insider threat is 'a current or former employee or other business partner who has or had authorised access... and intentionally misused that access' to cause damage. The crucial parts here are 'authorised access' and 'intentionally misused'. This isn't a hacker trying to break in; this is someone you've already trusted with a key to the building who then decides to do something malicious.
"This makes them very difficult to spot. So, how do you go about identifying the Insider? It's less about any one single action and more about looking for patterns of suspicious behaviour. The slide lists some potential behavioural indicators. These could be technical things, like someone who remotely accesses the network while on vacation or at odd times, or someone who shows interest in matters outside of [the] scope of his/her duties. They can also be related to personal circumstances, like someone known to have severe financial difficulties or problems with addiction.
"Now, it's really important to be careful here. Any one of these indicators on its own means very little. But a cluster of them might suggest that a person is a higher risk and that their activity should be monitored more closely.
"Because predicting who will become an insider threat is so hard, the best strategy is to have technical controls in place to limit the damage they can do. For preventing Insider Attacks, you can use a range of tools. Good data access monitoring and system log analysis let you see who is accessing what. Strong access control systems are vital—this is the 'least privilege' principle again. If an employee only has access to the data they absolutely need, the amount of harm they can do is severely limited. And things like data/file encryption and intrusion detection systems add further layers of protection.
"Ultimately, the insider threat is a huge challenge. It requires a combination of being aware of human behaviour and, more importantly, having robust technical controls in place to limit the potential damage from the start."

<!-- Slide number: 35 -->
# Secured Software Development Lifecycle
Software development lifecycle (SDLC) involves the various stages of completing the development of a software to the production stage
Security is also an essential part of software products
One can proactively integrate security into every stage of the Software development Lifecycle,
 Instead of waiting for security issues to come up when using the software product before we fix them
35

### Notes:
a specific and very challenging type of human risk: the Insider Threat.
"First, the definition. An insider threat is 'a current or former employee or other business partner who has or had authorised access... and intentionally misused that access' to cause damage. The crucial parts here are 'authorised access' and 'intentionally misused'. This isn't a hacker trying to break in; this is someone you've already trusted with a key to the building who then decides to do something malicious.
"This makes them very difficult to spot. So, how do you go about identifying the Insider? It's less about any one single action and more about looking for patterns of suspicious behaviour. The slide lists some potential behavioural indicators. These could be technical things, like someone who remotely accesses the network while on vacation or at odd times, or someone who shows interest in matters outside of [the] scope of his/her duties. They can also be related to personal circumstances, like someone known to have severe financial difficulties or problems with addiction.
"Now, it's really important to be careful here. Any one of these indicators on its own means very little. But a cluster of them might suggest that a person is a higher risk and that their activity should be monitored more closely.
"Because predicting who will become an insider threat is so hard, the best strategy is to have technical controls in place to limit the damage they can do. For preventing Insider Attacks, you can use a range of tools. Good data access monitoring and system log analysis let you see who is accessing what. Strong access control systems are vital—this is the 'least privilege' principle again. If an employee only has access to the data they absolutely need, the amount of harm they can do is severely limited. And things like data/file encryption and intrusion detection systems add further layers of protection.
"Ultimately, the insider threat is a huge challenge. It requires a combination of being aware of human behaviour and, more importantly, having robust technical controls in place to limit the potential damage from the start."

<!-- Slide number: 36 -->
# Core Phases of Security Integration in SDLC)
The following gives example of how we can integrate security into different stages of software development lifecycle.
36

### Notes:
a specific and very challenging type of human risk: the Insider Threat.
"First, the definition. An insider threat is 'a current or former employee or other business partner who has or had authorised access... and intentionally misused that access' to cause damage. The crucial parts here are 'authorised access' and 'intentionally misused'. This isn't a hacker trying to break in; this is someone you've already trusted with a key to the building who then decides to do something malicious.
"This makes them very difficult to spot. So, how do you go about identifying the Insider? It's less about any one single action and more about looking for patterns of suspicious behaviour. The slide lists some potential behavioural indicators. These could be technical things, like someone who remotely accesses the network while on vacation or at odd times, or someone who shows interest in matters outside of [the] scope of his/her duties. They can also be related to personal circumstances, like someone known to have severe financial difficulties or problems with addiction.
"Now, it's really important to be careful here. Any one of these indicators on its own means very little. But a cluster of them might suggest that a person is a higher risk and that their activity should be monitored more closely.
"Because predicting who will become an insider threat is so hard, the best strategy is to have technical controls in place to limit the damage they can do. For preventing Insider Attacks, you can use a range of tools. Good data access monitoring and system log analysis let you see who is accessing what. Strong access control systems are vital—this is the 'least privilege' principle again. If an employee only has access to the data they absolutely need, the amount of harm they can do is severely limited. And things like data/file encryption and intrusion detection systems add further layers of protection.
"Ultimately, the insider threat is a huge challenge. It requires a combination of being aware of human behaviour and, more importantly, having robust technical controls in place to limit the potential damage from the start."

<!-- Slide number: 37 -->
# Planning/Requirements Stage
At this stage, you defined functional security requirements e.g, Multi-factor Authentication (MFA) and Non-Functional requirements e,g,,  encryption
Set other security conditions for the requirement stage.
37

### Notes:
a specific and very challenging type of human risk: the Insider Threat.
"First, the definition. An insider threat is 'a current or former employee or other business partner who has or had authorised access... and intentionally misused that access' to cause damage. The crucial parts here are 'authorised access' and 'intentionally misused'. This isn't a hacker trying to break in; this is someone you've already trusted with a key to the building who then decides to do something malicious.
"This makes them very difficult to spot. So, how do you go about identifying the Insider? It's less about any one single action and more about looking for patterns of suspicious behaviour. The slide lists some potential behavioural indicators. These could be technical things, like someone who remotely accesses the network while on vacation or at odd times, or someone who shows interest in matters outside of [the] scope of his/her duties. They can also be related to personal circumstances, like someone known to have severe financial difficulties or problems with addiction.
"Now, it's really important to be careful here. Any one of these indicators on its own means very little. But a cluster of them might suggest that a person is a higher risk and that their activity should be monitored more closely.
"Because predicting who will become an insider threat is so hard, the best strategy is to have technical controls in place to limit the damage they can do. For preventing Insider Attacks, you can use a range of tools. Good data access monitoring and system log analysis let you see who is accessing what. Strong access control systems are vital—this is the 'least privilege' principle again. If an employee only has access to the data they absolutely need, the amount of harm they can do is severely limited. And things like data/file encryption and intrusion detection systems add further layers of protection.
"Ultimately, the insider threat is a huge challenge. It requires a combination of being aware of human behaviour and, more importantly, having robust technical controls in place to limit the potential damage from the start."

<!-- Slide number: 38 -->
# Design Stage
Threat Modelling
You identify potential attacks (threat) using frameworks such as STRIDE
The identification of potential threat should be done before any code is written at the design stage.
38

### Notes:
a specific and very challenging type of human risk: the Insider Threat.
"First, the definition. An insider threat is 'a current or former employee or other business partner who has or had authorised access... and intentionally misused that access' to cause damage. The crucial parts here are 'authorised access' and 'intentionally misused'. This isn't a hacker trying to break in; this is someone you've already trusted with a key to the building who then decides to do something malicious.
"This makes them very difficult to spot. So, how do you go about identifying the Insider? It's less about any one single action and more about looking for patterns of suspicious behaviour. The slide lists some potential behavioural indicators. These could be technical things, like someone who remotely accesses the network while on vacation or at odd times, or someone who shows interest in matters outside of [the] scope of his/her duties. They can also be related to personal circumstances, like someone known to have severe financial difficulties or problems with addiction.
"Now, it's really important to be careful here. Any one of these indicators on its own means very little. But a cluster of them might suggest that a person is a higher risk and that their activity should be monitored more closely.
"Because predicting who will become an insider threat is so hard, the best strategy is to have technical controls in place to limit the damage they can do. For preventing Insider Attacks, you can use a range of tools. Good data access monitoring and system log analysis let you see who is accessing what. Strong access control systems are vital—this is the 'least privilege' principle again. If an employee only has access to the data they absolutely need, the amount of harm they can do is severely limited. And things like data/file encryption and intrusion detection systems add further layers of protection.
"Ultimately, the insider threat is a huge challenge. It requires a combination of being aware of human behaviour and, more importantly, having robust technical controls in place to limit the potential damage from the start."

<!-- Slide number: 39 -->
# Development Stage
Static Analysis:

Use automated tools to scan  your source codes to review common flaws such as SQL injection

39

### Notes:
a specific and very challenging type of human risk: the Insider Threat.
"First, the definition. An insider threat is 'a current or former employee or other business partner who has or had authorised access... and intentionally misused that access' to cause damage. The crucial parts here are 'authorised access' and 'intentionally misused'. This isn't a hacker trying to break in; this is someone you've already trusted with a key to the building who then decides to do something malicious.
"This makes them very difficult to spot. So, how do you go about identifying the Insider? It's less about any one single action and more about looking for patterns of suspicious behaviour. The slide lists some potential behavioural indicators. These could be technical things, like someone who remotely accesses the network while on vacation or at odd times, or someone who shows interest in matters outside of [the] scope of his/her duties. They can also be related to personal circumstances, like someone known to have severe financial difficulties or problems with addiction.
"Now, it's really important to be careful here. Any one of these indicators on its own means very little. But a cluster of them might suggest that a person is a higher risk and that their activity should be monitored more closely.
"Because predicting who will become an insider threat is so hard, the best strategy is to have technical controls in place to limit the damage they can do. For preventing Insider Attacks, you can use a range of tools. Good data access monitoring and system log analysis let you see who is accessing what. Strong access control systems are vital—this is the 'least privilege' principle again. If an employee only has access to the data they absolutely need, the amount of harm they can do is severely limited. And things like data/file encryption and intrusion detection systems add further layers of protection.
"Ultimately, the insider threat is a huge challenge. It requires a combination of being aware of human behaviour and, more importantly, having robust technical controls in place to limit the potential damage from the start."

<!-- Slide number: 40 -->
# Testing Stage
Dynamic Analysis:

At this stage, you test the running application for common flaws/vulnerabilities such as session hijacking and misconfigurations.

40

### Notes:
a specific and very challenging type of human risk: the Insider Threat.
"First, the definition. An insider threat is 'a current or former employee or other business partner who has or had authorised access... and intentionally misused that access' to cause damage. The crucial parts here are 'authorised access' and 'intentionally misused'. This isn't a hacker trying to break in; this is someone you've already trusted with a key to the building who then decides to do something malicious.
"This makes them very difficult to spot. So, how do you go about identifying the Insider? It's less about any one single action and more about looking for patterns of suspicious behaviour. The slide lists some potential behavioural indicators. These could be technical things, like someone who remotely accesses the network while on vacation or at odd times, or someone who shows interest in matters outside of [the] scope of his/her duties. They can also be related to personal circumstances, like someone known to have severe financial difficulties or problems with addiction.
"Now, it's really important to be careful here. Any one of these indicators on its own means very little. But a cluster of them might suggest that a person is a higher risk and that their activity should be monitored more closely.
"Because predicting who will become an insider threat is so hard, the best strategy is to have technical controls in place to limit the damage they can do. For preventing Insider Attacks, you can use a range of tools. Good data access monitoring and system log analysis let you see who is accessing what. Strong access control systems are vital—this is the 'least privilege' principle again. If an employee only has access to the data they absolutely need, the amount of harm they can do is severely limited. And things like data/file encryption and intrusion detection systems add further layers of protection.
"Ultimately, the insider threat is a huge challenge. It requires a combination of being aware of human behaviour and, more importantly, having robust technical controls in place to limit the potential damage from the start."

<!-- Slide number: 41 -->
# Deployment Stage
Secure Configuration:

Harden environment, securely managing secrets;
For example, using Azure key vaults

41

### Notes:
a specific and very challenging type of human risk: the Insider Threat.
"First, the definition. An insider threat is 'a current or former employee or other business partner who has or had authorised access... and intentionally misused that access' to cause damage. The crucial parts here are 'authorised access' and 'intentionally misused'. This isn't a hacker trying to break in; this is someone you've already trusted with a key to the building who then decides to do something malicious.
"This makes them very difficult to spot. So, how do you go about identifying the Insider? It's less about any one single action and more about looking for patterns of suspicious behaviour. The slide lists some potential behavioural indicators. These could be technical things, like someone who remotely accesses the network while on vacation or at odd times, or someone who shows interest in matters outside of [the] scope of his/her duties. They can also be related to personal circumstances, like someone known to have severe financial difficulties or problems with addiction.
"Now, it's really important to be careful here. Any one of these indicators on its own means very little. But a cluster of them might suggest that a person is a higher risk and that their activity should be monitored more closely.
"Because predicting who will become an insider threat is so hard, the best strategy is to have technical controls in place to limit the damage they can do. For preventing Insider Attacks, you can use a range of tools. Good data access monitoring and system log analysis let you see who is accessing what. Strong access control systems are vital—this is the 'least privilege' principle again. If an employee only has access to the data they absolutely need, the amount of harm they can do is severely limited. And things like data/file encryption and intrusion detection systems add further layers of protection.
"Ultimately, the insider threat is a huge challenge. It requires a combination of being aware of human behaviour and, more importantly, having robust technical controls in place to limit the potential damage from the start."

<!-- Slide number: 42 -->
# Maintenance Stage
This stage requires continuous monitoring
That is continuous monitoring for new threats,
Manage patches, and establish and establish incident response plans for the live environment.
42

### Notes:
a specific and very challenging type of human risk: the Insider Threat.
"First, the definition. An insider threat is 'a current or former employee or other business partner who has or had authorised access... and intentionally misused that access' to cause damage. The crucial parts here are 'authorised access' and 'intentionally misused'. This isn't a hacker trying to break in; this is someone you've already trusted with a key to the building who then decides to do something malicious.
"This makes them very difficult to spot. So, how do you go about identifying the Insider? It's less about any one single action and more about looking for patterns of suspicious behaviour. The slide lists some potential behavioural indicators. These could be technical things, like someone who remotely accesses the network while on vacation or at odd times, or someone who shows interest in matters outside of [the] scope of his/her duties. They can also be related to personal circumstances, like someone known to have severe financial difficulties or problems with addiction.
"Now, it's really important to be careful here. Any one of these indicators on its own means very little. But a cluster of them might suggest that a person is a higher risk and that their activity should be monitored more closely.
"Because predicting who will become an insider threat is so hard, the best strategy is to have technical controls in place to limit the damage they can do. For preventing Insider Attacks, you can use a range of tools. Good data access monitoring and system log analysis let you see who is accessing what. Strong access control systems are vital—this is the 'least privilege' principle again. If an employee only has access to the data they absolutely need, the amount of harm they can do is severely limited. And things like data/file encryption and intrusion detection systems add further layers of protection.
"Ultimately, the insider threat is a huge challenge. It requires a combination of being aware of human behaviour and, more importantly, having robust technical controls in place to limit the potential damage from the start."

<!-- Slide number: 43 -->
# Conclusions
Threats, vulnerabilities and risks should be tackled at any stage of the system’s life cycle.
Security architectures are used to specify security and facilitate the design and development process of systems.
The application of secure design principles could guarantee a proper security level for the system to be developed.
43

### Notes:
"First, we established that threats, vulnerabilities and risks should be tackled at any stage of the system’s life cycle. We saw this clearly with the Software Development Lifecycle models. The old way of treating security as a final check before release just doesn't work. It has to be a continuous process, baked into every phase from the initial design right through to deployment and maintenance.
"Secondly, we've seen that security architectures are used to specify security and facilitate the design and development process of systems. We defined this as the high-level blueprint for security. It’s the master plan that guides our decisions and ensures we're building a solid foundation, rather than just reacting to problems as they appear.
"Third, and this was the real heart of the talk, we saw how the application of secure design principles could guarantee a proper security level for the system to be developed. We went through a whole range of these powerful, guiding ideas—things like Least Privilege, Defence in Depth, Failing Securely, and Keeping it Simple. These are the practical tools that allow us to translate a good architecture into a genuinely secure system.
"And finally, a point that can never be stressed enough: engineers should carefully consider humans as an important factor in the equation called system security. We talked about usable security, the psychology of security, and the insider threat. This reminds us that the most technically brilliant system can be undone by a person. We have to design for real people and understand that they are a crucial part of our security posture.
"So, to sum it all up: building secure systems requires a proactive and principled approach that thinks about security at every stage and never, ever forgets the human element.

<!-- Slide number: 44 -->
# Conclusions
Software Engineers should carefully consider humans as an important factor in the equation called system security.
Security can be proactively integrated into every stage of the software development lifecycle.
44

### Notes:
"First, we established that threats, vulnerabilities and risks should be tackled at any stage of the system’s life cycle. We saw this clearly with the Software Development Lifecycle models. The old way of treating security as a final check before release just doesn't work. It has to be a continuous process, baked into every phase from the initial design right through to deployment and maintenance.
"Secondly, we've seen that security architectures are used to specify security and facilitate the design and development process of systems. We defined this as the high-level blueprint for security. It’s the master plan that guides our decisions and ensures we're building a solid foundation, rather than just reacting to problems as they appear.
"Third, and this was the real heart of the talk, we saw how the application of secure design principles could guarantee a proper security level for the system to be developed. We went through a whole range of these powerful, guiding ideas—things like Least Privilege, Defence in Depth, Failing Securely, and Keeping it Simple. These are the practical tools that allow us to translate a good architecture into a genuinely secure system.
"And finally, a point that can never be stressed enough: engineers should carefully consider humans as an important factor in the equation called system security. We talked about usable security, the psychology of security, and the insider threat. This reminds us that the most technically brilliant system can be undone by a person. We have to design for real people and understand that they are a crucial part of our security posture.
"So, to sum it all up: building secure systems requires a proactive and principled approach that thinks about security at every stage and never, ever forgets the human element.

<!-- Slide number: 45 -->
# Resources
The OWASP security principles can be found at: https://www.owasp.org/index.php/Security_by_Design_Principles#Separation_of_duties
The paper "Software Engineering - Security as a Process in the SDLC" by SANS institute can be found at: https://uk.sans.org/reading-room/whitepapers/securecode/software-engineering-security-process-sdlc-1846
More about Security Principles by CISCO at: https://developer.cisco.com/media/onepk_security_guide/GUID-26BCB36E-7B4B-4D59-B71C-6CA423A6F569.html
Security Principles by NIST can be found at: http://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-27ra.pdf

### Notes:
If you want to explore further, here are some excellent resources. OWASP, NIST, Cisco, and the SANS Institute all offer valuable guidelines and documentation on secure design and development.

<!-- Slide number: 46 -->
# End
