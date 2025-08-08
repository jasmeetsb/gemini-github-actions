# Enforce Contribution Guidelines (PR)

**Author:** [@jasmeetsb](https://github.com/jasmeetsb)

**Repository:** [jasmeetsb/gemini-github-actions](https://github.com/jasmeetsb/gemini-github-actions)

**Category:** Project Management

Automates validation of pull requests against your repository's CONTRIBUTING.md using the Google Gemini CLI. The workflow posts a single upserted PR comment indicating PASS/FAIL with a concise checklist of actionable items, and can optionally fail the job to enforce compliance.

**Key Features:**

- Reads and evaluates PR title, body, and diff against CONTRIBUTING.md
- Posts a single PR comment with a visible status marker: `<!-- guidelines-check: PASS|FAIL -->`
- Upserts the comment on re-runs (no duplicates)
- Optional enforcement: fail the workflow when violations are detected
- Fork-safe: supports GitHub App token (uses `actions/create-github-app-token` if configured)
- Robust handling of quotes/newlines in PR content
- Minimal permissions; uses `gh` CLI from the Gemini session for comments

**Setup Requirements:**

- Secrets:
  - `GEMINI_API_KEY` (or configure Vertex AI auth via action inputs)
- Optional (for fork PRs / elevated perms):
  - Repository variable `APP_ID`
  - Secret `APP_PRIVATE_KEY` (private key for the GitHub App)
- File: `CONTRIBUTING.md` at the repository root (update the path in the prompt if different)
- (Optional) Repository variable `FAIL_ON_GUIDELINE_VIOLATIONS=true` to fail the job on violations

**Example Use Cases:**

- Enforce PR templates, required sections, and naming conventions
- Verify docs/tests/changelog requirements per your guidelines
- Provide immediate feedback to contributors with a clear checklist

**Workflow File:**

- Example location in this repo: [workflows/contribution-guidelines-compliance/pr-contribution-guidelines.yml](./pr-contribution-guidelines-enforcement.yml)
- Typical usage in a consumer repo: `.github/workflows/pr-contribution-guidelines-enforcement.yml` (copy the file and adjust settings/secrets as needed)
