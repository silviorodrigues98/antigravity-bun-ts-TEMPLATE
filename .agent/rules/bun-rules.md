---
trigger: always_on
---

# Agent Guidelines: Bun Framework

Default to using Bun instead of Node.js.

- Use `bun <file>` instead of `node <file>` or `ts-node <file>`
- Use `bun test` instead of `jest` or `vitest`
- Use `bun install` instead of `npm install` or `yarn install` or `pnpm install`
- Use `bun run <script>` instead of `npm run <script>` or `yarn run <script>` or `pnpm run <script>`
- Bun automatically loads `.env`, so NEVER use `dotenv`.

NOTE: When only changing TypeScript, you do NOT need to run the build script.

## Bun Native APIs (MANDATORY)

- **Servers:** `Bun.serve()` supports WebSockets, HTTPS, and routes. Do NOT use `express` or `fastify`.
- **Database (SQLite):** Use `bun:sqlite`. Do NOT use `better-sqlite3`.
- **Database (Redis):** Use `Bun.redis`. Do NOT use `ioredis` or `redis`.
- **Database (Postgres):** Use `Bun.sql`. Do NOT use `pg` or `postgres.js`.
- **WebSockets:** `WebSocket` is built-in. Do NOT use `ws` or `socket.io`.
- **File System:** Prefer `Bun.file` and `Bun.write` over `node:fs`'s readFile/writeFile.
- **Child Processes:** Use `Bun.$` instead of `execa` or `child_process`.

## Testing

Use `bun test` to run tests from the `tests/` directory.

```ts
// Example: tests/index.test.ts
import { test, expect } from "bun:test";

test("hello world", () => {
  expect(1).toBe(1);
});
```

For more information, read the Bun API docs in `node_modules/bun-types/docs/**.md`.

## TypeScript Code Style

- **Runtime**: Bun with TypeScript
- **Formatting & Linting**: Biome (Do NOT use Prettier or ESLint).
- **Imports**: Use explicit imports. Group by: built-ins, external deps, internal modules.
- **Types**: Strict TypeScript (`strict: true`). Use interfaces for options/configs, and explicit return types for public APIs.
- **Naming**: `camelCase` for variables/functions, `PascalCase` for classes/interfaces, `UPPER_CASE` for constants.
- **Error Handling**: Use proper `Error` objects, avoid silent failures.
- **Async**: Prefer `async/await` over Promises, handle errors explicitly.
- **Comments**: Minimal comments, **NO JSDoc**. Code must be self-explanatory.
- **File Structure**: Index files for clean exports, group related functionality into `src/core`, `src/infra`, and `src/interfaces`.
- **Testing Style**: Descriptive test names, use `beforeEach`/`afterEach` for setup.

## Debugging Workflow

1. Reproduce the issue in a test case inside the `tests/` folder. 
2. **Do NOT start fixing without a reproducible test case.**
3. Use debug logs to see what is actually happening. 
4. **DO NOT GUESS.** Validate assumptions through tests before outputting the final code.