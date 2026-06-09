# Branching Guidelines

This workspace uses a **GitHub Flow** branching model: a single permanent `main`
branch, with short-lived feature branches that merge back into `main` through
pull requests. There is no long-running `dev` integration branch.

> **Why GitHub Flow?** GitHub Flow fits **continuously-delivered** software where
> only the latest version runs — the common case. Software that is **explicitly
> versioned** or must **support multiple versions in the wild** (e.g. a published
> library) is a better fit for Gitflow — add a `dev` integration branch and cut
> releases from `dev` into `main`. The choice is by release model, not tech stack.

## Branch Naming Convention

Branch-name prefixes for ordinary work follow the **global two-prefix default** —
see `git-branch-naming-conventions.md` (deployed to `~/.claude/`): `bug/` for
fixes, `feature/` for everything else, named `<prefix>/<issue#>-<short-description>`.
Lowercase, hyphen-separated, short slugs; issue number required where one exists.

## Workflow

### Permanent Branch

| Branch | Purpose | Protection |
|--------|---------|------------|
| `main` | The single source of truth; always releasable | PR required, no direct push |

`main` is the default branch. All work branches off it and returns to it via PR.

### Feature Workflow

Standard flow for all new work — features, fixes, docs, maintenance:

```
1. Create branch from main:    git checkout main && git checkout -b feature/5-add-thing
2. Do work, commit:            git add ... && git commit
3. Push branch:                git push -u origin feature/5-add-thing
4. Create PR targeting main:   gh pr create --base main
5. Review and merge PR
6. Delete the feature branch
```

All branches target `main`. There is no intermediate integration branch.

**Closing an issue from a feature merge.** `main` is the default branch, so a
`Closes #N` keyword in the **`feature → main` PR body** fires and auto-closes the
issue. The full per-model carrier rules — and when to defer to `References #N`
instead — live in `~/.claude/commit-workflow-checklist.md`
§ Closing-Keyword Convention.

## Versioning & Tagging

Stable `vMAJOR.MINOR.PATCH` tags are cut from `main`. **How releases are cut and
how the version advances** — manual tagging vs. automated GitVersion — lives in
`docs/version-management.md`. That file is the single source of truth for the
release cadence; this section owns only the branch topology (stable tags come
from `main`).

## Merge Strategy

- **Default merge type:** Standard merge commit (`--merge`). Preserves full commit history.
- **Squash merges:** Only when explicitly requested (e.g., to collapse a noisy feature branch). Never the default.

## Branch Cleanup

Branches should be deleted once they've served their purpose, but not prematurely.

| Scenario | Action | Why |
|----------|--------|-----|
| PR merged to `main` | Delete branch (remote + local) | Commits preserved in `main`, branch served its purpose |
| PR closed without merge | Keep branch | May be closed for rework, rebasing, or a cleaner merge approach |
| Long-running feature | Keep alive, rebase on `main` periodically | Avoid merge conflicts at PR time |

### AI Tool Behavior

When merging a PR (at the user's request), AI tools must include the branch
cleanup action in their merge notification. For example:

> "PR #22 merged to `main`. Deleted remote branch `feature/22-thing`. Switching to `main` and cleaning up local branch."

Always state what will happen to the branch so the user can intervene if needed.

## Quick Reference

| I want to... | Branch from | Name pattern | PR target |
|--------------|-------------|--------------|-----------|
| Add a feature, update docs, or do maintenance | `main` | `feature/<#>-<desc>` | `main` |
| Fix a bug | `main` | `bug/<#>-<desc>` | `main` |
