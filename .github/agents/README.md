# Agents Pack

Agents are specialized personas that orchestrate how Copilot approaches a class of tasks.

## Relationship with Other Files
- `.github/copilot-instructions.md`: non-negotiable global rules.
- `.github/copilot-context.md`: project-specific facts.
- `.github/skills/*.md`: task playbooks/checklists.
- `.github/agents/*.agent.md`: role-based orchestration and output style.

## Available Agents
- `backend-api-reviewer.agent.md` — Reviews or guides backend API changes for layered architecture, contract safety, validation, tests, and docs sync.

## How to Use
Prompt pattern:
- "Use agent backend-api-reviewer for this task: <task details>"

Recommended input fields:
- Endpoint(s) affected
- Request/response changes
- Business/security constraints
- Compatibility expectations
- Scope limits

## Output Expectations
A good agent response should provide:
1. Scope understanding
2. Findings/checklist results
3. Required code/test/doc actions
4. Risk and compatibility notes
5. Clear next actions
