# Copilot Governance Kit (Start Here)

This directory is the **primary home** for the repository's governance system:
- **Modules**: reusable rule sets
- **Compositions**: selected modules assembled into one *effective* ruleset
- **Skills/Agents** (in `.github/`): how to execute and review work against the effective rules

This repository is **not** a production application. It is a reusable Copilot-first operating system intended to be copied/adapted into real Spring Boot + Angular repositories.

---

## 1) How to use this repo (human + Copilot)
1. Open the **active effective governance**:
   - `.copilot/compositions/spring-angular-layered-rest/EFFECTIVE.md`
2. Follow links from `EFFECTIVE.md` into the selected module rules under:
   - `.copilot/modules/`
3. When doing work, use execution playbooks and checklists:
   - Skills: `.github/skills/`
   - Agents: `.github/agents/`

**Conflict rule:** if anything conflicts with `EFFECTIVE.md`, **EFFECTIVE.md wins**.

---

## 2) What is "effective governance"?
A composition's `EFFECTIVE.md` is the **single source of truth** for the rules that apply.

It should be:
- short
- link-heavy
- explicit about selected modules
- explicit about conflict resolution

---

## 3) Modules (building blocks)
- Location: `.copilot/modules/<category>/<module-name>/`
- Expected files:
  - `README.md` — when to use the module
  - `rules.md` — actionable rules ("must/should/must not")
  - `adr.md` (optional) — rationale & trade-offs

Modules are meant to be reusable across compositions.

---

## 4) Compositions (selecting modules)
- Location: `.copilot/compositions/<composition-name>/`
- Expected files:
  - `modules.md` — which modules are selected
  - `EFFECTIVE.md` — compiled/linked effective ruleset

### Current active composition (manual-first)
Right now the active composition is:
- `.copilot/compositions/spring-angular-layered-rest/EFFECTIVE.md`

If you want a different architecture style, create a new composition folder and point the entrypoint to its `EFFECTIVE.md`.

---

## 5) How this integrates with `.github/`
- `.github/copilot-instructions.md` is the **entrypoint/router** that points to the active `EFFECTIVE.md`.
- `.github/skills/` are task playbooks (how to do work).
- `.github/agents/` are reviewer/driver personas (how to guide work).
