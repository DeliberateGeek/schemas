---
applyTo: "**"
---

# Commit Message Guidelines

This project uses UPPERCASE Conventional Commits. See `docs/commit-message-guidelines.md` for the canonical specification — this file mirrors that content for GitHub Copilot. AI-authored commit messages follow `~/.claude/commit-workflow-checklist.md` (the global checklist); this file does not redefine universal types, AI attribution, or the approval workflow.

## Format

```
TYPE(scope): description

optional body

optional footer
```

## Rules

- Types MUST be UPPERCASE
- Breaking changes: add `!` before colon (e.g. `FEAT(api)!: remove endpoint`)
- Scopes are optional, use lowercase, prefer values from the approved list below
- Description immediately follows the colon and space
- Body separated from description by a blank line
- Footers use `-` in place of whitespace in tokens (e.g. `Approved-by`)

## Repo-Specific Types (extend the universal set)

The universal types (defined in the global `commit-workflow-checklist.md`) are always available. This generic base workspace adds **no** repo-specific types yet — add them here if the project develops a need (e.g., `BUILD`, `CI`, `PERF`, `TEST` once a build or test pipeline exists).

## Approved Scopes

No scopes are defined yet — a generic workspace has no codebase-derived scopes at creation. Refine this list to match the actual project structure as it takes shape; omit the scope when a change spans multiple areas or is repository-wide.
