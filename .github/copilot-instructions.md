# Copilot Instructions for This Workspace

## Purpose
These instructions define how GitHub Copilot should behave in this repository to maximize correctness, safety, maintainability, and delivery quality.

## Core Working Rules
- If requirements are ambiguous, ask precise clarification questions (1–3 at a time) until no open questions remain that could significantly affect implementation.
- Never make silent assumptions. If an assumption is required, list it explicitly and wait for approval before proceeding.
- Keep responses concise by default; provide more detail when requested.
- For non-trivial changes, provide brief rationale and clearly state assumptions.
- Prefer incremental, PR-sized implementation steps for large work (target ~300 lines or less per PR).

## Architecture and Design
- Enforce strict layering:
  - Controllers: HTTP/API transport concerns only.
  - Services: business logic.
  - Repositories: persistence concerns only.
- Prefer the simplest solution that satisfies requirements.
- Enforce clean naming and readability:
  - Use clear, descriptive names.
  - Avoid one-letter variables except well-known loop indices.
  - Prefer small, focused functions/methods.
- Prefer existing project stack/patterns strictly; do not introduce alternate frameworks/patterns unless explicitly approved.

## Change Management
- Broad changes are allowed when useful, but changes must remain cohesive and clearly justified.
- Avoid unrelated edits in the same task.
- Create new files/folders only when necessary, and explain why each new file is needed before creation.
- For refactors:
  - Preserve behavior by default.
  - Add/update regression tests.
  - Call out intentional behavior changes before applying them.
- For deprecated/legacy code paths:
  - Prefer marking for explicit follow-up rather than forced deletion.
  - Add clear follow-up checklist items.

## Dependency and Version Policy
- Use a strict dependency policy:
  - Prefer standard library/native capabilities first.
  - Add third-party dependencies only when clearly justified.
  - Prefer actively maintained packages.
- Before adding/upgrading dependencies, verify compatibility with current stack/runtime and warn about breaking changes.

## API, Validation, and Contracts
- Preserve API backward compatibility by default unless explicitly approved.
- Enforce strict input validation at boundaries (API DTOs/forms); never trust client input.
- When backend API contracts change, update frontend client/types/tests in the same task, or explicitly list what remains.
- Use a standard API error response structure: `{ error, message, details, timestamp }`.

## Security and Privacy
- Never hardcode secrets, tokens, or credentials.
- Use environment/config-based secret handling.
- Never log sensitive values.
- For tasks touching auth, permissions, or data exposure, perform and report a security review before completion using this checklist:
  - Access control: verify only authorized users can access.
  - Input validation: all inputs validated and sanitized.
  - Data exposure: no sensitive fields leaked in responses.
  - Logging safety: no secrets/PII in logs.
- Enforce strict privacy defaults:
  - Minimize personal data collection/retention.
  - Mask/anonymize sensitive fields in logs, examples, fixtures, and test data.

## Reliability, Performance, and Observability
- Enforce structured error handling:
  - Do not swallow exceptions.
  - Return meaningful API errors.
  - Log actionable context without sensitive data.
- Enforce concurrency/async safety:
  - Identify race-condition risks.
  - Use safe patterns (idempotency, retries, locking/transaction boundaries where appropriate).
- Performance guardrail:
  - For potentially heavy changes, provide impact note and trade-offs.
  - Ask developer whether to proceed before applying risky/high-cost approach.
- Observability guidelines:
  - Add logs/metrics for service entry/exit points, async jobs, and error paths.
  - Use appropriate log levels: INFO for normal flow, DEBUG for diagnostics, WARN for recoverable issues, ERROR for failures.
  - Recommended for important backend/async paths, but not mandatory for every change.
- Feature flags are a soft rule:
  - Prefer for risky/user-facing changes.
  - Optional for low-risk changes.

## Migration and Rollout Safety
- For schema/data migrations, use safe rollout patterns (expand/contract where applicable).
- Include rollback approach for risky changes.
- Include backup awareness note for data-affecting changes.

## Verification and Definition of Done
A task is complete only when all applicable items are satisfied:
- Code changes are implemented.
- Tests are added/updated where required (especially for business logic and bug fixes).
- Relevant checks are run (tests/lint/build/security checks as applicable).
- Related documentation is updated when behavior/setup/config changed.
- A concise risk/impact summary is provided.
- Any unresolved risks/blockers are explicitly reported.

If any required check fails:
- Do not claim completion.
- Report root cause and concrete fix options.

## Git and Safety Constraints
- Never run destructive git/history commands (for example hard reset, forced clean, or history rewrite) unless explicitly requested.

## Behavior When Uncertain
- If uncertainty remains after investigation, return clear implementation options with trade-offs instead of silently continuing.

## Testing Strategy
- Use unit tests for services/business logic; use integration tests for API endpoints and repository layers.
- Business logic changes and bug fixes always require corresponding tests.
- Test class naming: `*Test.java` (backend), `*.spec.ts` (frontend).
- Prefer mocks for external dependencies; use real (embedded) DB for repository/integration tests.

## Backend Conventions (Spring Boot)
- Always use constructor injection; never use field injection (`@Autowired` on fields).
- Never expose JPA entities directly in API responses; always use DTOs.
- Mark service methods `@Transactional` where needed; keep transactions short and focused.
- Use MapStruct or explicit manual mapping for DTO ↔ entity conversion.
- Database naming: snake_case for columns/tables, PascalCase for Java entities.
- Prefer stateless services; avoid holding request-scoped data in service fields.
- Use `@ConfigurationProperties` for typed, validated configuration binding.
- Use SLF4J with parameterized messages (`log.info("User {} created", id)`) for logging.
- Use projections or DTO queries when only partial entity data is needed.

### Package Structure
- Use package-by-feature (e.g., `com.example.user/`, `com.example.order/`), not package-by-layer.

### Exception Handling
- Use a global `@ControllerAdvice` for consistent API error responses.
- Create custom business exceptions extending `RuntimeException` for domain-specific errors.

### Validation and DTOs
- Use Bean Validation annotations (`@NotNull`, `@Size`, `@Valid`, etc.) on request DTOs.
- Validate at controller entry point with `@Valid`.

### Configuration
- Use Spring Profiles (`dev`, `test`, `prod`) for environment-specific configuration.
- Keep secrets in environment variables or external config, never in `application.properties`.

### Repository Layer
- Prefer derived query methods or `@Query` with JPQL; avoid native SQL unless necessary.
- Use specifications or custom repository methods for complex queries.

### API Design
- Use plural nouns for REST resources (e.g., `/users`, `/orders`).
- Use standard HTTP status codes consistently: 200 OK, 201 Created, 400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found, 500 Internal Server Error.

## Frontend Conventions (Angular)
- Prefer standalone components over NgModule-based components where possible.
- Use Angular signals or RxJS consistently within a feature; do not mix arbitrarily.
- Lazy-load feature modules/routes for performance.
- Use environment files for configuration; never hardcode API URLs or secrets.

### Component Architecture
- Use smart (container) components for data fetching and state; dumb (presentational) components for display only.
- Smart components pass data via inputs; dumb components emit events via outputs.

### Routing
- Use route guards (`canActivate`, `canDeactivate`) for access control.
- Use resolvers for pre-fetching critical data before route activation.
- Define routes in dedicated `*.routes.ts` files per feature.

### HTTP Handling
- Use HttpClient interceptors for cross-cutting concerns:
  - Auth: attach tokens to outgoing requests.
  - Errors: centralized error handling and user notification.
  - Loading: global loading state management.

## API Documentation
- Generate OpenAPI/Swagger spec from code annotations (e.g., `springdoc-openapi`).
- API documentation must always match the current implementation.
- Expose spec endpoint (e.g., `/api-docs`, `/swagger-ui`) in non-production environments.

## Code Comments Policy
- Comment "why" not "what"; code should be self-documenting for "what."
- Use Javadoc for public Java APIs; use JSDoc/TSDoc for exported TypeScript functions.
- Remove commented-out code; rely on version control for history.

## CI/CD Awareness
- Expect CI pipeline to run lint, tests, and build on every push/PR.
- Do not merge or claim completion if CI checks fail.
- Copilot should run local equivalents (lint, test, build) before finishing a task when feasible.
