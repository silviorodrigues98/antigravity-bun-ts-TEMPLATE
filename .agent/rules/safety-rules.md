---
trigger: always_on
---

# Agent Guidelines: Safety & Refactoring

You (the Agent) MUST protect the integrity of the codebase at all costs.

## 1. Anti-Breakage
- **Regression Check:** Before refactoring or adding a new feature to an existing module, run `bun test` to ensure the current state is working.
- **Post-Change Validation:** After ANY code change, you MUST run `bun test` and `bun run lint`. If anything breaks, undo or fix it immediately before presenting the result to the human.
- **Cascading Impact:** If you change an interface or a Zod Schema in `src/interfaces/`, you must check and update all files in `src/core/` and `src/infra/` that depend on it.

## 2. Destructive Actions (Require Confirmation)
- **NEVER delete files** (`.ts`, `.md`, `.json`, etc.) without explicitly asking the human first: *"Do you confirm the deletion of [filename]?"*.
- **NEVER delete database tables** or drop columns in migrations without explicit human confirmation.
- **NEVER overwrite entire complex logic blocks** at once. If a refactor is massive, present the plan to the human first.

## 3. Small Steps
- Make incremental changes. If the user asks for a massive feature, break it down into small logical steps and test each one in isolation.