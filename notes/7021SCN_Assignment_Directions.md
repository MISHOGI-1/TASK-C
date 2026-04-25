# 7021SCN Assignment Directions (Complete Reference)

Every instruction, requirement, marking criterion, and submission rule extracted from `Assignment_Brief_7021SCN.md` and consolidated here as the single source of truth.

---

## 1. Module and Submission Metadata

- Module: 7021SCN Software Security (30 credits)
- Assignment type: Practical Portfolio and Report
- Deadline: **18:00 Monday 20 April 2026**
- Grace period: 24 hours (until 18:00 Tuesday 21 April 2026) for unforeseen technical issues only
- Submission method: Word document via Turnitin on Aula
- Grading: Percentage (0-100%), pass mark 40%
- Module leader: Dr. Olalekan Lanihun (ad9193@coventry.ac.uk)

---

## 2. What Must Be Submitted

1. A **500-word Word document** report uploaded via Turnitin on Aula.
2. A **working link to your repository** placed at the end of the report.
3. The same **Word document** also placed at the root of the repository.
4. The repository must contain a clear **README.md** acting as a directory for the portfolio.

### Critical Fail Conditions

- Broken link = immediate fail.
- Private/inaccessible repository = immediate fail.
- Missing any of Tasks A-E = incomplete portfolio.

---

## 3. Portfolio Tasks (Each 20%)

### Task A: Vulnerability Discovery and Remediation (20%)

- Provide a small, custom-written **C or C++ programme** with a deliberate **memory corruption flaw** (e.g., buffer overflow).
- **Document** your method for exploiting it.
- Provide the **corrected code** using secure coding practices.

**Distinction (70-79%):** Excellent understanding of techniques. Well-detailed, documented evidence of discovery, exploitation, and fix.
**Exceptional (80-100%):** Exceptional understanding. Well-detailed, documented evidence throughout.

### Task B: Threat Modelling and SDLC (20%)

- Include a **threat model** for a hypothetical web application.
- Use **STRIDE methodology** to identify potential threats.
- Propose **specific, secure requirements** to mitigate them.

**Distinction (70-79%):** Critically evaluates complex threats. Deep understanding of attack surface. Highly tailored, robust mitigations. Excellent proactive, defensive design thinking in SDLC integration.
**Exceptional (80-100%):** Exceptional understanding of attack surface. Highly tailored, robust mitigations. Exceptional proactive, defensive design thinking.

### Task C: Automated Security Testing (20%)

- Submit **CI/CD pipeline configuration files** that automatically run static analysis.
- Include **output of a scan** (e.g., Semgrep or SonarQube).
- Include a brief **explanation of how you triaged the inevitable false positives**.

**Distinction (70-79%):** Excellent application of static analysis strategies. Excellent assessment of tool limitations. Intelligently explained results.
**Exceptional (80-100%):** Exceptional application and assessment. Intelligently explained results.

### Task D: Dynamic Analysis and Exploit Development (20%)

- Document a **web application penetration test** against a **local, vulnerable target**.
- Include **screenshots or logs** from tools (e.g., OWASP ZAP or Burp Suite).
- Prove understanding of flaws like **SQL injection** or **cross-site scripting (XSS)**.

**Distinction (70-79%):** Excellent application of dynamic testing strategies. Excellent assessment of tool limitations. Intelligently explained results.
**Exceptional (80-100%):** Exceptional application and assessment. Intelligently explained results.

### Task E: Compliance and Supply Chain (20%)

- Generate a **Software Bill of Materials (SBOM)** for a **containerised application**.
- Briefly explain how this artifact helps maintain **compliance** with frameworks like the **NIST Secure Software Development Framework (SSDF)**.

**Distinction (70-79%):** Thoroughly evaluates practical application of compliance frameworks. Demonstrates exactly how portfolio artifacts satisfy strict industry standards.
**Exceptional (80-100%):** Exceptional evaluation. Demonstrates exactly how artifacts satisfy strict industry standards.

---

## 4. The Report (500 words)

- **Not** a descriptive list of what is in the folder.
- Must be a **critical reflection** on the security posture of the work.
- Must discuss the **limitations of the tools used**.
- Must discuss the **real-world challenges of integrating security into the SDLC**.
- Must include a **working repository link** at the end.
- Must include an **AI usage declaration table** before the reference list.

---

## 5. Module Learning Outcomes (MLOs)

1. Critically identify and categorize software security threats and vulnerabilities, evaluating their potential impacts and mitigation strategies.
2. Integrate secure coding practices into the software development lifecycle (SDLC) and design robust systems that address common vulnerabilities.
3. Apply and critically assess software security testing strategies, including static and dynamic analysis, to identify and mitigate security flaws.
4. Evaluate and implement compliance with software security standards such as the SSDF, demonstrating an understanding of their practical applications.
5. Analyse and critique current and emerging software security challenges, proposing innovative and sustainable solutions.

---

## 6. AI Usage Declaration

A summary of where and how AI tools were used must be included at the end of the work before the reference list, using a table format:

| Tool | How used in this assignment |
|---|---|
| e.g. ChatGPT-3.5 | Key word search on topics related to learning outcomes |
| e.g. Microsoft Copilot | Summarising documents as part of background research |

---

## 7. Academic Integrity Rules

- All sources must be acknowledged and attributed.
- All AI tools must be referenced with purpose.
- Keep a record of thinking development (version control, journals).
- Plagiarism, self-plagiarism, and collusion detection software is used.
- Spelling, punctuation, and grammar must be effective, accurate, and appropriate.

---

## 8. Technical Problem Protocol

- If submission issues occur at the deadline, capture screenshots as evidence.
- Email screenshots and completed assessment to module leader immediately.
- This evidence supports an appeal but cannot itself be marked.

---

## 9. Marking Rubric Summary (Per Task)

| Band | Task A | Task B | Task C | Task D | Task E |
|---|---|---|---|---|---|
| 0-29% | No/minimal understanding | Fails to identify threats, incorrect categorization | No/minimal SAST application or assessment | No/minimal DAST application or assessment | Fails to generate SBOM, ignores compliance |
| 30-35% | Minimal understanding, fails pass mark | Fails to identify threats, minimal SDLC integration | Minimal SAST, minimal assessment | Minimal DAST, minimal assessment | Fails SBOM, minimal compliance identification |
| 40-49% | Limited understanding, limited evidence | Some STRIDE threats, generic mitigations, limited SDLC | Limited SAST, limited assessment | Limited DAST, limited assessment | Basic SBOM, weak/confusing compliance explanation |
| 50-59% | Good understanding, good evidence | Standard STRIDE, some mitigations, good defensive design | Good SAST, good assessment, explained results | Good DAST, good assessment, explained results | Basic SBOM, explanation of relevance to SSDF |
| 60-69% | Very good understanding, well-detailed evidence | Clear identification, realistic mitigations, very good defensive design | Very good SAST, intelligently explained results | Very good DAST, intelligently explained results | Very good SBOM-SSDF mapping |
| 70-79% | Excellent understanding, well-detailed evidence | Critical complex threat evaluation, deep attack surface, highly tailored mitigations | Excellent SAST, intelligently explained results | Excellent DAST, intelligently explained results | Thorough compliance evaluation, artifacts satisfy standards |
| 80-100% | Exceptional understanding, well-detailed evidence | Exceptional attack surface, exceptional defensive design | Exceptional SAST, intelligently explained results | Exceptional DAST, intelligently explained results | Exceptional compliance evaluation, artifacts satisfy strict standards |

---

## 10. Lecture-Derived Directions (Current Baseline)

### From Week 1 Lecture

- Apply CIA triad (confidentiality, integrity, availability) as the security framework across all tasks.
- Recognize why developers consistently get security wrong (time pressure, complexity, lack of training).
- Apply foundational secure coding principles: input validation, output encoding, least privilege, error handling, memory management, data protection.
- Use OWASP Top 10 as the vulnerability classification system.
- Avoid known vulnerable functions (printf, strcat, strcpy, etc.).
- Understand injection attacks (SQLi, XSS), broken authentication, security misconfiguration, vulnerable components, SSRF.
- Use peer review, static analysis, and OWASP best practices to discover vulnerabilities.

### From Week 2 Lecture 1 (Threat Modelling)

- Threat modelling is an engineering technique: Diagram -> Identify -> Mitigate -> Validate.
- Use DFDs with trust boundaries to map the system.
- Apply STRIDE for systematic threat identification.
- Use DREAD for risk prioritization (Damage, Reproducibility, Exploitability, Affected Users, Discoverability).
- Record threats in a structured triage table.
- Mitigate by redesign, apply countermeasure, or accept risk (documented decision).
- Threat modelling is iterative and must be revisited as systems change.
- Available tools: MS Threat Modeling Tool, OWASP Threat Dragon, IriusRisk.

### From Week 2 Lecture 2 (SDLC and Architecture)

- Apply security at every SDLC stage: Planning, Design, Development, Testing, Deployment, Maintenance.
- Distinguish security architecture (blueprint) from policies/standards (rules).
- Key secure design principles: Separation of Duties, Keep Security Simple, Audit Security Events, Fail Securely, Defense in Depth, Do Not Invent Security Mechanisms, Secure the Weakest Link.
- Quality code does not automatically mean secure code; security by design must be explicit.
- Defensive programming: anticipate misuse, validate all inputs, handle errors safely.
- Security architecture must cover: protect, deter, detect, react.
- NIST considers 30+ security principles in design/development guidance.

---

## Update Policy

This file should be updated whenever new reference materials, instructions, or scope changes are provided.
