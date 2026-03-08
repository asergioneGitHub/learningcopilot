# Skills Pack

These skills are reusable task playbooks for this repository and similar Spring Boot + Angular projects.

## How to Use
- Keep governance in `.github/copilot-instructions.md`.
- Keep project-specific facts in `.github/copilot-context.md`.
- Use one skill prompt when starting a task to enforce consistent execution.

## Available Skills

### Workflow Skills
Step-by-step execution playbooks — use "Apply skill \<name\>" to drive a task end-to-end.

- `backend-api.md` — Add/update backend REST endpoint end-to-end.
- `backend-bugfix.md` — Diagnose and fix backend bugs with regression safety.
- `backend-refactor.md` — Refactor backend code without behavior changes.
- `frontend-feature.md` — Implement Angular feature with routing/state/http conventions.
- `contract-sync.md` — Apply backend API changes and sync frontend contracts.
- `migration-rollout.md` — Design and implement safe schema/data migrations.
- `security-review.md` — Proactively audit endpoints/features for security gaps.
- `performance-pass.md` — Identify and resolve performance hotspots with trade-off analysis.

### Reference Checklists
Best-practice guides — use alongside any workflow skill for quality checks and review.

- `java-springboot.md` — Spring Boot best-practice checklist for implementation/review.
- `java-junit.md` — JUnit 5 testing checklist for unit/integration test quality.
- `angular-testing.md` — Angular testing checklist for component/service/routing test quality.

## Quick-Start Prompts
See `ready-prompts.md` for copy-paste prompt templates mapped to the skills above.

## Prompting Pattern
Use: "Apply skill <name>" then provide inputs listed in that skill file.

Example:
"Apply skill backend-api. Add POST /api/v1/users with fields name/email, validate inputs, enforce unique email, return DTO, add unit+integration tests, and update API docs."
