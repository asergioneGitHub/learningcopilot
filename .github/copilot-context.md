# Copilot Project Context

## Project Summary
- Project name: learningcopilot
- Goal: Maintain a reusable Copilot guidance baseline for Spring Boot + Angular projects.
- Main users: Developers using GitHub Copilot in VS Code.
- Non-goals: This repository itself is not a production application. Skills, agents, and prompts are designed to be applied in target Spring Boot + Angular projects.

## Tech Stack
- Guidance files: Markdown under .github
- Target stack for reuse: Spring Boot (Java) + Angular (TypeScript)
- Build tools (target projects): Maven Wrapper + npm
- Runtime constraints (target projects): Java 21, Node LTS, Windows-friendly commands

## Architecture Snapshot
- Style expected for target projects: classic layered architecture
- Backend flow: Controller -> Service -> Repository
- Frontend flow: smart/dumb components, guards/resolvers, interceptor-based HTTP cross-cutting concerns
- Integration points: REST APIs, relational DB, optional external APIs

## Key Commands (Template Repository)
- Validate markdown and links: manual review in PR
- Copilot context files to maintain:
  - .github/copilot-instructions.md
  - .github/copilot-context-template.md
  - .github/copilot-context.md

## Key Commands (Target Fullstack Projects)
- Backend run: ./mvnw spring-boot:run (Windows fallback: .\\mvnw.cmd spring-boot:run)
- Backend tests: ./mvnw test (Windows fallback: .\\mvnw.cmd test)
- Frontend create: npx.cmd -y @angular/cli@latest new frontend --directory frontend --defaults --skip-git
- Frontend run/test/build: npm run start / npm run test / npm run build

## Contracts and Rules
- API base path and versioning: /api/v1 (recommended default)
- Error response shape: { error, message, details, timestamp }
- Validation requirements: validate request DTOs/forms at boundaries
- Security requirements: no hardcoded secrets; perform security review for auth/permission/data-exposure changes
- Performance-sensitive paths: DB queries, async workflows, rendering-heavy frontend paths

## Project Conventions
- Naming conventions: descriptive names, avoid one-letter identifiers except common loop indices
- Testing conventions: unit tests for business logic, integration tests for API/repository
- Branch/PR conventions: focused PR-sized changes (~300 LOC target), include risk/impact summary
- Logging conventions: INFO normal flow, DEBUG diagnostics, WARN recoverable issues, ERROR failures; no sensitive data

## Current Priorities
- Current milestone: Build reusable Copilot operating system for similar projects
- Active tasks:
  - Keep instructions and context aligned
  - Add additional reusable config files iteratively
- Known risks/blockers:
  - Project-specific placeholders must be customized when copied to real app repos

## Copilot Guidance Notes
- Prefer these patterns: layered backend architecture, DTO boundaries, strict validation, test-first for logic changes
- Avoid these patterns: framework leakage into domain decisions, unrelated broad edits, silent assumptions
- Areas requiring clarification before coding: domain model, module boundaries, API contract details, deployment targets
