# Skill: Backend Bug Fix

## Purpose
Fix a backend bug at root cause with regression protection and clear impact reporting.

## References
- `.github/copilot-instructions.md`
- `.github/copilot-context.md`

## Required Inputs
- Symptoms and failing behavior
- Expected behavior
- Reproduction steps or failing tests
- Affected module/endpoint (if known)

## Execution Checklist
1. Reproduce issue (test/log/trace) and identify root cause.
2. Confirm whether auth/permission/data-exposure paths are impacted.
3. Implement minimal cohesive fix in correct layer.
4. Add or update regression tests that fail before and pass after fix.
5. Verify no API contract break unless explicitly approved.
6. Run relevant checks (tests/lint/build) and report exact results.
7. Provide concise impact and residual risk notes.

## Done Criteria
- Root cause addressed.
- Regression test added/updated.
- No unrelated changes.
- Checks pass or failures documented with fix options.

## Prompt Template
Apply skill backend-bugfix.
Bug summary: <summary>
Expected behavior: <expected>
Repro steps: <steps>
Scope limits: <what not to change>
Please reproduce, find root cause, fix it, add regression tests, run checks, and report impact.
