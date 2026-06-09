# Commit Message Guidelines

This file defines this workspace's **additions** to the universal commit types
and any workspace-specific scopes. The universal types and all other commit
rules (format, attribution, workflow, approval gate) are defined in the global
`commit-workflow-checklist.md`. Repo-local types **extend** the universal set;
this file MUST NOT re-list universal types.

## Repo-Specific Types (extend the universal set)

_None yet._ This is a generic base workspace — it adds no language- or
tool-specific commit types beyond the universal set. Add rows here if the
project develops a need (e.g., `BUILD`, `CI`, `PERF`, `TEST` once a build or
test pipeline exists).

## Approved Scopes

_None defined yet._ Scopes name the area of the project a change touches
(e.g., `docs`, `config`, `build`). A generic workspace has no codebase-derived
scopes at creation. Refine this list to match the actual project structure as
it takes shape; omit the scope entirely when a change spans multiple areas or
is repository-wide.
