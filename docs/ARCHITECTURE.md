# 🏗 Project Architecture & Design Principles

> **Note to AI Agents:** Read this document BEFORE creating new files. You must strictly adhere to this folder structure and separation of concerns.

## 1. High-Level Philosophy
This project follows a **Pragmatic Modular Architecture** designed for:
1.  **Type Safety:** `Zod` is the gatekeeper for all data.
2.  **Performance:** `Bun` native APIs are preferred over external libraries.
3.  **Agent-Friendliness:** Code is isolated into small, single-responsibility modules to minimize context window usage.

## 2. Directory Structure

### `src/interfaces/` (The Contracts)
**Purpose:** Contains data definitions.
- **Content:** Zod Schemas (`.schema.ts`) and TypeScript Types (`.types.ts`).
- **Rule:** Every external input (API request, DB result, File read) MUST be validated by a Zod schema here before being used in the Core.
- **Example:** `src/interfaces/user.schema.ts`

### `src/core/` (The Business Logic)
**Purpose:** Pure business rules and domain logic.
- **Content:** Service functions, domain calculations, and data transformations.
- **Rule:** This layer should be **framework-agnostic**. Avoid importing `Bun.serve` or database drivers directly here if possible. It receives typed data (from `interfaces`), processes it, and returns results.
- **Example:** `src/core/pricing.service.ts`

### `src/infra/` (The External World)
**Purpose:** Interaction with the outside world.
- **Content:** HTTP Routes, Database Clients, API Clients, File System access.
- **Rule:** This is the only layer allowed to use side-effects (fetching URLs, querying SQL, writing files).
- **Example:** `src/infra/http/routes.ts`, `src/infra/db/postgres.ts`

### `tests/` (Quality Assurance)
**Purpose:** Automated tests using `bun:test`.
- **Rule:** Tests must mirror the `src` structure or be grouped by feature.
- **Requirement:** Run `bun test` after every significant change.

## 3. The Data Flow
1.  **Input:** Request comes into `src/infra` (e.g., an HTTP request).
2.  **Validation:** Data is validated against a Schema in `src/interfaces`.
3.  **Processing:** Validated data is passed to a function in `src/core`.
4.  **Output:** Result is returned to `src/infra` to be sent back to the user/database.

## 4. Stack Decisions
- **Runtime:** Bun (Use `Bun.file`, `Bun.write`, `Bun.serve`, `Bun.env`).
- **Validation:** Zod (No `any` types allowed).
- **Formatting:** Biome (No Prettier/ESLint).