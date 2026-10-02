<!-- Template: copy to the repository root as AGENTS.md.
Replace every [placeholder] with a fact verified in the repository: a manifest, config, script, migration, or existing doc.
A section with nothing project-specific says "Not applicable to this project." Delete every pointer whose target does not exist.
Keep this file lean: it is loaded into every agent session, so a line earns its place only by changing behaviour versus the agent's default. -->

# AGENTS.md

## Project

### Overview

[Short factual description of the project.]

### Technology

- Language: [language]
- Runtime: [runtime]
- Framework: [framework]
- Database: [database]
- Package manager: [package manager]

---

## Architecture

### Overview

[Short description of the system architecture.]

### Main Components

- `[component]` — [responsibility]

### Architecture Documentation

- `docs/architecture/[document].md`

---

## Repository Structure

```text
[repository tree showing only important directories]
```

### Important Directories

| Directory | Purpose |
|---|---|
| `[path]` | [purpose] |

---

## Development

### Commands

```bash
[actual installation command]
[actual development command]
[actual build command]
```

List only commands a manifest does not make obvious, plus conventions such as the package manager when several are possible.

Detailed development documentation:

- `docs/development/[document].md`

---

## Testing

### Test Commands

```bash
[actual test command]
```

### Test Structure

[Description of how tests are organized.]

### Validation

- Run the project's tests, type checker, and linter as configured.
- Report exactly what ran; a check that did not run is reported as not run.

---

## Code Standards

### General

[Project-specific conventions.]

### Language

[Project-specific language conventions.]

### Naming

[Project-specific naming conventions.]

### Error Handling

[Project-specific error-handling rules.]

### Architecture Rules

[Project-specific architectural constraints.]

---

## Database

### Schema

[Database technology and important schema information.]

### Migrations

[Project's migration system.]

### Rules

- Never run destructive operations against production.

Detailed documentation:

- `docs/architecture/database.md`
- `docs/development/database.md`

---

## Documentation

Project documentation is organized under:

```text
docs/
├── architecture/   how the system works
├── development/    setup, testing, debugging, deployment procedures
├── decisions/            sequential decisions: 0001-slug.md
└── plans/
    ├── active/
    └── completed/
```

Show only the directories that exist.

### Documentation Rules

- Rules and navigation live in this file; detailed knowledge lives in `docs/`.
- Each fact lives in exactly one place.
- A plan moves from `docs/plans/active/` to `docs/plans/completed/` when done.
- Conventions owned by other tools stay where they are and are.

---

## Git

### Branching

[Project branching strategy.]

### Commits

[Project commit conventions.]

### Pull Requests

[Project pull request requirements.]

### Rules

- Do not rewrite shared history without explicit authorization.

---

## Security

- Never commit credentials, tokens, private keys, or secrets.
- Treat production credentials and data as sensitive.

---

## Agent Workflow

- Read the nearest nested `AGENTS.md` and any relevant documentation under `docs/` before editing.

---

## Restrictions

- Verify a missing fact in the repository rather than assume it.
- Do not create documentation merely to fill a section.
