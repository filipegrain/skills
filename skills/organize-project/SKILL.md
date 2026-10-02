---
name: organize-project
description: Organize an existing repository for AI-agent development — install the fixed-section AGENTS.md contract, add nested AGENTS.md files only where justified, and lay out docs/.
disable-model-invocation: true
---

# Organize Project

Organize a repository so any agent enters at the root `AGENTS.md` and finds every kind of rule where the **contract** says it lives: the Database section holds the database rules, the Agent Workflow section the workflow, in every repository. Install the contract by re-homing what the project already has, never dropping a rule silently.

## The contract

Root `AGENTS.md` uses these sections, in this order:

Project · Architecture · Repository Structure · Development · Testing · Code Standards · Database · Documentation · Git · Security · Agent Workflow · Restrictions

[AGENTS-TEMPLATE.md](AGENTS-TEMPLATE.md) holds the skeleton, the standing content each section carries, and the docs tree.

Every line is **verified** — read from a manifest, config, script, migration, or existing doc. Where the repository does not say, write `[Needs verification]`.

`AGENTS.md` is loaded into every future session. A line earns its place only by changing behaviour versus the agent's default; push detail behind a pointer.

## Process

### Survey — read only

Read the repository before touching it: manifests (`package.json`, `pyproject.toml`, `go.mod`, `Cargo.toml`, …), build/test/CI/Docker config, scripts, migrations, `README`, existing `docs/`, and every agent configuration — `AGENTS.md`, `CLAUDE.md`, `.cursor/`, `.github/copilot-instructions.md`, `.opencode/`. Check `git status`; record uncommitted work so no later step clobbers it.

Done when you can name the stack, the real commands, the major components, every existing doc and agent config, and the state of the worktree — and have written nothing.

### Mark the boundaries

A boundary earns a nested `AGENTS.md` only when its rules genuinely differ from the root: a different stack, architecture, test procedure, security requirement, or conventions that would overload the root file.

Done when every major component is either assigned a nested file or consciously skipped.

### Write or merge the root AGENTS.md

No root `AGENTS.md` exists: copy [AGENTS-TEMPLATE.md](AGENTS-TEMPLATE.md) and fill every section with surveyed facts, keeping its standing content.

One already exists: rewrite it into the contract rather than replacing it. Map every existing rule to its nearest section; a rule that fits no section goes in the nearest one; consciously retire the rest and list every retired rule in the report. Never drop a rule silently.

`AGENTS.md` is canonical. If a project-wide `CLAUDE.md` exists, reduce it to a pointer at `AGENTS.md`; preserve tool-specific configs (`.cursor/`, `.github/copilot-instructions.md`, `.opencode/`).

A section with nothing project-specific says "Not applicable to this project." Point only at docs that exist.

Done when all twelve sections are present in order, every old rule is placed or retired in the report, every command and path is checked against the repository, and nothing is invented.

### Write nested AGENTS.md

Same section order; the Project section becomes Scope, naming the directory the file governs. Only rules additional or more specific than the root — root rules stay in the root — and omit sections with nothing to add; the "Not applicable" rule is for the root.

Done when every boundary you marked has a file whose every line is scope-specific.

### Migrate docs

File existing documentation into the tree in [AGENTS-TEMPLATE.md](AGENTS-TEMPLATE.md), moving rather than deleting. Use `git mv` for tracked files. Preserve useful content; deduplicate only once the replacement is verified. Create a file only when it holds something real, and list only directories that exist.

Conventions owned by other tools stay in place and are linked from the Documentation section: `docs/`. Leave the worktree uncommitted; the report is the handoff.

Done when every existing doc is filed or deliberately left in place, no fact appears twice, and every doc the root references exists.

### Validate and report

Check:

- every referenced file exists
- every documented command exists in the project's manifest and uses its package manager
- paths are correct
- no secrets were added
- no `[placeholder]` or `[Needs verification]` remains unless listed in Notes
- the documented docs tree matches the directories that exist
- no instruction is duplicated; nested files are scope-only; the root order and full section set are intact

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
[Anything that could not be verified, and every rule retired during the merge.]
```
