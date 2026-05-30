# GitHub Organization Profile & README Design
## Universitas Gunadarma — HPC & AI Hub

**Date:** 2026-05-30  
**Status:** Approved  
**Scope:** `.github` repository for GitHub Organization profile, member onboarding, and community health files

---

## Overview

This spec defines the structure and content of the `.github` repository for the Universitas Gunadarma HPC & AI Hub GitHub Organization. The repository serves as the single source of truth for org-wide standards, public-facing identity, and member onboarding.

The GitHub Organization hosts work related to High-Performance Computing (HPC), AI research, Big Data, and the Nvidia DGX infrastructure operated by Universitas Gunadarma.

---

## Repository Structure

The repo is named `.github` within the GitHub Organization. Community health files placed here automatically apply to all repositories in the org without needing to be duplicated.

```
.github/
├── profile/
│   └── README.md                  # Public: rendered on the org's GitHub page
│
├── README.md                      # Internal: member onboarding & org guide
│
├── CONTRIBUTING.md                # Contribution standards (org-wide)
│
├── SECURITY.md                    # Security policy & vulnerability reporting
│
├── PULL_REQUEST_TEMPLATE.md       # Standard PR checklist (org-wide)
│
└── ISSUE_TEMPLATE/
    ├── bug_report.md              # Bug report template
    ├── feature_request.md         # Feature request template
    └── research_proposal.md       # HPC/AI research proposal template
```

---

## File Specifications

### `profile/README.md` — Public Organization Profile

**Language:** English only.  
**Tone:** Clean and professional. Minimal emoji use — at most 2–3 for navigational clarity, or none at all. No AI-generated filler text.  
**Visual style:** Hybrid — strong visual header with animated tagline, followed by dense and informative content.

**Section order:**

1. **Header**
   - Full organization name in large typography
   - Single sharp tagline (not marketing copy)
   - Animated rotating text via `readme-typing-svg`: cycles through `High-Performance Computing`, `Deep Learning`, `Big Data`, `AI Research`
   - Badge row: Nvidia DGX Partner, relevant tech stack badges (Python, PyTorch, CUDA), org status badge

2. **About**
   - 2–3 tight paragraphs: who we are, what infrastructure we operate, why it matters
   - Written as prose paragraphs, not bullet lists — conveys more authority

3. **Infrastructure**
   - Clean table with columns: Machine, GPU Count, VRAM, Primary Use Case
   - Rows:
     - Nvidia DGX-1: 8× V100, 128 GB total, Training & Inference
     - Nvidia DGX A100 (×2): 8× A100, 320 GB total, Training / Inference / Analytics

4. **Programs**
   - Four items, each with a name, one-sentence description, and link:
     - Praktikum DGX — student access to supercomputer in coursework
     - AI Center of Excellence — Matching Fund Kedaireka initiative
     - Nvidia DLI Training — certified deep learning training for students and faculty
     - Workshop Series — Fundamental Python, Docker for DGX, Data Science for Non-Technical

5. **For Students / For Researchers**
   - Two clearly separated CTA columns
   - **Students:** access DGX portal, practical course schedule, getting started guide
   - **Researchers / Partners:** collaboration inquiries, research publications, contact

6. **Footer**
   - Links: Official HPC Hub, Praktikum UG, DGX Portal
   - Affiliation note: Nvidia DGX partner
   - Copyright: Universitas Gunadarma

---

### `README.md` — Internal Member Guide

**Audience:** Org members and contributors.  
**Purpose:** Orientation without needing to ask anyone.

**Section order:**

1. **Welcome & Scope**
   - One paragraph: this repo is the single source of truth for all org standards
   - Links to key documents within the repo

2. **Getting Started (Onboarding Checklist)**
   - Request DGX access via the official portal
   - Read `CONTRIBUTING.md`
   - Familiarize with the org's repository naming conventions
   - Contact PIC if questions arise

3. **Navigating the Projects Board**
   - How the org uses GitHub Projects for task tracking
   - Description of each board column: Backlog → In Progress → Review → Done
   - When to create a new issue vs. adding a card to an existing item
   - Who has authority to move cards between columns

4. **Repository Conventions**
   - Naming: `[domain]-[description]` (e.g., `hpc-training-materials`, `ai-lab-notebooks`)
   - Branch convention: `main` for stable/production, `dev` for active development
   - When to create a new repo vs. adding to an existing one

5. **Key Contacts & Resources**
   - Table: Role → Name / Contact
   - Links: DGX portal, access request form, internal documentation

---

### `CONTRIBUTING.md` — Contribution Standards

Applies org-wide to all repositories.

- **Workflow:** fork → feature branch → pull request
- **Commit message convention:** Conventional Commits format (`feat:`, `fix:`, `docs:`, `chore:`, `refactor:`)
- **Code review:** minimum 1 approval required before merge; author cannot approve own PR
- **Documentation requirement:** every repository must have a `README.md` that explains purpose and how to run the project
- **Branch naming:** `feat/`, `fix/`, `docs/` prefixes matching commit convention

---

### `SECURITY.md` — Security Policy

- **Reporting channel:** Contact the security PIC directly via WhatsApp at `[WA_CONTACT]` or email at `[SECURITY_EMAIL]`. Do not open a public GitHub issue for security vulnerabilities.
- **Response SLA:** Acknowledgement within 48 hours of initial report
- **Scope:** Covers vulnerabilities in code hosted in this org, exposure of credentials or sensitive data, and misconfigurations in HPC access controls
- **Out of scope:** General bugs, feature requests, performance issues unrelated to security

---

### `PULL_REQUEST_TEMPLATE.md`

Standard checklist applied to all PRs across the org:

- Description of changes
- Type of change: `feat` / `fix` / `docs` / `chore` / `refactor`
- Tests performed (unit tests, manual testing, or N/A with reason)
- Screenshot if UI or notebook output is changed
- Checklist: branch is up to date with `main`, no hardcoded secrets, documentation updated

---

### `ISSUE_TEMPLATE/`

**`bug_report.md`**
- Steps to reproduce
- Expected vs. actual behavior
- Environment: OS, Python version, CUDA version, DGX machine used

**`feature_request.md`**
- Problem being solved
- Proposed solution
- Alternatives considered
- Priority/urgency

**`research_proposal.md`** *(HPC-specific)*
- Research title and description
- HPC resources required: GPU hours estimate, dataset size, target machine (DGX-1 or DGX A100)
- Timeline
- Supervisor / PIC name

---

## Design Constraints

- No emojis in prose content. At most 2–3 used only for clear navigational anchors in the public README if needed.
- No placeholder filler text in final output — all sections must have real, accurate content.
- WhatsApp and email contacts in `SECURITY.md` remain as explicit placeholders (`[WA_CONTACT]`, `[SECURITY_EMAIL]`) until assigned by the org.
- The public README targets an international audience; all content in `profile/README.md` is in English.
- Internal files (`README.md`, `CONTRIBUTING.md`, etc.) may use Bahasa Indonesia where appropriate for member clarity.

---

## Verification

- All files render correctly in GitHub Markdown preview
- `profile/README.md` is confirmed visible on the org's public GitHub page
- Animated badge and typing SVG load without errors
- Community health files (CONTRIBUTING, SECURITY, ISSUE_TEMPLATE) are recognized by GitHub and shown in the org's community profile checklist
- PR and issue templates appear correctly when creating new PRs/issues in any org repo
