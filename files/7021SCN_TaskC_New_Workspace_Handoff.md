# Task C — New Workspace Handoff (Context Pack)

Use this document when you open a **new Cursor window** or **new Codespace** so work continues without losing requirements, constraints, or repo facts.

---

## 1) What Task C Must Satisfy (Assignment Brief)

From `Assignment_Brief_7021SCN.md`, Task C requires:

- **CI/CD pipeline configuration** that automatically runs **static analysis** on your code.
- **Output of a scan** (e.g. Semgrep or SonarQube) included as evidence.
- A **brief explanation of how you triaged false positives** (markers expect judgement, not raw dump only).

**Distinction-level expectation (rubric):** excellent application of static analysis, **intelligent assessment of tool limitations**, and clear explanation of results—not a generic tool run.

---

## 2) Instructions You Have Given the Assistant (Carry Forward)

Apply all of these in the new workspace:

1. **Distinction-level quality** — depth, evidence, critical judgement; not checklist-only prose.
2. **Non-generic Task C** — avoid “92 findings from `--config auto`” as the only story; prefer **targeted rules**, **clear scope**, **line-level triage**, and **explicit duplicate/false-positive rationale** tied to *your* files.
3. **Markdown-first** — planning and process docs live in `.md` files (you asked for this pattern earlier).
4. **Do not change these Task E paths** (locked for your portfolio layout):
   - `7021SCN_Coursework_Portfolio/Task_E_Compliance_Supply_Chain/app.py`
   - `7021SCN_Coursework_Portfolio/Task_E_Compliance_Supply_Chain/database.db`
   - `7021SCN_Coursework_Portfolio/Task_E_Compliance_Supply_Chain/init_db.py`
   - `7021SCN_Coursework_Portfolio/Task_E_Compliance_Supply_Chain/requirements.txt`
   - `7021SCN_Coursework_Portfolio/Task_E_Compliance_Supply_Chain/schema.sql`  
   Task C may **scan** these paths; it must not **rewrite** those files unless you explicitly decide to remediate later.
5. **You will add lab materials in the new space** — after you add them, update scan scope, rules, and triage to reference **lab filenames and exercises**, not broad auto-config noise.

---

## 3) Reference Documents Already in This Project (Read in New Window)

| Document | Role |
|---|---|
| `Assignment_Brief_7021SCN.md` | Official requirements and submission rules |
| `7021SCN_Assignment_Directions.md` | Consolidated brief + MLO + rubric notes |
| `7021SCN_Distinction_Checklist.md` | Process and quality gates |
| `7021SCN_Evidence_Capture_Checklist.md` | Screenshot/log naming for submission |
| `7021SCN_Week_6_Lab_1_Automating_Container_SBOM_Generation.md` | Task E / SBOM automation pattern (GitHub Actions, artifacts) |
| `7021SCN_Week_6_Lab_2_Compliance_Mapping.md` | SSDF mapping discipline (evidence-led, non-Wikipedia) |
| `7021SCN_Week1_Lecture.md`, `7021SCN_Week2_Lecture1_ThreatModelling.md`, `7021SCN_Week2_Lecture2_SDLC_Architecture.md` | CIA, OWASP, STRIDE, SDLC framing for report |
| `notes/7021SCN_Report_Documentation_Live.md` | Living evidence map (update when Task C changes) |
| `7021SCN_Coursework_Portfolio/README.md` | Portfolio index |

---

## 4) Current Task C State in This Repo (Facts)

### Present

- `7021SCN_Coursework_Portfolio/Task_C_Automated_Security_Testing/README.md` — maps brief to artifacts; still references `scan-output/semgrep-results.json` and `triage-log.md`.
- `7021SCN_Coursework_Portfolio/Task_C_Automated_Security_Testing/task-c-static-analysis.yml` — **copy of** the Semgrep CI workflow (see section 5).

### Intentionally removed (per your request)

- `7021SCN_Coursework_Portfolio/Task_C_Automated_Security_Testing/scan-output/semgrep-results.json` — deleted; prior run was too generic/noisy.
- `7021SCN_Coursework_Portfolio/Task_C_Automated_Security_Testing/triage-log.md` — deleted; to be replaced with **non-generic** triage tied to new scan strategy.

### Scan scope used previously (for context only)

- `7021SCN_Coursework_Portfolio/Task_A_Vulnerability_Remediation/`
- `7021SCN_Coursework_Portfolio/Task_E_Compliance_Supply_Chain/`

---

## 5) Critical Repo Fact — GitHub Actions Workflow Location

**GitHub only runs workflows from:**

`.github/workflows/*.yml`

You currently have a workflow file at:

`7021SCN_Coursework_Portfolio/Task_C_Automated_Security_Testing/task-c-static-analysis.yml`

That path is **documentation-friendly** but **will not execute in GitHub Actions** until the same content exists under `.github/workflows/`.

**First action in new workspace:**

1. Ensure `.github/workflows/task-c-static-analysis.yml` exists (same content as the Task C copy, or move and commit one canonical file).
2. Delete or clearly label the Task C folder copy as “reference only” to avoid confusion.

The portfolio `README.md` currently cites `.github/workflows/task-c-static-analysis.yml` — align the repo to that.

---

## 6) Non-Generic Task C Strategy (Recommended After Labs Land)

When your new lab files are in the repo:

1. **Define scan scope explicitly**  
   Example: only `Task_E_Compliance_Supply_Chain/app.py` + `Task_A_Vulnerability_Remediation/vulnerable.c` + specific lab files—**not** whole trees unless justified.

2. **Prefer a custom ruleset** over raw `--config auto` alone  
   - `7021SCN_Coursework_Portfolio/Task_C_Automated_Security_Testing/semgrep.yml` with a small number of **high-signal** rules (SQLi, XSS, dangerous C APIs, Dockerfile USER).  
   - Optionally add `--config auto` as a second job *if* you can triage it.

3. **Produce two artifacts** (strong distinction signal)  
   - `scan-output/semgrep-sarif.json` (machine interchange)  
   - `scan-output/semgrep-results.json` (human review / legacy)  
   Or one JSON + a short `triage-log.md` that maps **rule id → file → line → decision**.

4. **Triage log must cite exact evidence**  
   For each decision: rule name, file path, line range, why true positive / false positive / duplicate / accepted lab risk, and what you would change in production.

5. **CI must upload artifacts**  
   Match naming to brief: workflow artifact + committed summary optional (markers like reproducibility).

---

## 7) Commands Snippet (After Strategy Is Final)

Local regeneration (adjust paths after labs are added):

```bash
pip install semgrep
semgrep scan --config semgrep.yml --json --output 7021SCN_Coursework_Portfolio/Task_C_Automated_Security_Testing/scan-output/semgrep-results.json <YOUR_SCOPE_PATHS>
```

---

## 8) Evidence Checklist (Task C Submission)

Capture for portfolio/report:

- [ ] Green GitHub Actions run for Task C workflow  
- [ ] Downloaded workflow artifact (JSON)  
- [ ] One readable screenshot of **specific** findings (line numbers visible)  
- [ ] `triage-log.md` (or equivalent) with **non-generic** decisions  
- [ ] Short paragraph on **tool limitations** (auto rules noise, framework mismatches, non-taint blind spots)

---

## 9) When You Add Lab Work in the New Space

Do this in order:

1. Add lab files under a clear folder (e.g. `labs/week-.../` or as your module specifies).
2. Update **scan scope** in workflow + local commands.
3. Regenerate **small, defensible** scan output + triage.
4. Update `Task_C_Automated_Security_Testing/README.md` and `notes/7021SCN_Report_Documentation_Live.md` with new evidence paths and counts.

---

## 10) One-Line Success Definition for Task C

Markers should see: **automation + real scan artifact + intelligent triage tied to your code**, not a bulk auto-scan with generic counts.

---

*End of handoff — copy this file into the new workspace root or keep it in `#SOFTWARE SECURITY#` and open it first in the new Cursor window.*
