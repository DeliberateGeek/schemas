---
applyTo: "**"
---

# Branching Guidelines

This project uses GitHub Flow: a single permanent `main` branch with short-lived
feature branches merged back via pull requests. There is no `dev` integration
branch. See `docs/branching-guidelines.md` for the canonical specification — this
file mirrors key content for GitHub Copilot.

## Branch Naming

Format: `<prefix>/<issue#>-<short-description>` — the global two-prefix default.

| Prefix | Use when |
|--------|----------|
| `feature/` | New functionality, docs, maintenance — everything that isn't a bug fix |
| `bug/` | Bug fixes |

Examples: `feature/5-add-user-service`, `bug/10-null-ref-in-auth`, `feature/20-update-readme`

## Workflow

- All branches from `main`, and all target `main` via PR — there is no `dev` branch
- PRs required for `main` — no direct push
- One branch per issue
- Stable `vMAJOR.MINOR.PATCH` tags are cut from `main`; release cadence and version
  bumps live in `docs/version-management.md` (the single source of truth for versioning)
- Default merge type: standard merge commit (`--merge`). Squash only when explicitly requested.

## Branch Cleanup

- PR merged to `main`: delete branch (remote + local)
- PR closed without merge: keep branch (may be reworked)
- After merging, always state the branch cleanup action in the merge notification
