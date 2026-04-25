# 7021SCN Report Documentation (Live Working Draft)

## Status
- Mode: Active build and evidence capture
- Build state: In progress
- Update policy: This file must be updated whenever scope, evidence, tools, or instructions change.
- Environment note: `python` is available; `gcc` is not currently installed in this workspace environment.

## Reference Inputs (Current Baseline)
- `Assignment_Brief_7021SCN.md`
- `7021SCN_Week1_Lecture.md`
- `7021SCN_Week2_Lecture1_ThreatModelling.md`
- `7021SCN_Week2_Lecture2_SDLC_Architecture.md`
- `7021SCN_Assignment_Directions.md` (consolidated directions from all sources)
- Note: Additional references will be appended as provided.

## Report Target
- Required length: 500 words
- Style: Critical reflection (not descriptive inventory)
- Required inclusions:
  - Repository link at end of report
  - AI usage declaration table before references
  - Report Word document stored at repository root

## Word Budget Plan (500 words)
- Introduction and scope: 40
- Task A critical reflection: 70
- Task B critical reflection: 90
- Task C critical reflection: 80
- Task D critical reflection: 80
- Task E critical reflection: 70
- Cross-cutting limitations and SDLC integration challenges: 50
- Conclusion: 20

## Living Evidence Map (Populate During Build)
### Task A - Vulnerability Discovery and Remediation
- Objective: Demonstrate a memory corruption flaw in C and show secure remediation.
- Evidence files: `Task_A_Vulnerability_Remediation/vulnerable.c`, `Task_A_Vulnerability_Remediation/fixed.c`, `Task_A_Vulnerability_Remediation/vulnerable.exe`, `Task_A_Vulnerability_Remediation/fixed.exe`, `Task_A_Vulnerability_Remediation/README.md`
- Key findings: Unsafe `strcpy` into fixed stack buffer creates overflow risk.
- Mitigation applied: Input length check + bounded copy + explicit null termination.
- Validation outcome: **VERIFIED** — `vulnerable.exe` crashes with exit code -1073741819 (access violation) on overflow input. `fixed.exe` safely rejects with "Input rejected: name too long."
- Report insight (draft): Memory safety failures are often predictable design failures that can be prevented with secure coding defaults.

### Task B - Threat Modelling and SDLC
- Objective: Build STRIDE-based threat model for a hypothetical student web portal.
- Evidence files: `Task_B_Threat_Modelling_SDLC/README.md`, `Task_B_Threat_Modelling_SDLC/DFD_StudentHub.md`
- Key findings: Highest-risk items include EoP, credential abuse, and data disclosure.
- Mitigation applied: MFA, RBAC authorization checks, secure logging, validation, and deployment hardening controls.
- Validation outcome: Threats are recorded and risk-prioritized using DREAD-style scoring.
- Report insight (draft): Threat modelling becomes useful only when translated into SDLC gates and testable requirements.

### Task C - Automated Security Testing
- Objective: Implement CI/CD static analysis and produce evidence-led triage including false-positive handling.
- Evidence files: `.github/workflows/task-c-static-analysis.yml`, `Task_C_Automated_Security_Testing/scan-output/semgrep-results.json`, `Task_C_Automated_Security_Testing/README.md`, `Task_C_Automated_Security_Testing/triage-log.md`
- Key findings: 92 total findings from Semgrep auto ruleset, dominated by repeated SQL-injection sink detections in `Task_E_Compliance_Supply_Chain/app.py` plus 1 Docker least-privilege finding.
- Mitigation applied: Findings grouped into must-fix, contextual lab-only accepted risk, and duplicate/framework-mismatch noise classes with explicit rationale.
- Validation outcome: JSON scan artifact generated and stored in Task C path; CI workflow added to reproduce and upload artifact on push/PR.
- Report insight (draft): Static analysis value depends on disciplined triage and explainable risk decisions, not raw finding count.

### Task D - Dynamic Analysis and Exploit Development
- Status: **Removed from repo** pending your new instructions and resources. Will be rebuilt from scratch.

### Task E - Compliance and Supply Chain
- Objective: Produce SBOM for a containerised application and map to SSDF-aligned expectations (per brief).
- Evidence files (current): `Task_E_Compliance_Supply_Chain/app.py`, `Task_E_Compliance_Supply_Chain/database.db`, `Task_E_Compliance_Supply_Chain/init_db.py`, `Task_E_Compliance_Supply_Chain/readme.txt`, `Task_E_Compliance_Supply_Chain/schema.sql`, `Task_E_Compliance_Supply_Chain/requirements.txt`, `Task_E_Compliance_Supply_Chain/static/css/style.css`, `Task_E_Compliance_Supply_Chain/README.md`
- Key findings: Flask shop app with intentional insecure patterns (for later security analysis); SQLite schema and seed data loaded via `init_db.py`.
- Mitigation applied: None yet at Task E layer; SBOM/Docker/SSDF mapping to follow your next instructions.
- Validation outcome: `database.db` generated successfully in task folder; `app.py` and `init_db.py` use paths relative to this folder so the app runs regardless of current working directory.
- Report insight (draft): SBOM and supply-chain controls must be tied to a reproducible build surface (dependencies + base image), not only source files.

## Cross-Cutting Reflection Prompts
- Which controls were effective, and which were weak?
- Where did tool output require human judgement?
- What false positives or blind spots appeared?
- What SDLC integration friction appeared (time, complexity, skills, tooling)?
- What residual risks remain and why?

## AI Usage Declaration (Draft Table)
| Tool | How used in this assignment |
|---|---|
| Cursor AI | Assisted with code scaffolding, report structuring, and documentation formatting |
| ChatGPT | |
| Other | |

## Related Files
- `7021SCN_Assignment_Directions.md` - Complete consolidated directions from brief, rubric, MLOs, and lectures.
- `7021SCN_Evidence_Capture_Checklist.md` - Per-screenshot/log evidence capture checklist for all tasks.
- `7021SCN_Distinction_Checklist.md` - Process and quality gate checklist.
- `Report_7021SCN_Draft.md` - Ready-to-paste 500-word report draft in portfolio root.

## Change Log
- 2026-03-23: Created live report documentation template and update protocol.
- 2026-03-23: Started implementation and created full Task A-E portfolio scaffold with initial evidence artifacts and report-draft structure.
- 2026-03-23: Verified Python source syntax for Task D and Task E; identified missing local GCC tool for Task A runtime compilation.
- 2026-03-23: Added comprehensive directions file (`7021SCN_Assignment_Directions.md`) with all brief, rubric, MLO, and lecture-derived requirements.
- 2026-03-23: Created DFD artifact (`DFD_StudentHub.md`) for Task B with trust boundaries and per-flow STRIDE mapping.
- 2026-03-23: Produced ready-to-paste 500-word report draft (`Report_7021SCN_Draft.md`).
- 2026-03-23: Created evidence capture checklist (`7021SCN_Evidence_Capture_Checklist.md`) with every required screenshot/log per task.
- 2026-04-11: Installed GCC (MinGW via MSYS2). Compiled and ran both Task A programs. Overflow crash verified (exit -1073741819). Fix verified (safe rejection).
- 2026-04-11: Installed Semgrep v1.159.0. Ran live scan: 8 findings across 303 rules. Triage table updated with real CWE-mapped results.
- 2026-04-11: Added database auto-init to Task D sample_app.py. App is now fully runnable with 4 demo users.
- 2026-04-11: Installed Syft v1.23.0. Generated real SBOM with 7 actual Flask dependency components in CycloneDX 1.6 format.
- 2026-04-25: Rebuilt `Task_E_Compliance_Supply_Chain` from workspace `app.py`, `init_db.py`, `schema.sql`, and `README.txt` (as `readme.txt`), with path-safe SQLite handling; copied `static/css/style.css`; ran `init_db.py` to create `database.db`. Tasks C and D remain removed until new instructions arrive.
- 2026-04-25: Rebuilt Task C with non-generic evidence: added CI workflow (`task-c-static-analysis.yml`), generated fresh Semgrep JSON artifact, and produced rule-family triage log covering duplicates, contextual accepted risks, and must-fix issues.
