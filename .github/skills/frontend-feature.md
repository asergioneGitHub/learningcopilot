# Skill: Frontend Feature (Angular)

## Purpose
Implement or update an Angular feature using project conventions for architecture, routing, and HTTP handling.

## References
- `.github/copilot-instructions.md`
- `.github/copilot-context.md`

## Required Inputs
- Feature goal and user flow
- Route changes (if any)
- API dependencies
- Validation/error/loading expectations
- Accessibility constraints (if any)

## Execution Checklist
1. Design smart/container vs presentational component split.
2. Define/update routes in feature `*.routes.ts` and add guards/resolvers where needed.
3. Implement data access via services and HttpClient interceptors patterns.
4. Keep state approach consistent within feature (signals or RxJS).
5. Use environment config for API base URL; no hardcoded endpoints.
6. Add/update tests (`*.spec.ts`) for key behavior.
7. Run build/tests and report outcomes.
8. If backend contract changed, trigger contract-sync skill.

## Done Criteria
- Feature behavior matches requirements.
- Tests/build pass.
- No contract drift with backend.

## Prompt Template
Apply skill frontend-feature.
Feature: <name>
User flow: <flow>
Routes: <changes>
API calls: <endpoints>
Validation/error/loading: <rules>
Implement with component architecture conventions, tests, and check results.
