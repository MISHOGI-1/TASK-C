# 7021SCN Software Security

## Week 6 Lab 2 — Automating Container SBOM Generation

---

## Introduction

The assessment requires a critical written report explaining how your pipeline and SBOM satisfy strict industry standards. Today, we will map your specific engineering evidence directly to the NIST Secure Software Development Framework (SSDF). You will write the core arguments of your report today.

**Prerequisites and Setup Instructions**

- A word processor (Word, Google Docs, etc.).
- Your `.github/workflows/generate-sbom.yml` file from the previous lab.
- A screenshot of a successful GitHub Actions workflow run from the previous lab.
- Your downloaded `cyclonedx-sbom.zip` (containing your `sbom.json`) from the previous lab.

> **Warning:** Do not open ChatGPT. If you generate a generic essay about "why NIST is important," you will not do well. You must write about *your specific code*.

---

## Step 1: Mapping to SSDF Practice PS.1 (Protect Software)

*NIST defines PS.1 as: "Protect all forms of code from unauthorized access and tampering."*

In the real world, if you build a Docker container on your local laptop and push it to production, an auditor will fail you. Why? Because your laptop is contaminated. You could have malware, or you could have tampered with the code before building it.

- **The Evidence:** Open your report document and create a heading for **PS.1**. Paste a snippet of your `generate-sbom.yml` file (specifically the `on: push` and `runs-on: ubuntu-latest` lines) and insert the screenshot of your successful GitHub Actions run.
- **The Argument (Write this in your own words):** Explain that by using GitHub Actions, you have created a "clean room" build environment. You do not build the software; the automated pipeline builds it on a pristine, ephemeral Ubuntu runner triggered exclusively by version-controlled code commits.
- **The Conclusion:** State that this automation removes human tampering from the build process, directly satisfying PS.1.

*Expected Output:* A drafted paragraph clearly linking your CI/CD YAML to the concept of tamper-evident, automated builds.

---

## Step 2: Mapping to SSDF Practice PW.4 (Produce Well-Secured Software)

*NIST defines PW.4 as: "Maintain provenance data for all components of a software release."*

When the next Log4j zero-day vulnerability drops, companies without provenance data spend weeks guessing if their servers are vulnerable. Companies with provenance data run a database query and know in five seconds.

- **The Evidence:** Create a heading for **PW.4**. Open your `sbom.json` file in a text editor. Take a screenshot of a specific dependency block (e.g., where it lists a Python library like Flask and its exact version number). Paste this screenshot into your report.
- **The Argument (Write this in your own words):** Explain that your `sbom.json` acts as an absolute ingredient list. It provides deep visibility into the hidden, nested third-party libraries inside your Docker container.
- **The Conclusion:** State that by automatically capturing the exact versions and licenses of every component during the build phase, you are maintaining the strict provenance records required by PW.4.

*Expected Output:* A drafted paragraph using your SBOM JSON file to prove you understand software supply chain transparency.

---

## Step 3: Mapping to SSDF Practice RV.1 (Respond to Vulnerabilities)

*NIST defines RV.1 as: "Identify and confirm vulnerabilities in software on an ongoing basis."*

You could have generated your SBOM as a PDF document. You didn't. You generated it as a machine-readable CycloneDX JSON file. This distinction is the difference between a Junior and a Senior engineer.

- **The Evidence:** Create a heading for **RV.1**. Reference the fact that your pipeline specifically uses the `format: "cyclonedx-json"` command.
- **The Argument (Write this in your own words):** Explain *why* you chose JSON. A PDF sits on a manager's desk gathering dust. A standardized CycloneDX JSON file can be automatically ingested by continuous monitoring tools (like Aqua Trivy or enterprise SIEMs).
- **The Conclusion:** State that formatting the SBOM as machine-readable data allows security teams to automate daily scans against new CVE databases, satisfying the "ongoing basis" requirement of RV.1.

*Expected Output:* A drafted paragraph explaining the strategic value of machine-readable data formats in continuous security monitoring.

---

## Troubleshooting Common Errors

- **The "Generic Essay" Trap:** If your report reads like a Wikipedia article about the NIST SSDF, you have failed the assignment. Every paragraph must reference *your* GitHub Action, *your* Dockerfile, or *your* JSON file.
- **Missing Evidence:** Do not just write that you did these things. You must include screenshots of the logs and the JSON snippets. Auditors (and markers) do not believe what you say; they believe what you can prove.
- **Formatting Fails:** Ensure your screenshots are legible. If the marker cannot read the text in your terminal screenshot, they cannot award you marks for it.

---

## Challenge Tasks

### Challenge 1: The Remediation Mapping (RV.2)

If you completed Challenge 1 and 2 in Lab 1 (adding Aqua Trivy to your pipeline to scan the SBOM and break the build on CRITICAL vulnerabilities), you have a massive advantage.

Create a final section in your report mapping your Trivy integration to **NIST SSDF Practice RV.2 (Remediate Vulnerabilities)**. Use a screenshot of Trivy intentionally failing your pipeline to prove that you do not just *monitor* for vulnerabilities; you have engineered a hard, automated policy that prevents vulnerable code from ever reaching the registry. This is Exceptional-level analysis.

### Challenge 2: Threat Modelling and SDLC

If you have completed the Week 6 Lab 1 and Lab 2 exercises, you have successfully mapped your report to the evidence for tasks C and E in the assignment brief. Create another section in your report document titled **Threat Modelling and SDLC**. Briefly explain how you use the STRIDE methodology to identify and mitigate potential threats using secure requirements for a threat model of a hypothetical web application that you have provided in your GitHub repository. This satisfies task B of the assignment brief.

### Challenge 3: Dynamic Analysis and Exploit Development

In the Week 1 lab, we use Burp Suite to perform a penetration test against the Juice Shop site. In this challenge, you will use the same Burp Suite and follow the steps in Week 1 to perform penetration testing on a local vulnerable web app that you have been using in the previous labs (`webapp.zip` file on Aula). Create a section in your report and call it **Dynamic Analysis and Exploit Development**. In the section, document the web application penetration test against this local host web app target (provided in your repository), including screenshots from the tools that you used (e.g., Burp Suite), proving your understanding of flaws like SQL injection or cross-site scripting (XSS). When you have done this challenge, you have successfully completed task D of the assignment brief.

### Challenge 4: Vulnerability Discovery and Remediation

Create a section/heading in your report titled **Vulnerability Discovery and Remediation**. Briefly explain your methods of exploiting a memory corruption (C/C++) code, such as a buffer overflow that you provide in your GitHub repository. Also, explain how you have used secure coding practices to fix the memory corruption flaws (referencing the fix/corrected code in your GitHub repository). When you have done this, you will have been able to solve Task A of the assignment brief.

---

*This document is intended for Coventry University Group students for their own use in their work for this module. It should not be passed to third parties or posted on any website. — Jeffrey Ting*
