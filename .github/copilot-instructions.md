# Copilot Instructions — {{WORKSPACE_NAME}}

{{WORKSPACE_DESCRIPTION}}

## Documentation

Project conventions live in `docs/` — read these files for authoritative guidance:

- **`docs/commit-message-guidelines.md`** — UPPERCASE Conventional Commits and approved types
- **`docs/branching-guidelines.md`** — Branching workflow and naming
- **`docs/repository-guidelines.md`** — Directory structure and baseline editor settings

## Key Conventions

- **Git:** UPPERCASE Conventional Commits; branching per `docs/branching-guidelines.md`.
- **Editor settings:** Baseline conventions enforced via `.editorconfig`.
- **Merging:** Default to standard merge commits (`--merge`). Squash only when explicitly requested.
- **PRs:** Never merge a PR unless the user explicitly asks. When asked, check whether the PR meets the branch's merge requirements before attempting. If requirements aren't met, inform the user. After merging, always state the branch cleanup action taken or planned.
