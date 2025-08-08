# Enforce Contribution Guidelines (PR)

**Author:** [@jasmeetsb](https://github.com/jasmeetsb)

**Repository:** [jasmeetsb/gemini-github-actions](https://github.com/jasmeetsb/gemini-github-actions)

**Category:** Project Management

Automates validation of pull requests against your repository's CONTRIBUTING.md using the Google Gemini CLI. The workflow posts a single upserted PR comment indicating PASS/FAIL with a concise checklist of actionable items, and can optionally fail the job to enforce compliance.

**Key Features:**

- Reads and evaluates PR title, body, and diff against CONTRIBUTING.md
- Posts a single PR comment with a visible PASS/FAIL marker in Comment Title and details of compliance status in the comment body
- Optional enforcement: fail the workflow when violations are detected

**Setup Requirements:**
- Copy [workflows/contribution-guidelines-compliance/pr-contribution-guidelines-enforcement.yml](./pr-contribution-guidelines-enforcement.yml) to your .github/workflows/ folder.
- Secrets:
  - `GEMINI_API_KEY` 
- File: `CONTRIBUTING.md` at the repository root (update the path in the prompt if different)
- (Optional) Repository variable `FAIL_ON_GUIDELINE_VIOLATIONS=true` to fail the job on violations


**Workflow File:**

- Example location in this repo: [workflows/contribution-guidelines-compliance/pr-contribution-guidelines-enforcement.yml](./pr-contribution-guidelines-enforcement.yml)
- Typical usage in a consumer repo: `.github/workflows/pr-contribution-guidelines-enforcement.yml` (copy the file and adjust settings/secrets as needed)
