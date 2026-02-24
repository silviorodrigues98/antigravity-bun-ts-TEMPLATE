---
trigger: always_on
---

# Project Stack Rules

Whenever you operate in this project, strictly obey these rules:

- **Runtime & Packages:** EXCLUSIVELY use `bun`. Never use `npm`, `yarn`, or `pnpm`. Commands must always be `bun install`, `bun run`, `bun test`, etc.
- **Language:** TypeScript in strict mode (`strict: true`).
- **Typing & Validation:** NEVER use `any`. If a type is unknown, use `unknown`. All external data validation, payloads, and DTOs must be parsed using the `zod` library.
- **Linting & Formatting:** This project uses `@biomejs/biome`. Do not suggest, install, or configure ESLint or Prettier.
- **Architecture:** The code must be modular.
  - `src/core/`: Pure business rules and use cases.
  - `src/infra/`: Integrations, databases, external APIs.
  - `src/interfaces/`: Zod schemas and TypeScript types.