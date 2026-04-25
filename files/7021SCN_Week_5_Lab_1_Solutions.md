# 7021SCN Software Security

## Week 5 Lab 1 — Solutions to Challenges

---

## Challenge 1: Extracting Machine-Readable Reports

**Objective:** Management wants a dashboard, not terminal logs. You will modify your `semgrep-sast.yml` file to generate a JSON output file instead of just printing to the console. You will then add a step using the `actions/upload-artifact@v4` action to permanently save the Semgrep JSON report to the workflow run so it can be downloaded by auditors.

Auditors do not read terminal output. They expect machine-readable data (like JSON or SARIF) that can be ingested into vulnerability management dashboards like DefectDojo.

**Prerequisites:** Your completed `semgrep-sast.yml` from Step 1 of the lab.

### Step-by-Step Execution

1. Open your terminal and edit your existing pipeline file:

```
.github/workflows/semgrep-sast.yml
```

2. Replace the `steps` block with the following. This switches from the pre-packaged Semgrep action to a direct command-line execution so we can precisely control the output flags, and adds the artifact upload step:

```yaml
steps:
  - name: Checkout repository
    uses: actions/checkout@v4

  - name: Install Semgrep
    run: pip install semgrep

  - name: Run Semgrep and Export JSON
    run: |
      semgrep scan --config="p/owasp-top-ten" --json -o semgrep-report.json

  - name: Upload Semgrep Report
    uses: actions/upload-artifact@v4
    if: always()
    with:
      name: semgrep-audit-report
      path: semgrep-report.json
```

3. Save the file, commit, and push:

```bash
git add .github/workflows/semgrep-sast.yml
git commit -m "Configure JSON report extraction for auditors"
git push origin main
```

**Expected Output:** When the pipeline runs, go to the **Actions** tab in GitHub and click on the specific workflow run. Scroll to the bottom of the summary page — you will see an "Artifacts" section containing `semgrep-audit-report`. Clicking this will download a `.zip` file containing your machine-readable JSON.

**Troubleshooting:**

- **The artifact didn't upload when the build failed:** Did you forget the `if: always()` line? By default, if the `semgrep scan` step finds a vulnerability, it exits with an error code and GitHub Actions immediately aborts subsequent steps — unless you explicitly tell the upload step to run `always()`.

---

## Challenge 2: Writing Custom Security Rules

**Objective:** Default rules are good, but what if your company bans a specific library? You will create a file named `custom-rules.yaml` in your repository and write a custom Semgrep rule that specifically searches for the use of the `hashlib.md5()` function in Python and flags it as a failure. You will then update your GitHub Action to use your custom ruleset alongside the OWASP rules.

**Prerequisites:** A basic understanding of Python syntax.

### Step-by-Step Execution

1. In the root of your repository, create the custom rules file `custom-rules.yaml`.

2. Paste the following configuration. The ellipsis `...` acts as a wildcard for any arguments passed into the function:

```yaml
rules:
  - id: internal-ban-md5-hashing
    languages:
      - python
    message: "SECURITY VIOLATION: MD5 is cryptographically broken and banned by corporate policy. Use hashlib.sha256() instead."
    severity: ERROR
    pattern: hashlib.md5(...)
```

3. Save and close the file.

4. Edit your pipeline file to point to both the OWASP rules and your new custom file:

```
.github/workflows/semgrep-sast.yml
```

5. Modify the Semgrep run command from Challenge 1 to include your new config:

```yaml
  - name: Run Semgrep and Export JSON
    run: |
      semgrep scan --config="p/owasp-top-ten" --config="custom-rules.yaml" --json -o semgrep-report.json
```

6. Create a dummy Python file `bad_crypto.py` to test it, with the following offending code:

```python
import hashlib
password_hash = hashlib.md5(b"my_password").hexdigest()
```

7. Commit and push everything:

```bash
git add .
git commit -m "Implement custom rule banning MD5"
git push origin main
```

**Expected Output:** The pipeline will fail. When you check the logs, you will see your custom error message:

```
SECURITY VIOLATION: MD5 is cryptographically broken and banned by corporate policy.
```

**Troubleshooting:**

- **Semgrep ignored the custom rule:** Ensure the `--config="custom-rules.yaml"` flag points to the correct file path. If you placed the YAML file inside a subfolder, you must update the path in the pipeline command accordingly.

---

## Challenge 3: Branch Protection Enforcement

**Objective:** Right now, developers can just bypass the pipeline. You will navigate to your GitHub repository settings and set up a "Branch Protection Rule" for your `main` branch. You will require status checks to pass before merging, and select your Semgrep job as a mandatory check.

A security pipeline that developers can ignore by just clicking "Merge Anyway" is completely useless.

**Prerequisites:**

- Your GitHub repository must be **public**, or you must have a GitHub Pro/Team/Enterprise account. Branch protection rules for private repos are paywalled by GitHub.

### Step-by-Step Execution

1. In your browser, navigate to your repository on GitHub.com.
2. Click **Settings** (the gear icon at the top right of the repo).
3. On the left-hand sidebar, click **Branches**.
4. Click the **Add branch protection rule** button.
5. In the **Branch name pattern** box, type `main` (or `master`, depending on your default branch).
6. Check the box labelled **Require a pull request before merging**.
7. Check the box labelled **Require status checks to pass before merging**.
8. In the search bar that appears, type `Semgrep` or the exact name of the job you specified in your YAML file (e.g., `Run Semgrep and Export JSON`). Select it so it appears in the list of required checks.
9. Click **Create** at the bottom of the page.

### Proving It Works

1. In your local terminal, create a new branch:

```bash
git checkout -b bypass-attempt
```

2. Write some intentionally vulnerable code in a new file, commit it, and push the branch:

```bash
git add .
git commit -m "Trying to sneak in bad code"
git push origin bypass-attempt
```

3. Go to GitHub and open a **Pull Request** from `bypass-attempt` to `main`.

**Expected Output:** The Pull Request page will show the Semgrep Action running. Once it finds the vulnerability and fails, the "Merge pull request" button will turn red and become unclickable. The UI will explicitly state:

> **Required statuses must pass before merging.**

You have officially locked down the supply chain.

---

*This document is intended for Coventry University Group students for their own use in their work for this module. It should not be passed to third parties or posted on any website. — Jeffrey Ting*
