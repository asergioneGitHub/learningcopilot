# Skill: Migration and Safe Rollout

## Purpose
Implement schema/data changes with safe rollout, rollback readiness, and operational awareness.

## References
- `.github/copilot-instructions.md`
- `.github/copilot-context.md`

## Required Inputs
- Migration intent and affected entities/tables
- Data volume/risk profile
- Rollout constraints (downtime window, compatibility period)
- Rollback expectation

## Execution Checklist
1. Propose expand/contract migration plan.
2. Assess compatibility with running application versions.
3. Implement migration scripts and app changes in safe order.
4. Add rollback strategy and backup awareness note.
5. Add/adjust tests for migration-sensitive paths.
6. Report impact, risks, and required operator steps.
7. Ask for explicit go/no-go before risky/high-cost rollout actions.

## Done Criteria
- Migration path is reversible or operationally safe.
- Compatibility and rollback documented.
- Risks and operator actions clearly stated.

## Prompt Template
Apply skill migration-rollout.
Change intent: <intent>
Affected schema/data: <details>
Risk profile: <low/medium/high + why>
Rollout constraints: <constraints>
Design expand/contract plan, rollback strategy, required checks, and implementation steps.
