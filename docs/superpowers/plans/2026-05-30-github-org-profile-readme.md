# GitHub Org Profile & README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create all files for the `.github` repository of the Universitas Gunadarma HPC & AI Hub GitHub Organization — including public profile, internal member guide, and org-wide community health files.

**Architecture:** All files live in a single repo named `.github` on the GitHub Organization. The `profile/README.md` renders publicly on the org's GitHub page. All other files at root level are recognized by GitHub as community health files and apply org-wide automatically.

**Tech Stack:** Markdown, GitHub-flavored Markdown (GFM), shields.io badges, readme-typing-svg (via GitHub CDN), GitHub ISSUE_TEMPLATE YAML front matter.

---

## File Map

| File | Purpose | Audience |
|---|---|---|
| `.github/profile/README.md` | Public org profile page | Everyone (public) |
| `.github/README.md` | Member onboarding & org guide | Org members |
| `.github/CONTRIBUTING.md` | Contribution standards | All contributors |
| `.github/SECURITY.md` | Vulnerability reporting policy | All users |
| `.github/PULL_REQUEST_TEMPLATE.md` | Standard PR checklist | Contributors |
| `.github/ISSUE_TEMPLATE/bug_report.md` | Bug report template | Contributors |
| `.github/ISSUE_TEMPLATE/feature_request.md` | Feature request template | Contributors |
| `.github/ISSUE_TEMPLATE/research_proposal.md` | HPC/AI research proposal | Org members & researchers |

---

## Task 1: Repository Scaffold

**Files:**
- Create: `.github/profile/.gitkeep`
- Create: `.github/ISSUE_TEMPLATE/.gitkeep`

- [ ] **Step 1: Create directory structure**

  Create the two required directories with placeholder files so git tracks them:

  ```powershell
  New-Item -ItemType Directory -Force -Path ".github/profile"
  New-Item -ItemType Directory -Force -Path ".github/ISSUE_TEMPLATE"
  New-Item -ItemType File -Force -Path ".github/profile/.gitkeep"
  New-Item -ItemType File -Force -Path ".github/ISSUE_TEMPLATE/.gitkeep"
  ```

- [ ] **Step 2: Commit scaffold**

  ```bash
  git add .github
  git commit -m "chore: scaffold .github directory structure"
  ```

---

## Task 2: Public Profile README

**Files:**
- Create: `.github/profile/README.md`

- [ ] **Step 1: Create `profile/README.md`**

  Write the following content exactly:

  ````markdown
  <div align="center">

  # Universitas Gunadarma — HPC & AI Hub

  <a href="https://hpc.gunadarma.ac.id">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=16&pause=1500&color=76B900&center=true&vCenter=true&width=500&lines=High-Performance+Computing;Deep+Learning+%26+AI+Research;Big+Data+%26+Analytics;Nvidia+DGX+Infrastructure" alt="Focus areas" />
  </a>

  [![Nvidia DGX Partner](https://img.shields.io/badge/Nvidia-DGX%20Partner-76B900?style=flat-square&logo=nvidia&logoColor=white)](https://www.nvidia.com/en-us/data-center/dgx-systems/)
  [![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
  [![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)](https://pytorch.org)
  [![CUDA](https://img.shields.io/badge/CUDA-76B900?style=flat-square&logo=nvidia&logoColor=white)](https://developer.nvidia.com/cuda-toolkit)

  </div>

  ---

  ## About

  The Universitas Gunadarma HPC & AI Hub is the university's dedicated center for high-performance computing, artificial intelligence research, and data science education. We operate one of Indonesia's most capable academic HPC environments, providing students and researchers with direct access to Nvidia DGX supercomputing infrastructure.

  Our mission is to accelerate Indonesia's digital talent development through rigorous education and applied research in AI, deep learning, and large-scale data processing. We partner with Nvidia through the Deep Learning Institute (DLI) to deliver internationally certified training programs to students and faculty.

  ## Infrastructure

  | Machine | Count | GPU | Total VRAM | Primary Use |
  |---|---|---|---|---|
  | Nvidia DGX-1 | 1 | 8× Tesla V100 | 128 GB | Model training, inference |
  | Nvidia DGX A100 | 2 | 8× A100 (per unit) | 320 GB (per unit) | Training, inference, large-scale analytics |

  All systems are interconnected via Nvidia NVSwitch for high-bandwidth multi-GPU workloads.

  ## Programs

  **Praktikum DGX**
  A flagship practical course giving all Universitas Gunadarma students direct hands-on access to Nvidia DGX supercomputers as part of their curriculum.
  → [Learn more](https://praktikum.gunadarma.ac.id)

  **AI Center of Excellence**
  Established through the Matching Fund Kedaireka program to build and accelerate the AI ecosystem within the university.

  **Nvidia DLI Training**
  Official Nvidia Deep Learning Institute training and certification programs for students and faculty, covering deep learning fundamentals, computer vision, and natural language processing.
  → [Nvidia DLI](https://www.nvidia.com/en-us/training/)

  **Workshop Series**
  Regularly scheduled technical workshops including: Fundamentals of Python, Docker for Nvidia DGX, and Data Science for Non-Technical Audiences.
  → [DGX Development Portal](https://dgx.gunadarma.ac.id)

  ---

  ## For Students

  Access the Nvidia DGX supercomputers through the university's practical course program.

  - [Praktikum DGX Portal](https://praktikum.gunadarma.ac.id) — request access and view course schedule
  - [DGX Development Portal](https://dgx.gunadarma.ac.id) — documentation, guides, and resources
  - [Official HPC Hub](https://hpc.gunadarma.ac.id) — announcements and upcoming workshops

  ## For Researchers & Partners

  We welcome research collaborations and institutional partnerships in AI, HPC, and data science.

  - Open an [Issue](https://github.com/[ORG_NAME]/.github/issues/new?template=research_proposal.md) using the Research Proposal template to discuss a collaboration
  - Contact us at `[RESEARCH_EMAIL]` for partnership inquiries
  - View our affiliated programs on the [Official HPC Hub](https://hpc.gunadarma.ac.id)

  ---

  <div align="center">

  [HPC Hub](https://hpc.gunadarma.ac.id) · [Praktikum UG](https://praktikum.gunadarma.ac.id) · [DGX Portal](https://dgx.gunadarma.ac.id)

  © Universitas Gunadarma. Faculty of Computer Science & Information Technology.

  </div>
  ````

- [ ] **Step 2: Replace placeholder `[ORG_NAME]`**

  In `.github/profile/README.md`, find `[ORG_NAME]` and replace it with the actual GitHub Organization username (e.g., `ugcourse` or whatever the org handle is).

- [ ] **Step 3: Commit**

  ```bash
  git add .github/profile/README.md
  git commit -m "feat: add public organization profile README"
  ```

---

## Task 3: Internal Member Guide

**Files:**
- Create: `.github/README.md`

- [ ] **Step 1: Create `.github/README.md`**

  ```markdown
  # Universitas Gunadarma HPC & AI Hub — Member Guide

  This repository is the single source of truth for all standards, conventions, and workflows
  within this GitHub Organization. If you have a question about how we work, the answer is here
  or linked from here.

  ---

  ## Getting Started

  If you have just joined the organization, complete these steps in order:

  - [ ] Request DGX access via the [access request form](https://dgx.gunadarma.ac.id/access)
  - [ ] Read [`CONTRIBUTING.md`](./CONTRIBUTING.md) — covers workflow, commit conventions, and code review standards
  - [ ] Familiarize yourself with the repository naming conventions (see below)
  - [ ] Review the active Projects board to understand current priorities
  - [ ] Contact your PIC if you have any questions not covered here

  ---

  ## Navigating the Projects Board

  We use [GitHub Projects](https://github.com/orgs/[ORG_NAME]/projects) to track all active work
  across the organization.

  ### Board Columns

  | Column | Meaning |
  |---|---|
  | **Backlog** | Identified work not yet started — prioritized but not assigned |
  | **In Progress** | Actively being worked on — must have an assignee |
  | **Review** | Work complete, awaiting code review or stakeholder sign-off |
  | **Done** | Merged, deployed, or formally closed |

  ### Rules

  - Create a new Issue before starting any non-trivial work. Link it to the board.
  - Do not create cards directly on the board without a corresponding Issue.
  - Only the PIC or team lead moves cards to **Done**. Do not self-close work that affects others.
  - If a card has been in **Review** for more than 3 days with no action, ping the reviewer directly.

  ---

  ## Repository Conventions

  ### Naming

  All repositories follow the pattern: `[domain]-[description]`

  | Domain prefix | Use for |
  |---|---|
  | `hpc-` | HPC infrastructure, cluster configuration, job scripts |
  | `ai-` | AI/ML models, experiments, notebooks |
  | `data-` | Datasets, data pipelines, preprocessing tools |
  | `course-` | Course materials, practicum notebooks |
  | `infra-` | DevOps, Docker, environment configuration |

  Examples: `hpc-training-materials`, `ai-lab-notebooks`, `course-praktikum-dgx`

  ### Branches

  | Branch | Purpose |
  |---|---|
  | `main` | Stable. Direct pushes are not allowed. |
  | `dev` | Active development integration branch |
  | `feat/[name]` | New features |
  | `fix/[name]` | Bug fixes |
  | `docs/[name]` | Documentation-only changes |

  ### When to create a new repository

  Create a new repo when the work:
  - Has its own distinct audience or lifecycle
  - Is a standalone tool or service
  - Should be independently versioned or deployed

  Add to an existing repo when the work is a module, notebook, or closely related component
  that shares the same lifecycle as the parent project.

  ---

  ## Key Contacts & Resources

  | Role | Contact |
  |---|---|
  | HPC Infrastructure PIC | `[INFRA_PIC_NAME]` — `[INFRA_PIC_EMAIL]` |
  | Research Collaboration | `[RESEARCH_PIC_NAME]` — `[RESEARCH_PIC_EMAIL]` |
  | DLI Training Coordinator | `[DLI_PIC_NAME]` — `[DLI_PIC_EMAIL]` |
  | General Inquiries | `[GENERAL_EMAIL]` |

  ### Resource Links

  - [DGX Access Request Form](https://dgx.gunadarma.ac.id/access)
  - [Official HPC Hub](https://hpc.gunadarma.ac.id)
  - [Praktikum DGX Portal](https://praktikum.gunadarma.ac.id)
  - [DGX Development Portal](https://dgx.gunadarma.ac.id)
  - [Organization Projects Board](https://github.com/orgs/[ORG_NAME]/projects)
  ```

- [ ] **Step 2: Replace placeholder `[ORG_NAME]`**

  Replace all occurrences of `[ORG_NAME]` with the actual GitHub Organization username.

- [ ] **Step 3: Fill contact placeholders**

  Replace `[INFRA_PIC_NAME]`, `[INFRA_PIC_EMAIL]`, `[RESEARCH_PIC_NAME]`, `[RESEARCH_PIC_EMAIL]`,
  `[DLI_PIC_NAME]`, `[DLI_PIC_EMAIL]`, and `[GENERAL_EMAIL]` with real values.
  If not yet assigned, leave as-is and create an Issue to track the task.

- [ ] **Step 4: Commit**

  ```bash
  git add .github/README.md
  git commit -m "feat: add internal member onboarding guide"
  ```

---

## Task 4: Contributing Guidelines

**Files:**
- Create: `.github/CONTRIBUTING.md`

- [ ] **Step 1: Create `CONTRIBUTING.md`**

  ```markdown
  # Contributing

  This document defines the contribution standards for all repositories in the
  Universitas Gunadarma HPC & AI Hub GitHub Organization.

  ---

  ## Workflow

  1. Fork the repository (or create a branch if you have write access)
  2. Create a branch following the naming convention: `feat/`, `fix/`, `docs/`, `chore/`, `refactor/`
  3. Make your changes in focused, logical commits
  4. Open a pull request against `dev` (or `main` for documentation-only changes)
  5. Request review from at least one maintainer

  ## Commit Messages

  We use [Conventional Commits](https://www.conventionalcommits.org/).

  Format: `<type>: <short description>`

  | Type | Use for |
  |---|---|
  | `feat` | New feature or capability |
  | `fix` | Bug fix |
  | `docs` | Documentation changes only |
  | `chore` | Maintenance, dependency updates, tooling |
  | `refactor` | Code restructure with no behavior change |
  | `test` | Adding or updating tests |

  Examples:
  ```
  feat: add batch inference script for DGX A100
  fix: correct GPU memory allocation in training loop
  docs: update DGX access instructions
  ```

  ## Code Review

  - A minimum of **1 approval** is required before merging any pull request.
  - The author of a PR cannot approve their own PR.
  - Reviewers should complete review within **3 working days**. If blocked, comment to explain.
  - Merge only after CI passes (if applicable) and all review comments are resolved.

  ## Documentation

  Every repository must have a `README.md` that covers:

  - What the project does (one paragraph)
  - How to set up the environment
  - How to run the project or notebook
  - Any DGX-specific requirements (GPU count, estimated VRAM usage, estimated training time)

  ## Questions

  If something is unclear, open a Discussion or contact the PIC listed in the
  [member guide](./README.md).
  ```

- [ ] **Step 2: Commit**

  ```bash
  git add .github/CONTRIBUTING.md
  git commit -m "feat: add contribution guidelines"
  ```

---

## Task 5: Security Policy

**Files:**
- Create: `.github/SECURITY.md`

- [ ] **Step 1: Create `SECURITY.md`**

  ```markdown
  # Security Policy

  ## Reporting a Vulnerability

  Do not open a public GitHub Issue to report a security vulnerability. Public disclosure
  before a fix is available puts all users at risk.

  To report a vulnerability, contact the security PIC directly:

  - **WhatsApp:** `[WA_CONTACT]`
  - **Email:** `[SECURITY_EMAIL]`

  Provide a clear description of the issue, steps to reproduce if applicable, and any
  relevant environment details (machine, OS, CUDA version).

  ## Response Timeline

  | Stage | Target |
  |---|---|
  | Acknowledgement | Within 48 hours of initial report |
  | Status update | Within 7 days |
  | Resolution or mitigation | Dependent on severity |

  ## Scope

  The following are in scope for this policy:

  - Security vulnerabilities in code hosted in this organization's repositories
  - Accidental exposure of credentials, API keys, or sensitive data in commits or files
  - Misconfigurations that could expose HPC access controls or user data

  The following are out of scope:

  - General bugs or unexpected behavior without security impact
  - Feature requests
  - Performance issues unrelated to security
  - Social engineering attempts

  ## Disclosure

  We follow responsible disclosure. Once a fix is available, we will coordinate with the
  reporter on a disclosure timeline.
  ```

- [ ] **Step 2: Fill contact placeholders**

  Replace `[WA_CONTACT]` and `[SECURITY_EMAIL]` with actual PIC contact details.
  If not yet finalized, leave as-is and track via an internal Issue.

- [ ] **Step 3: Commit**

  ```bash
  git add .github/SECURITY.md
  git commit -m "feat: add security policy"
  ```

---

## Task 6: Pull Request Template

**Files:**
- Create: `.github/PULL_REQUEST_TEMPLATE.md`

- [ ] **Step 1: Create `PULL_REQUEST_TEMPLATE.md`**

  ```markdown
  ## Description

  <!-- What does this PR do? Why is this change needed? -->

  ## Type of Change

  - [ ] `feat` — new feature or capability
  - [ ] `fix` — bug fix
  - [ ] `docs` — documentation only
  - [ ] `chore` — maintenance or tooling
  - [ ] `refactor` — restructure without behavior change

  ## Testing

  <!-- Describe how you tested this change. If no tests apply, explain why. -->

  - [ ] Ran on DGX (specify machine: DGX-1 / DGX A100)
  - [ ] Unit tests pass
  - [ ] Notebook runs end-to-end without errors
  - [ ] N/A — documentation or config change only

  ## Checklist

  - [ ] Branch is up to date with `dev` (or `main` for docs)
  - [ ] Commit messages follow Conventional Commits format
  - [ ] No hardcoded credentials, API keys, or internal URLs
  - [ ] `README.md` updated if the interface or setup changed
  - [ ] Screenshots or output attached if this changes a notebook or UI
  ```

- [ ] **Step 2: Commit**

  ```bash
  git add .github/PULL_REQUEST_TEMPLATE.md
  git commit -m "feat: add pull request template"
  ```

---

## Task 7: Issue Templates

**Files:**
- Create: `.github/ISSUE_TEMPLATE/bug_report.md`
- Create: `.github/ISSUE_TEMPLATE/feature_request.md`
- Create: `.github/ISSUE_TEMPLATE/research_proposal.md`

- [ ] **Step 1: Create `bug_report.md`**

  ```markdown
  ---
  name: Bug Report
  about: Report unexpected behavior or an error
  labels: bug
  assignees: ''
  ---

  ## Summary

  <!-- One sentence describing the bug. -->

  ## Steps to Reproduce

  1.
  2.
  3.

  ## Expected Behavior

  ## Actual Behavior

  <!-- Include error messages or stack traces. -->

  ## Environment

  | Field | Value |
  |---|---|
  | DGX Machine | DGX-1 / DGX A100 (unit 1 or 2) |
  | OS | |
  | Python version | |
  | CUDA version | |
  | Framework & version | PyTorch x.x / TensorFlow x.x / other |

  ## Additional Context
  ```

- [ ] **Step 2: Create `feature_request.md`**

  ```markdown
  ---
  name: Feature Request
  about: Propose a new feature or improvement
  labels: enhancement
  assignees: ''
  ---

  ## Problem

  <!-- What problem does this feature solve? Be specific. -->

  ## Proposed Solution

  ## Alternatives Considered

  ## Priority

  - [ ] Low — nice to have
  - [ ] Medium — would meaningfully improve workflow
  - [ ] High — blocking current work
  ```

- [ ] **Step 3: Create `research_proposal.md`**

  ```markdown
  ---
  name: Research Proposal
  about: Propose a research project or HPC compute allocation request
  labels: research
  assignees: ''
  ---

  ## Research Title

  ## Description

  <!-- What is the research question or objective? -->

  ## HPC Resource Requirements

  | Resource | Estimate |
  |---|---|
  | Target machine | DGX-1 / DGX A100 |
  | Number of GPUs needed | |
  | Estimated GPU-hours | |
  | Dataset size | |
  | Estimated storage required | |

  ## Timeline

  | Phase | Duration |
  |---|---|
  | Data preparation | |
  | Training / experimentation | |
  | Analysis & write-up | |

  ## Supervisor / PIC

  Name:
  Email:
  Department:

  ## Additional Notes
  ```

- [ ] **Step 4: Remove `.gitkeep` placeholder from ISSUE_TEMPLATE**

  ```powershell
  Remove-Item .github/ISSUE_TEMPLATE/.gitkeep
  ```

- [ ] **Step 5: Commit all issue templates**

  ```bash
  git add .github/ISSUE_TEMPLATE/
  git commit -m "feat: add bug report, feature request, and research proposal issue templates"
  ```

---

## Task 8: Final Review & Cleanup

- [ ] **Step 1: Remove `.gitkeep` from `profile/` if still present**

  ```powershell
  Remove-Item .github/profile/.gitkeep
  git add .github/profile/.gitkeep
  git commit -m "chore: remove .gitkeep placeholder from profile/"
  ```

  Skip if already removed.

- [ ] **Step 2: Verify all placeholder values are tracked**

  Search for any remaining unresolved placeholders:

  ```powershell
  Select-String -Path ".github/**/*.md" -Pattern "\[.*\]" -Recurse
  ```

  For any placeholder still present, create a GitHub Issue to track filling it in.

- [ ] **Step 3: Push to GitHub**

  ```bash
  git log --oneline
  git push origin main
  ```

  After push, navigate to `https://github.com/[ORG_NAME]` and confirm:
  - The public README is visible on the org's page
  - The animated typing SVG loads correctly
  - All badges render without error

- [ ] **Step 4: Verify community health files are recognized**

  Go to `https://github.com/[ORG_NAME]/.github/community` and confirm GitHub recognizes:
  - Contributing guidelines
  - Security policy
  - Issue templates
  - Pull request template

---

## Placeholder Reference

All placeholders to fill before going live:

| Placeholder | File(s) | Description |
|---|---|---|
| `[ORG_NAME]` | `profile/README.md`, `README.md` | GitHub Organization username |
| `[RESEARCH_EMAIL]` | `profile/README.md` | Public research/partnership contact email |
| `[WA_CONTACT]` | `SECURITY.md` | WhatsApp contact for security PIC |
| `[SECURITY_EMAIL]` | `SECURITY.md` | Email for security reports |
| `[INFRA_PIC_NAME]` | `README.md` | Infrastructure PIC name |
| `[INFRA_PIC_EMAIL]` | `README.md` | Infrastructure PIC email |
| `[RESEARCH_PIC_NAME]` | `README.md` | Research PIC name |
| `[RESEARCH_PIC_EMAIL]` | `README.md` | Research PIC email |
| `[DLI_PIC_NAME]` | `README.md` | DLI Training coordinator name |
| `[DLI_PIC_EMAIL]` | `README.md` | DLI Training coordinator email |
| `[GENERAL_EMAIL]` | `README.md` | General inquiries email |
