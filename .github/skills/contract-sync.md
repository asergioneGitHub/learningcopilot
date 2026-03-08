# Skill: Backend/Frontend Contract Sync

## Purpose
Keep backend API and frontend client/types/tests synchronized in one cohesive task.

## References
- `.github/copilot-instructions.md`
- `.github/copilot-context.md`

## Required Inputs
- Contract change summary
- Affected endpoints and DTO fields
- Frontend features consuming changed endpoints
- Compatibility strategy (additive/deprecate/breaking)

## Execution Checklist
1. Apply backend contract changes with backward compatibility by default.
2. Update OpenAPI/Swagger docs.
3. Update frontend API services/types/models.
4. Update frontend tests affected by contract changes.
5. Validate runtime behavior across both sides.
6. Document anything intentionally deferred.

## Done Criteria
- No backend/frontend contract mismatch.
- Docs and tests aligned.
- Deferred work explicitly listed.

## Prompt Template
Apply skill contract-sync.
Contract change: <summary>
Affected endpoints: <list>
Frontend consumers: <list>
Compatibility approach: <approach>
Implement backend + frontend sync, update docs/tests, and report any remaining follow-ups.
