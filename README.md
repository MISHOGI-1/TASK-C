# Task C — Semgrep outcomes and pipeline failure (technical explanation)

This document is **separate from the main coursework report** (for example, a 500-word write-up). It exists for portfolio evidence, triage, and markers who want **line-level reasoning** tied to your CI and Semgrep Cloud results—not a generic “we ran a scanner” summary.

---

## What failed and why

Your GitHub Actions run shows **two jobs**, both ending in **Failure**: **Semgrep CI (Cloud)** and **Semgrep Scan (JSON Artifact)**. That outcome is expected once Semgrep is configured to **treat security findings as blocking** rather than advisory. In practice, Semgrep exits with a non-zero status when it detects rule violations under your chosen policy (for example, `semgrep ci` in the Cloud-connected job, and `--error` on the local `semgrep scan` path). A red workflow therefore means: **the scanner produced at least one finding that your CI configuration classifies as unacceptable**, not that GitHub Actions itself is misconfigured.

The run still produced **at least one workflow artifact**, which matters for Task C evidence: you can show **machine-readable output** (JSON and/or SARIF) even when the build is red, proving the scan ran and produced auditable results rather than a silent skip.

---

## What Semgrep Cloud is reporting (evidence-led)

Your Semgrep Cloud view for `MISHOGI-1/TASK-C` on `main` reports **111 matching findings**. The dashboard highlights two prominent clusters:

### 1. Flask SQL injection (Critical severity — 16 occurrences)

These align with a consistent pattern in the application: **SQL strings built with user-controlled or request-derived values interpolated into queries** executed via `sqlite3` connection calls. The Cloud UI lists concrete anchors such as **`app.py` lines 22, 99, 141, 193, 221** (with additional occurrences grouped under further findings).

**Assessment:** these are **true positives at the static-analysis level** for an intentionally vulnerable teaching application: the code demonstrates classic injection surfaces (cookie-derived username, form fields, route parameters) concatenated into SQL. A distinction-level triage does not argue the tool is wrong; it explains **why the pattern matches**, **what attacker capability it implies**, and **what a production fix would be** (parameterized queries / bound parameters, strict input validation, least-privilege database accounts, and removing query string assembly from request data).

### 2. `sqlalchemy-execute-raw-query` (Low severity — 16 occurrences)

This cluster illustrates **tool behaviour versus project reality**. The vulnerable Flask app uses **`sqlite3` + string-built SQL**, not SQLAlchemy ORM code. Semgrep may still surface this rule where the analyzer matches a **generic “execute raw SQL” shape** or where rulesets overlap in coverage.

**Assessment:** treat these as **secondary signals**: they reinforce the same underlying issue (unsafe query construction), but the rule name can be **misleading** relative to the actual dependency stack. That mismatch is an example of **intelligent assessment of tool limitations**: not every alert label is perfectly calibrated to your architecture.

---

## Why “111 findings” is not the same as “111 distinct vulnerabilities”

A large total count often includes **duplicates across rules**, **multiple findings per line**, **related variants** (SQLi versus raw-query warnings), and **breadth-first rulesets** (for example OWASP Top 10 style packs combined with Flask-oriented rules). For Task C, the defensible story is not the headline number; it is **a scoped set of representative issues** with **line-level mapping** and a clear statement of **which items are equivalent root causes** versus **independent weaknesses** (for example, repeated SQL concatenation patterns across routes versus separate classes of issues such as XSS or insecure session handling if those appear elsewhere in the full scan output).

---

## Triage stance (what you can claim credibly)

- **True positive (primary):** dynamic SQL construction in `app.py` at the cited line anchors—consistent with Semgrep’s SQL injection reporting and consistent with OWASP injection risk.
- **Partially redundant / naming mismatch:** `sqlalchemy-execute-raw-query` findings should be triaged as **overlapping evidence of the same unsafe SQL practice**, while explicitly noting **SQLAlchemy may not be in use**—this shows understanding of **rule applicability limits**.
- **CI failure reason:** policy-driven enforcement (Cloud `semgrep ci` plus local scan with error-on-findings), which is appropriate for a security gate, provided the submission explains **what is being gated** and **what would change in a real SDLC** (fix-first, suppress-only with governance, baseline management for legacy code).

---

## Tool limitations (brief, non-generic)

- **Architecture labels versus actual libraries:** rules may reference SQLAlchemy while the code uses `sqlite3`.
- **Taint precision:** static analysis may miss some flows or over-approximate others; triage should mention **dataflow assumptions** (what Semgrep can prove versus what still needs manual review).
- **Ruleset breadth:** combining OWASP-style packs with Flask-oriented rules increases recall but also increases **clustered duplicates** unless findings are consolidated for reporting.

---

## How this satisfies Task C expectations

Markers should see: **automation** (GitHub Actions workflow), **real scan output** (workflow artifacts and/or Semgrep Cloud project view), and **judgement** (true positives, duplicates, rule-name mismatches, and what you would change in production)—not a bulk count with no interpretation.

For day-to-day development instructions (install, run the app), see `README.txt`.
