# 7021SCN Distinction Checklist

## Baseline Reference Set (Current)
- `7021SCN_Week1_Lecture.md`
- `7021SCN_Week2_Lecture1_ThreatModelling.md`
- `7021SCN_Week2_Lecture2_SDLC_Architecture.md`
- This checklist is `v1` and should be updated when new reference material is provided.

## Working Rule
- Do not start implementation work until all instructions are provided and the explicit command to start is given.

## 1) Pre-start Requirements Lock
- [ ] Confirm language/tooling choices for Tasks A-E.
- [ ] Confirm vulnerable targets are legal and local-only.
- [ ] Confirm repository host and visibility settings.
- [ ] Confirm referencing/citation style.
- [ ] Confirm report word budget strategy (target: 500 words).
- [ ] Confirm we will explicitly apply CIA, OWASP, STRIDE, and secure design principles from lecture references.

## 2) Evidence-First Repository Structure
- [x] Define repository folder structure and naming conventions.
- [x] Create per-task folders with: objective, method, evidence, fix/mitigation, limitations.
- [x] Add root `README.md` as a clear index to all tasks and artifacts.

## 3) Task A - Vulnerability Discovery and Remediation (20%)
- [x] Build a custom vulnerable C/C++ program (memory corruption, e.g., buffer overflow).
- [x] Document reproducible exploit method with clear proof (logs/screenshots).
- [x] Provide secure remediated code and explain why the fix is effective.
- [x] Validate that the original exploit path is no longer viable.
- [x] Align remediation with secure coding principles (input validation, safer memory handling, defensive coding, logging).

## 4) Task B - Threat Modelling and SDLC (20%)
- [x] Define assets, actors, entry points, trust boundaries, and attack surface.
- [x] Build a DFD and highlight trust boundaries clearly.
- [x] Apply STRIDE correctly and specifically (not generic statements).
- [x] Provide realistic, tailored mitigations for each threat.
- [x] Record threats in a triage table and prioritize using a risk model (e.g., DREAD scoring where appropriate).
- [x] Show SDLC integration points (requirements, design, testing, deployment, monitoring).

## 5) Task C - Automated Security Testing (20%)
- [x] Add CI/CD configuration that runs static analysis automatically.
- [x] Include actual scan output artifact(s) in the repo.
- [x] Explain triage decisions, including false positives and rationale.
- [x] Document tool limitations and risk trade-offs.
- [x] Show how static analysis findings map to OWASP-style vulnerability classes where relevant.

## 6) Task D - Dynamic Analysis and Exploit Development (20%)
- [x] Perform web penetration testing against a local vulnerable target.
- [x] Demonstrate at least one meaningful flaw class (e.g., SQLi or XSS) with evidence.
- [ ] Include tool evidence (OWASP ZAP/Burp logs/screenshots).
- [x] Provide remediation guidance and retest/validation outcomes.
- [x] Explain attack impact in terms of confidentiality, integrity, and availability (CIA).

## 7) Task E - Compliance and Supply Chain (20%)
- [x] Generate an SBOM for a containerized application.
- [x] Explain practical SBOM value for compliance and risk visibility.
- [x] Map artifacts explicitly to SSDF (or equivalent framework expectations).
- [x] Note supply-chain limitations and ongoing monitoring approach.
- [x] Link supply-chain controls to secure architecture ideas (defense in depth, weakest-link awareness, no custom crypto/security mechanisms).

## 8) Report Quality Gate (500 words)
- [ ] Report is a critical reflection, not a folder description.
- [ ] Evaluate limitations of tools used and practical SDLC integration challenges.
- [ ] Synthesize key lessons learned across Tasks A-E.
- [ ] Critically justify design/security decisions using lecture-grounded principles.
- [ ] Place a working repository link at the end of the report.
- [ ] Include AI usage declaration table before references.
- [ ] Include the report Word document at repo root.

## 9) Report Word Count Allocation (Target: 500 words)
- [ ] Introduction and scope: **40 words**
- [ ] Task A critical reflection: **70 words**
- [ ] Task B critical reflection: **90 words**
- [ ] Task C critical reflection: **80 words**
- [ ] Task D critical reflection: **80 words**
- [ ] Task E critical reflection: **70 words**
- [ ] Cross-cutting limitations and SDLC integration challenges: **50 words**
- [ ] Conclusion: **20 words**
- [ ] Total: **500 words exactly**

## 10) Final Submission Gate
- [ ] Verify repository link works while logged out/incognito.
- [ ] Verify all evidence artifacts open correctly.
- [ ] Check clarity, professionalism, and consistency of naming.
- [ ] Submit report via Turnitin before deadline.
- [ ] Keep a timestamped backup copy of final submission assets.

## Distinction Standard Reminder
- Aim for depth, evidence quality, and critical judgement in every task.
- Show clear finding -> mitigation -> validation traceability.
- Explicitly discuss limitations and residual risk, not only successes.
- Demonstrate secure-by-design thinking, not security-as-afterthought.
