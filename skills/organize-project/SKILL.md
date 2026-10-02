---
name: organize-project
description: Organize an existing repository for AI-agent development — install the fixed-section AGENTS.md contract, add nested AGENTS.md files only where justified, and lay out docs/.
disable-model-invocation: true
---

# Organize Project

Organize a repository so any agent enters at the root `AGENTS.md` and finds every kind of rule where the **contract** says it lives: the Database section holds the database rules, the Agent Workflow section the workflow, in every repository. Install the contract without replacing what the project already does well.

## The contract

Root `AGENTS.md` uses these sections, in this order:

Project · Architecture · Repository Structure · Development · Testing · Code Standards · Database · Documentation · Git · Security · Agent Workflow · Restrictions

[AGENTS-TEMPLATE.md](AGENTS-TEMPLATE.md) holds the skeleton and the standing content each section carries.

Every line is a fact **verified** in the repository — read from a manifest, config, script, migration, or existing doc, never inferred from a directory name. Where the repository does not say, write `[Needs verification]`.

## Process

### Survey — read only

Read the repository before touching it: manifests (`package.json`, `pyproject.toml`, `go.mod`, `Cargo.toml`, …), build/test/CI/Docker config, scripts, migrations, `README`, existing `docs/`, and every agent configuration — `AGENTS.md`, `CLAUDE.md`, `.cursor/`, `.github/copilot-instructions.md`, `.opencode/`.

Done when you can name the stack, the real commands, the major components, and every existing doc and agent config — and have written nothing.

### Mark the boundaries

A boundary earns a nested `AGENTS.md` only when its rules genuinely differ from the root: a different stack, architecture, test procedure, security requirement, or conventions that would overload the root file. A directory existing is not a reason.

Done when every major component is either assigned a nested file or consciously skipped.

### Write the root AGENTS.md

Copy [AGENTS-TEMPLATE.md](AGENTS-TEMPLATE.md); fill every section with surveyed facts and keep its standing content. A section with nothing project-specific says "Not applicable to this project." Point only at docs that exist.

Done when all sections are present in order, every command and path is checked against the repository, and nothing is invented.

### Write nested AGENTS.md

Same section order; the Project section becomes Scope, naming the directory the file governs. Only rules additional or more specific than the root — root rules stay in the root — and omit sections with nothing to add.

Done when every boundary you marked has a file whose every line is scope-specific.

### Migrate docs

Classify existing documentation into the tree, moving rather than deleting:

```text
docs/
├── architecture/   how the system works
├── development/    setup, testing, debugging, deployment procedures
├── decisions/      ADR-001-….md, sequential
└── plans/
    ├── active/
    └── completed/
```

Preserve history and useful content; deduplicate only once the replacement is verified. Create a file only when it holds something real. Rules and navigation stay in `AGENTS.md`; knowledge goes in `docs/` — each fact in exactly one place. Preserve tool-specific agent configs; shared rules live in `AGENTS.md`, and a purely project-wide `CLAUDE.md` shrinks to a pointer at it.

Done when every existing doc is filed or deliberately left in place, no fact appears twice, and every doc the root references exists.

### Validate and report

Check:

- every referenced file exists
- every documented command exists and uses the project's package manager
- paths are correct
- no secrets were added
- no instruction is duplicated; nested files are scope-only; the root order is intact

Report created, updated, and preserved files with validation status per check. Claim a check passed only if it ran.

```md
## Project Organization

### Created
- `[file]`

### Updated
- `[file]`

### Nested Agent Instructions
- `[path]/AGENTS.md`

### Existing Agent Configuration
- `[file]` — preserved | updated

### Validation
- [check] — PASS | FAIL | NOT RUN

### Notes
[Anything that could not be verified.]
```
