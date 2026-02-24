---
name: Generate New Resource (Scaffold)
description: Creates the standardized structure (Zod Schema, Core service, and Tests) for a new project domain.
triggers: ["create resource", "new module", "generate entity", "scaffold"]
---

# Skill Instructions

When the user asks to create a new resource (e.g., "Create the Product entity"):
1. Create the validation schema in `src/interfaces/<resource>.schema.ts` using `zod`.
2. Create the business logic in `src/core/<resource>.service.ts`.
3. Create the test file in `tests/<resource>.test.ts` importing `bun:test`.
4. Ensure the generated code passes the linter by running `bun run lint` in the terminal before completing the task.