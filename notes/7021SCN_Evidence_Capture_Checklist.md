# 7021SCN Evidence Capture Checklist

Every screenshot, log, and output artifact required for distinction-level submission. Check each item off as captured. File names are suggested conventions; save all evidence into the respective task folder.

---

## Task A - Vulnerability Discovery and Remediation

| # | Evidence Item | Filename | Status |
|---|---|---|---|
| A1 | Terminal: compile `vulnerable.c` with safety checks disabled (`gcc -fno-stack-protector -z execstack -o vulnerable vulnerable.c`) | `evidence-compile-vulnerable.png` | [ ] |
| A2 | Terminal: run `./vulnerable` with normal input showing expected output | `evidence-run-normal.png` | [ ] |
| A3 | Terminal: run `./vulnerable` with oversized input showing crash/corruption | `evidence-run-overflow.png` | [ ] |
| A4 | Terminal: compile `fixed.c` (`gcc -o fixed fixed.c`) | `evidence-compile-fixed.png` | [ ] |
| A5 | Terminal: run `./fixed` with normal input showing expected output | `evidence-fixed-normal.png` | [ ] |
| A6 | Terminal: run `./fixed` with oversized input showing safe rejection | `evidence-fixed-rejected.png` | [ ] |

**Save all to:** `Task_A_Vulnerability_Remediation/`

---

## Task B - Threat Modelling and SDLC

| # | Evidence Item | Filename | Status |
|---|---|---|---|
| B1 | DFD diagram (already created as `DFD_StudentHub.md`) | `DFD_StudentHub.md` | [x] |
| B2 | Optional: visual DFD exported from MS Threat Modeling Tool or OWASP Threat Dragon | `evidence-dfd-tool-export.png` | [ ] |
| B3 | STRIDE threat table (already in README.md) | Inline in `README.md` | [x] |
| B4 | DREAD prioritization table (already in README.md) | Inline in `README.md` | [x] |

**Save all to:** `Task_B_Threat_Modelling_SDLC/`

---

## Task C - Automated Security Testing

| # | Evidence Item | Filename | Status |
|---|---|---|---|
| C1 | Screenshot: GitHub Actions pipeline run (green/red status) | `evidence-ci-pipeline-run.png` | [ ] |
| C2 | Screenshot: Semgrep scan output in terminal or CI log | `evidence-semgrep-terminal-output.png` | [ ] |
| C3 | JSON scan results artifact (already included) | `scan-output/semgrep-results.json` | [x] |
| C4 | Screenshot: triage decision documented in PR or issue | `evidence-triage-decision.png` | [ ] |

**Save all to:** `Task_C_Automated_Security_Testing/`

---

## Task D - Dynamic Analysis and Exploit Development

| # | Evidence Item | Filename | Status |
|---|---|---|---|
| D1 | Terminal: start local Flask app (`python sample_app.py`) | `evidence-app-running.png` | [ ] |
| D2 | Browser/curl: SQLi payload sent to `/search?user=' OR '1'='1` showing unauthorized data | `evidence-sqli-exploit.png` | [ ] |
| D3 | Browser: XSS payload sent to `/echo?msg=<script>alert(1)</script>` showing script execution | `evidence-xss-exploit.png` | [ ] |
| D4 | OWASP ZAP: active scan results summary | `evidence-zap-scan-summary.png` | [ ] |
| D5 | OWASP ZAP: alert detail for SQL Injection finding | `evidence-zap-sqli-alert.png` | [ ] |
| D6 | OWASP ZAP: alert detail for XSS finding | `evidence-zap-xss-alert.png` | [ ] |
| D7 | Burp Suite: intercepted request/response for SQLi (optional, strengthens evidence) | `evidence-burp-sqli.png` | [ ] |
| D8 | Browser/curl: retest after fix applied showing safe behavior | `evidence-retest-after-fix.png` | [ ] |

**Save all to:** `Task_D_Dynamic_Analysis_Exploit/`

---

## Task E - Compliance and Supply Chain

| # | Evidence Item | Filename | Status |
|---|---|---|---|
| E1 | Terminal: Docker build command and output | `evidence-docker-build.png` | [ ] |
| E2 | Terminal: Syft SBOM generation command and output | `evidence-syft-sbom-generation.png` | [ ] |
| E3 | CycloneDX SBOM JSON artifact (already included) | `sbom-cyclonedx.json` | [x] |
| E4 | Terminal or tool: vulnerability scan against SBOM (e.g., `grype sbom:sbom-cyclonedx.json`) | `evidence-grype-vuln-scan.png` | [ ] |

**Save all to:** `Task_E_Compliance_Supply_Chain/`

---

## Report and Submission

| # | Evidence Item | Filename | Status |
|---|---|---|---|
| R1 | Final Word report placed at repo root | `Report_7021SCN.docx` | [ ] |
| R2 | Turnitin submission confirmation screenshot | `evidence-turnitin-submitted.png` | [ ] |
| R3 | Incognito browser test of public repo link | `evidence-repo-public-check.png` | [ ] |

**Save all to:** Repository root / personal records

---

## Capture Tips

- Use **Windows Snipping Tool** or **Snip & Sketch** (`Win+Shift+S`) for screenshots.
- Name files exactly as listed above for consistency.
- Ensure terminal text is legible (increase font size before capturing if needed).
- For ZAP/Burp, expand the finding detail panel before capturing.
- Timestamp is embedded in PNG metadata automatically.
