# Gemini GitHub Actions

A repository of GitHub Actions powered by Gemini AI for intelligent repository automation.

## Overview

This repository contains GitHub Actions workflows that leverage Google's Gemini AI to automate common repository tasks with intelligent decision-making capabilities. These workflows demonstrate how AI can enhance your development workflow by automating code reviews, enforcing contribution guidelines, triaging issues, and more.

## Available Workflows

### 📐 PR Contribution Guidelines Enforcement

Automatically validates pull requests against your repository's `CONTRIBUTING.md` file using Gemini AI. Posts intelligent feedback as PR comments with actionable checklists for contributors.

**Features:**

- Reads and evaluates PR content against contribution guidelines
- Posts upserted comments (no duplicates) with PASS/FAIL status
- Optional workflow enforcement on violations (Set repository variable FAIL_ON_GUIDELINE_VIOLATIONS=false to disable enforcement)
- Handles complex PR content safely (quotes, newlines, etc.)

**Location:** [`examples/workflows/new_workflows/pr-contribution-guidelines.yml`](./examples/workflows/new_workflows/pr-contribution-guidelines-enforcement.yml)

## Setup

### Prerequisites

- Google Gemini API key
- Repository with contribution guidelines (`CONTRIBUTING.md`)

### Quick Start

1. Copy the desired workflow file to your repository's `.github/workflows/` directory
2. Add required secrets to repository variables:
   - `GEMINI_API_KEY` (for Gemini API access)









