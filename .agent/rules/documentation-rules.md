---
trigger: always_on
---

# Agent Guidelines: Continuous Documentation

## 1. Feature and Changelog Documentation
- Whenever you implement, alter, or remove a feature, you MUST update the `docs/CHANGELOG.md` or `docs/FEATURES.md` file (create it if it doesn't exist) with a brief technical description of what was done.
- The code should be self-explanatory, but the overarching architecture of a new feature must be documented in the `docs/` folder.

## 2. API Documentation (Swagger/OpenAPI)
If the project has HTTP/API routes:
- The project uses `Zod` for validation.
- Whenever you create or modify an API route, you MUST update the corresponding OpenAPI (Swagger) specification file, usually located at `docs/openapi.yaml` or `docs/swagger.json`.
- Strictly map the `Zod` schemas (body, params, responses) to the OpenAPI 3.0 syntax.
- If the user asks to "Generate Swagger", use readable scripts and Zod-compatible libraries (e.g., `@asteasolutions/zod-to-openapi`) to automate the generation of `openapi.json`.