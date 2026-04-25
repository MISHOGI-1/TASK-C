# 7021SCN Software Security

## Week 6 Lab 1 — Automating Container SBOM Generation

---

## Introduction

The assessment requires you to generate a machine-readable Software Bill of Materials (SBOM) for your containerised application. Generating this manually once is an easy trick; generating it automatically on every code change is engineering. Today, you will test Anchore Syft manually within your Codespace, and then write the GitHub Actions YAML to fully automate the process and capture the JSON evidence required for your portfolio.

**Prerequisites and Setup Instructions**

- Your GitHub Codespace from the previous lab must be running.
- You must have a functional `Dockerfile` in the root of your repository.
- Your basic Flask application must successfully build via `docker build`.

---

## Step 1: The Manual Test (Running Syft in Codespaces)

Before we automate anything, we must prove the tool actually works against your specific container.

1. Open your GitHub Codespace terminal.

2. Build your local Docker image so Syft has a target to scan:

```bash
docker build -t task-e-target:latest .
```

3. Install the open-source Anchore Syft CLI tool directly into your Codespace Ubuntu environment using their official installation script:

```bash
curl -sSfL https://raw.githubusercontent.com/anchore/syft/main/install.sh | sh -s -- -b /usr/local/bin
```

4. Execute Syft against your newly built container and force it to output a standard CycloneDX JSON format:

```bash
syft docker:task-e-target:latest -o cyclonedx-json=local-sbom.json
```

*Expected Output:* Syft will deeply scan the container's operating system layers and your Python `requirements.txt`. It will generate a file named `local-sbom.json`. Type `cat local-sbom.json` to view it. You will see a massive, highly detailed JSON array listing every single dependency, version, and license inside your app.

> **Do not submit this file.** Manual generation fails the automation requirement of the rubric.

---

## Step 2: Automating the Audit (Writing the Pipeline)

Now we translate that manual command into an automated CI/CD pipeline.

1. In your Codespace, navigate to your `.github/workflows` directory.

2. Create a new file named `generate-sbom.yml`.

3. Paste the following configuration. This instructs the GitHub runner to check out your code, build the container dynamically, scan it using the official Anchore Action, and extract the JSON file:

```yaml
name: Task E - Supply Chain Audit (SBOM)

on:
  push:
    branches: [ "main", "master" ]

jobs:
  generate-sbom:
    name: Build and Scan Container
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Build local container image
        run: docker build -t temp-target:latest .

      - name: Run Anchore Syft
        uses: anchore/sbom-action@v0
        with:
          image: "temp-target:latest"
          format: "cyclonedx-json"
          output-file: "sbom.json"

      - name: Save Artifact for Auditors
        uses: actions/upload-artifact@v4
        with:
          name: cyclonedx-sbom
          path: sbom.json
```

4. Save the file, commit your changes, and push to GitHub:

```bash
git add .github/workflows/generate-sbom.yml
git commit -m "Automate SBOM generation for Task E"
git push
```

*Expected Output:* Navigate to the **Actions** tab on your GitHub repository. The "Task E - Supply Chain Audit" workflow will trigger. Wait for it to turn green.

---

## Step 3: Extracting the Evidence

Management does not care about your YAML; they care about the legal compliance artifact it produces.

1. Click on the successful workflow run you just triggered in the **Actions** tab.
2. Scroll to the very bottom of the run summary page.
3. Under the **Artifacts** header, you will see a downloadable zip file named `cyclonedx-sbom`.
4. Download this file. **This is your primary technical evidence for Task E.** Extract it, verify it contains your `sbom.json`, and keep it safe for your final portfolio submission.

---

## Troubleshooting Common Errors

- **Error response from daemon: pull access denied** — Your GitHub Action failed at the Syft scanning step because it tried to pull an image from the internet instead of scanning the one you just built. Ensure the image name in the `docker build` step perfectly matches the `image:` parameter in the `anchore/sbom-action` step (e.g., `temp-target:latest`).
- **Artifact is Missing** — If the pipeline passes but there is no download link at the bottom, your `actions/upload-artifact` step failed to find the file. Ensure the `output-file` name in the Syft step exactly matches the `path` name in the artifact step.
- **Empty JSON File** — If your `sbom.json` is only 2 kilobytes, your Dockerfile is likely broken and didn't install any of your Python dependencies. Go back to Lab 2 and fix your build.

---

## Challenge Tasks

### Challenge 1: Vulnerability Scanning (Aqua Trivy)

An SBOM tells you *what* is in your container, but it doesn't tell you if it's currently on fire. Research **Aqua Trivy**. Add a new job to your pipeline that takes the generated `sbom.json` file and scans it against the CVE database using the official Trivy GitHub Action. Have it output a table of known vulnerabilities.

### Challenge 2: Breaking the Build on Criticals

Auditors love SBOMs, but security engineers want to stop bad code from deploying. Configure your Trivy step (from Challenge 1) to explicitly exit with a code of `1` (which turns the pipeline RED) if it detects any vulnerabilities with a `"CRITICAL"` severity rating.

### Challenge 3: Cryptographic Signing (Cosign)

How does an auditor know your `sbom.json` wasn't tampered with after it was generated? Research **Sigstore Cosign**. Add a step to your pipeline that cryptographically signs the generated SBOM artifact before it is uploaded, ensuring its absolute provenance.

---

*This document is intended for Coventry University Group students for their own use in their work for this module. It should not be passed to third parties or posted on any website. — Jeffrey Ting*
