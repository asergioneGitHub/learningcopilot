# Copilot-First Reusable Template

A reusable "Copilot operating system" for Spring Boot + Angular projects — instructions, context, skills, agents, and prompts that enforce consistent, high-quality AI-assisted development.

## What's Inside

### Governance
- `.github/copilot-instructions.md` — Always-on rules: architecture, security, testing, conventions.
- `.github/copilot-context.md` — Project-specific facts, priorities, and stack details.
- `.github/copilot-context-template.md` — Blank template to copy into new projects.

### Skills (`.github/skills/`)
On-demand execution playbooks and reference checklists.

**Workflow Skills** — step-by-step task execution:
- `backend-api.md` — REST endpoint end-to-end
- `backend-bugfix.md` — Bug diagnosis with regression safety
- `backend-refactor.md` — Behavior-preserving refactor
- `frontend-feature.md` — Angular feature implementation
- `contract-sync.md` — Backend/frontend contract sync
- `migration-rollout.md` — Safe schema/data migration
- `security-review.md` — Security audit checklist
- `performance-pass.md` — Performance hotspot resolution

**Reference Checklists** — best-practice quality gates:
- `java-springboot.md` — Spring Boot conventions
- `java-junit.md` — JUnit 5 testing patterns
- `angular-testing.md` — Angular 17+ testing patterns

**Prompts:**
- `ready-prompts.md` — 13 copy-paste starter prompts mapped to skills and agents.

### Agents (`.github/agents/`)
- `backend-api-reviewer.agent.md` — Reviews/guides backend API changes across architecture, contracts, security, tests, and docs.

### VS Code Configuration (`.vscode/`)
- `settings.json` — Editor defaults (format on save, organize imports, Java/TS settings)
- `tasks.json` — Backend/frontend task runners
- `extensions.json` — Recommended extensions

### Repo Management
- `.github/PULL_REQUEST_TEMPLATE.md` — PR checklist aligned with Definition of Done
- `.github/ISSUE_TEMPLATE/` — Bug report and feature request forms
- `.github/workflows/validate-markdown.yml` — CI to lint and link-check markdown on push/PR

## How to Reuse in Another Project
1. Copy `.github/` folder into the target repository.
2. Copy `.github/copilot-context-template.md` as `.github/copilot-context.md`.
3. Fill the placeholders in `copilot-context.md` with project-specific details.
4. Copy `.vscode/` folder for editor/task defaults.
5. Adjust skills and agents as needed for your stack.
6. Keep files updated as project conventions evolve.

## Prompting Pattern
```
Apply skill <name>.
<provide required inputs listed in the skill file>
```

For agents:
```
Use agent <name> for this task.
<provide inputs listed in the agent file>
```

## Target Stack
- **Backend:** Spring Boot (Java 21) + Maven
- **Frontend:** Angular 17+ (TypeScript) + npm
- **Architecture:** Layered (Controller → Service → Repository)
- **Testing:** JUnit 5 + Mockito (backend), Jasmine/Karma or Jest (frontend)
