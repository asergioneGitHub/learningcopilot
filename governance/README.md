# Governance (Modules + Manual Compositions)

This directory turns this repository into a governance/template library that can be *composed* for different architectures and delivery styles.

## Key idea
- **Modules** are small, reusable governance building blocks.
- **Compositions** are hand-assembled, human-readable “runtime governance” documents created by selecting and combining modules.

This is intentionally **manual-first**: no generator is required to get value. If/when needed, a composer can be added later.

## Directory structure
- `governance/modules/` — reusable building blocks (Markdown-first)
- `governance/compositions/` — hand-assembled “runtime” governance docs

## Rules
1. Modules should be reusable and focused on a single concern.
2. Compositions may add only minimal glue text to resolve conflicts or state choices.
3. Do not edit modules to fit a single composition; instead, add glue in the composition.

## How to add a module
1. Create a folder under `governance/modules/<category>/<module-name>/`.
2. Add `README.md` describing when to use the module.
3. Add `rules.md` with the actionable governance rules.
4. (Optional) Add `adr.md` with rationale and tradeoffs.

## How to create a composition
1. Create a folder under `governance/compositions/<composition-name>/`.
2. Create `modules.md` listing selected modules and links.
3. Create `RUNTIME.md` as the single compiled governance document Copilot and humans should follow.
