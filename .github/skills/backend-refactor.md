# Skill: Backend Refactor Safety

## Purpose
Refactor backend code for readability/maintainability while preserving behavior.

## References
- `.github/copilot-instructions.md`
- `.github/copilot-context.md`

## Required Inputs
- Refactor target (class/module/feature)
- Primary goal (naming, decomposition, duplication removal)
- Explicit non-goals
- Allowed behavior changes (if any)

## Execution Checklist
1. State assumptions and confirm no behavior change intent by default.
2. Refactor in small cohesive steps (PR-sized).
3. Keep architecture boundaries strict (controller/service/repository).
4. Preserve public API contracts unless explicitly approved.
5. Add/update tests to lock behavior and cover touched logic.
6. Run checks and document outcomes.
7. If uncertain, present options with trade-offs before proceeding.

## Done Criteria
- Code readability improved with no unintended behavior changes.
- Tests updated and passing.
- Any intentional behavior change explicitly documented.

## Prompt Template
Apply skill backend-refactor.
Target: <files/classes>
Goal: <goal>
Non-goals: <non-goals>
Behavior-change approval: <yes/no + details>
Proceed incrementally, preserve behavior, update tests, run checks, and summarize risks.
