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

We use [GitHub Projects](https://github.com/orgs/ugcourse/projects) to track all active work
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
- [Organization Projects Board](https://github.com/orgs/ugcourse/projects)
