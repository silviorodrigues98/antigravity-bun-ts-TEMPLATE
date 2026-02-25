---
trigger: always_on
---

# Agent Guidelines: TypeScript Style & Best Practices

Whenever you are writing, refactoring, or reviewing TypeScript code (`.ts` files), you MUST adhere to the following rules.

## 1. Type Safety (Zero Tolerance for `any`)
- **NEVER use `any`.** If a type is truly unknown at compile time, use `unknown` and perform type narrowing.
- **Strict Mode:** Assume `"strict": true` is always enabled. You must handle all potentially `null` or `undefined` values.
- **Type Assertions:** Avoid using `as Type` (type casting). Instead, structure your code so the TypeScript compiler infers the type naturally, or use validation schemas.
- **External Data Boundaries:** Any data coming from outside the application (HTTP requests, Database queries, APIs) MUST be validated using `zod` before reaching the `src/core/` domain. Extract TypeScript types from Zod schemas using `zod.infer<typeof schema>`.

## 2. Exports and Imports
- **Named Exports Only:** Prefer named exports (`export const`, `export class`, `export function`). Do NOT use `export default`. Named exports make refactoring and codebase navigation much easier for AI and humans.
- **Explicit Imports:** Do not use implicit index imports if it creates ambiguity. 
- **Grouping Imports:** Group imports at the top of the file in this exact order:
  1. Built-in native modules (e.g., `bun:sqlite`).
  2. External dependencies (e.g., `zod`).
  3. Internal project modules (e.g., `../interfaces/...`).

## 3. Naming Conventions
- **Variables & Functions:** `camelCase` (e.g., `getUserData`).
- **Classes, Interfaces, and Types:** `PascalCase` (e.g., `UserInterface`, `PaymentService`).
- **Constants:** `UPPER_SNAKE_CASE` for global/hardcoded constants (e.g., `MAX_RETRY_COUNT`).
- **Booleans:** Prefix boolean variables with `is`, `has`, or `should` (e.g., `isValid`, `hasPermission`).

## 4. Interfaces vs. Types
- Use `interface` for defining object shapes, class contracts, and dependency injection interfaces.
- Use `type` for unions (`type Status = "pending" | "done"`), intersections, and utility types (`Omit`, `Pick`).

## 5. Functions & Async Programming
- **Pure Functions:** Favor writing pure functions that do not mutate external state whenever possible.
- **Async/Await:** ALWAYS use `async/await`. Do NOT use Promise chaining (`.then().catch()`).
- **Explicit Return Types:** Public functions, class methods, and route handlers MUST have explicit return types. Do not rely solely on inference for public APIs.
  ```typescript
  // Correct
  export async function calculateTotal(items: Item[]): Promise<number> { ... }
  ```

## 6. Error Handling
- **No Silent Failures:** Never write empty `catch` blocks.
- **Custom Errors:** Throw standard `Error` objects or custom classes extending `Error`. Do not throw strings or generic objects.
- **Predictable Flow:** If a function can fail in an expected way (e.g., "User Not Found"), consider returning a result object (e.g., `{ success: false, error: "Not Found" }`) rather than throwing exceptions for control flow. Reserve `throw` for actual system exceptions.

## 7. Comments and Documentation
- **NO JSDoc for Types:** Do not write JSDoc comments just to declare types. TypeScript already handles this.
- **Self-Documenting Code:** Code must be expressive enough to explain *what* it is doing.
- **Minimal Comments:** Only write comments to explain *WHY* a specific, non-obvious technical decision was made.

## 8. Formatting & Linting
- Never use or configure `Prettier` or `ESLint`. 
- The project strictly uses `@biomejs/biome`. If the code has formatting issues, run `bun run lint` and `bun run format` to fix them autonomously before presenting the code to the user.