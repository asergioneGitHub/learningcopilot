# Copilot Instructions (Entrypoint)

## Source of truth
The authoritative, composed governance for this repository is:

- `.copilot/compositions/spring-angular-layered-rest/EFFECTIVE.md`

If anything conflicts with that document, the EFFECTIVE document wins.

## How to execute work
- Use `.github/skills/` for step-by-step task playbooks and quality checklists.
- Use `.github/agents/` for role-based guidance and review.

## Universal guardrails (always apply)
- Ask 1–3 clarifying questions when requirements are ambiguous.
- Don't make silent assumptions; list assumptions and wait for approval if they affect implementation.
- Keep changes cohesive and PR-sized; avoid unrelated edits.
- Never hardcode secrets or credentials; never log sensitive data.
- Validate inputs at boundaries; preserve backward compatibility unless explicitly approved.
- If checks/tests fail, do not claim completion—report cause and fix options.
