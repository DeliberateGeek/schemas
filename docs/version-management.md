# Version Management (manual)

**This workspace versions by hand.** This file is the single source of truth for
**how releases are cut and how the version advances** — `docs/branching-guidelines.md`
owns the branch *topology* (which branches exist, where stable tags are cut from) and
points here for the cadence.

> **Automated alternative:** applying the `auto-versioning` layer replaces this file
> with an automated version (GitVersion computes the SemVer and a GitHub Action tags
> `main` on every release). Until then, the manual baseline below is the release path.

## Cadence — bump at release, not per change

A version number corresponds to a **deliberate release**, not to each commit. You tag
`main` when you choose to mark a releasable point; intervening commits are
**released-but-unversioned** until the next tag. There is no requirement to tag every
commit on `main`.

## Releasing

Stable `vMAJOR.MINOR.PATCH` tags are cut from `main` at chosen release points:

```
1. On main, at a releasable point, tag it:   git tag -a vX.Y.Z -m "Release X.Y.Z"
2. Push the tag:                             git push origin vX.Y.Z
```

- Use **annotated** tags (`-a`) only.
- Tags are **immutable** once pushed — a version number, once stamped, never moves.

## Pre-release identifiers (optional)

Pre-release identifiers (`-rc.N`, `-alpha`, `-beta`) may be tagged on `main`
directly if used. They follow SemVer item 9 and have lower precedence than the
associated stable version (`1.0.0-alpha < 1.0.0`).
