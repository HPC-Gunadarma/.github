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
