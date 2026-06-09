# Repository Guidelines

This document describes the baseline standards for managing this repository.

## Directory Structure

```text
.
├── .editorconfig                # Baseline editor settings (root)
├── .gitattributes               # Line-ending and diff normalization
├── .gitignore                   # Ignored paths
├── .gitmessage                  # Commit message template
├── .github/                     # GitHub automation and AI tool instructions
│   ├── copilot-instructions.md
│   └── instructions/
├── docs/                        # Project documentation
└── README.md
```

This is the generic base layout — only the universal files every workspace
needs. Add directories (`src/`, `tests/`, `scripts/`, `infra/`, etc.) as the
project takes shape; **do not create empty directories**. A Workspace Toolkit
capability layer can also contribute structure for a specific language or tool.

## EditorConfig

This repository includes a root `.editorconfig` with baseline, language-agnostic
settings (charset, indentation, final newline, line length). EditorConfig
plugins search for `.editorconfig` files from the current file's directory
upward, stopping at the file marked `root = true`. Properties from closer files
override more distant ones.

To adjust code styles:

1. **Repository-wide changes:** edit the root `.editorconfig` directly.
2. **Project-specific additions:** add language-specific sections to the root
   file, or add a nested `.editorconfig` in a subdirectory for local overrides.

See the [official EditorConfig site](https://editorconfig.org/) for the format.

## Commit Messages

All commit messages follow the UPPERCASE Conventional Commits specification —
see [commit-message-guidelines.md](commit-message-guidelines.md). The
`.gitmessage` file at the repository root is the commit template.

## Branching

The branching model for this workspace is set at creation and documented in
[branching-guidelines.md](branching-guidelines.md).
