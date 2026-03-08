# Skill: Security Review

## Purpose
Proactively audit an endpoint or feature for security gaps before they become vulnerabilities.

> **Note:** This skill intentionally overlaps with the security checklist in `.github/copilot-instructions.md` so it remains self-contained and portable across repositories.

## References
- `.github/copilot-instructions.md`
- `.github/copilot-context.md`

## Required Inputs
- Target endpoint(s) or feature
- Auth/permission model in place
- Data sensitivity level (PII, financial, etc.)
- Known threat scenarios (if any)

## Execution Checklist
1. **Access control:** Verify only authorized users/roles can reach the endpoint. Check for missing or misconfigured guards/annotations.
2. **Input validation:** Confirm all inputs are validated and sanitized at the boundary (Bean Validation on DTOs, `@Valid` at controller entry). Check for injection vectors.
3. **Data exposure:** Ensure no sensitive fields leak in responses, error messages, or logs. Verify DTOs exclude internal/secret fields.
4. **Logging safety:** Confirm no secrets, tokens, passwords, or PII appear in log output.
5. **Authentication/authorization flow:** Trace the full auth path — token handling, session management, permission checks.
6. **Dependency exposure:** Check for known vulnerabilities in dependencies touched by this feature.
7. Implement required hardening fixes.
8. Add tests for unauthorized/forbidden paths and sensitive-data leakage prevention.
9. Run relevant checks and report outcomes.

## Done Criteria
- All checklist items reviewed and findings documented.
- Required fixes implemented with tests.
- No sensitive data exposed in responses or logs.
- Residual risks explicitly stated.

## Prompt Template
Apply skill security-review.
Target: `<endpoint/feature>`
Auth model: `<description>`
Data sensitivity: `<level>`
Known threats: `<scenarios or "none known">`
Audit using the checklist above, implement fixes, add security tests, run checks, and report findings with residual risk.
