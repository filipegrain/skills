<!-- Template: copy to the repository root as AGENTS.md.
Replace every [placeholder]. Keep only pointers whose targets exist.
A section with nothing project-specific says "Not applicable to this project."
Never invent content. -->

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

### Installation

```bash
[actual installation command]
```

### Development

```bash
[actual development command]
```

### Build

```bash
[actual build command]
```

### Important Commands

```text
[command] — [purpose]
[command] — [purpose]
```

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

Before completing a change:

- Run relevant tests.
- Run the project's type checker.
- Run linting when applicable.
- Review the final diff.

Do not claim validation was performed if the command was not actually executed.

---

## Code Standards

### General

- Follow existing project conventions.
- Prefer existing utilities over duplicating functionality.
- Keep changes scoped to the requested task.
- Avoid unnecessary dependencies.
- Do not modify generated files manually.

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

### Database

[Database technology.]

### Schema

[Important schema information.]

### Migrations

[Migration system and rules.]

### Rules

- Use migrations for schema changes.
- Do not modify released migrations unless explicitly required.
- Follow existing database naming conventions.
- Do not execute destructive operations against production.

Detailed documentation:

- `docs/architecture/database.md`
- `docs/development/database.md`

---

## Documentation

Project documentation is organized under:

```text
docs/
├── architecture/
├── development/
├── decisions/
└── plans/
    ├── active/
    └── completed/
```

### Documentation Rules

- Stable architectural knowledge lives in `docs/architecture/`.
- Operational procedures live in `docs/development/`.
- Significant architectural decisions are recorded in `docs/decisions/`.
- Temporary implementation plans live in `docs/plans/active/` and move to `docs/plans/completed/` when done.
- `AGENTS.md` holds rules and navigation; `docs/` holds detailed knowledge.
- A piece of knowledge lives in exactly one place.

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
- Do not discard unrelated user changes.
- Review the final diff before completing a task.

---

## Security

- Never commit credentials, tokens, private keys, or secrets.
- Do not expose credentials in logs or documentation.
- Do not disable security controls merely to make a task pass.
- Treat production credentials and production data as sensitive.
- Follow existing authentication and authorization mechanisms.

Additional security documentation:

- `[path]`

---

## Agent Workflow

When starting a task:

- Read this `AGENTS.md`.
- Identify the relevant project area.
- Read any applicable nested `AGENTS.md`.
- Read relevant documentation under `docs/`.
- Inspect existing implementation before creating new code.
- Make the smallest appropriate change.
- Run relevant validation.
- Review the final diff.
- Report validation results accurately.

### For Complex Tasks

- Create a plan under `docs/plans/active/`.
- Define objectives and constraints.
- Implement the change.
- Validate the implementation.
- Update relevant documentation.
- Move the completed plan to `docs/plans/completed/`.

---

## Restrictions

- Do not invent undocumented project behavior.
- Do not introduce architectural changes without justification.
- Do not modify unrelated code.
- Do not delete user changes.
- Do not expose secrets.
- Do not claim tests or commands were executed when they were not.
- Do not create duplicate documentation.
- Do not create documentation merely to fill sections of this file.
