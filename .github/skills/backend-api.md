# Skill: Backend API Endpoint

## Purpose
Implement one backend API endpoint end-to-end in layered architecture while respecting repository rules.

## References
- `.github/copilot-instructions.md`
- `.github/copilot-context.md`

## Required Inputs
- HTTP method and path
- Request and response fields
- Business rules and validation rules
- Auth/permission expectations
- Backward compatibility constraints

## Execution Checklist
1. Define or update request/response DTOs with Bean Validation.
2. Add controller endpoint with `@Valid` and correct status code.
3. Implement business logic in service layer only (`@Transactional` where needed).
4. Add repository methods (derived query or JPQL `@Query` when justified).
5. Map entity ↔ DTO (MapStruct/manual) and avoid exposing entities.
6. Ensure standardized API error format: `{ error, message, details, timestamp }`.
7. If endpoint touches auth/permissions/data exposure, perform security checklist (access control, input validation, data exposure, logging safety) — see `security-review.md` for full playbook.
8. Add/adjust tests:
   - Unit tests for service logic.
   - Integration tests for endpoint behavior, validation, and auth paths.
9. Update OpenAPI/Swagger docs to match implementation.
10. Run relevant checks and report outcomes.
11. If response contract changed and a frontend exists, trigger `contract-sync.md` skill or explicitly document deferred sync.

## Done Criteria
- Endpoint works as specified.
- Tests and checks pass.
- Docs updated.
- Risks/impact summarized.

## Prompt Template
Apply skill backend-api.
Implement: <METHOD> <PATH>
Request DTO: <fields>
Response DTO: <fields>
Business rules: <rules>
Security rules: <rules>
Compatibility constraints: <constraints>
Then implement code, tests, docs, run checks, and provide risk/impact summary.
