---
description: Initialize the codebase from the empty template
---

# Workflow: /setup-project

Triggered when the human types `/setup-project` in the chat.

**Goal:** Initialize the codebase from this empty template.

**Steps you (the Agent) must execute in the terminal and codebase:**
1. Run `bun init -y` to generate the base `package.json` (if it doesn't exist).
2. Install essential dependencies: `bun add zod` and `bun add -d @types/bun typescript @biomejs/biome`.
3. Create the `tsconfig.json` with `"strict": true` (if not already provided).
4. Run `bunx @biomejs/biome init` to create the `biome.json` (if not already provided).
5. Create the base directory structure: `src/core/`, `src/infra/`, `src/interfaces/`, `tests/`, and `docs/`.
6. Create an `src/index.ts` file with a simple `console.log("System successfully initialized!")`.
7. Add the following scripts to `package.json`: 
   - `"dev": "bun run --watch src/index.ts"`
   - `"test": "bun test"`
   - `"lint": "biome check ."`
   - `"format": "biome format --write ."`
8. Notify the user that the baseline is ready and ask what is the first use case or domain they want to build.