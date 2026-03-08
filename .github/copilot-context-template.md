# Copilot Project Context (Template)

Use this file as project-specific context for Copilot.
Copy this template to `.github/copilot-context.md` in each repository and replace placeholders.

## Project Summary
- Project name: <project-name>
- Goal: <what the project should achieve>
- Main users: <who uses it>
- Non-goals: <what is intentionally out of scope>

## Tech Stack
- Backend: <framework + language + version>
- Frontend: <framework + language + version>
- Database: <db type + version>
- Build tools: <maven/gradle/npm/etc>
- Runtime constraints: <java/node versions, OS constraints>

## Architecture Snapshot
- Style: <layered / hexagonal / other>
- Module boundaries: <key modules/features>
- Backend flow: <controller -> service -> repository, etc.>
- Frontend flow: <container/presentational, routing, state>
- Integration points: <external APIs, queues, storage>

## Key Commands
- Install dependencies: <commands>
- Run backend: <commands>
- Run frontend: <commands>
- Run tests: <commands>
- Lint/build: <commands>
- Windows shell notes: <.cmd fallbacks if needed>

## Contracts and Rules
- API base path and versioning: <e.g., /api/v1>
- Error response shape: <e.g., { error, message, details, timestamp }>
- Validation requirements: <DTO/form validation rules>
- Security requirements: <auth, permissions, sensitive data constraints>
- Performance-sensitive paths: <known hotspots>

## Project Conventions
- Naming conventions: <domain, code, database naming>
- Testing conventions: <unit/integration split, file naming>
- Branch/PR conventions: <review and checklist expectations>
- Logging conventions: <levels and sensitive data policy>

## Current Priorities
- Current milestone: <milestone>
- Active tasks: <short list>
- Known risks/blockers: <short list>

## Copilot Guidance Notes
- Prefer these patterns: <approved patterns>
- Avoid these patterns: <forbidden/legacy patterns>
- Areas requiring clarification before coding: <ambiguous domains>

## Available Skills and Agents
- Skills: see `.github/skills/README.md` for workflow playbooks and reference checklists.
- Agents: see `.github/agents/README.md` for role-based reviewers and guides.
- Prompts: see `.github/skills/ready-prompts.md` for copy-paste starters.
