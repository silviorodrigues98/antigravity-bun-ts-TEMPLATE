# 🚀 Antigravity Agent-First Boilerplate

A boilerplate architected **to be read and operated by Artificial Intelligence**. 
Built on top of **Bun**, **TypeScript**, **Biome**, and **Zod**.

This repository contains **no application code**. It contains the "Mind" (rules, workflows, and skills in the hidden `.agent/` folder) and a pre-configured foundation so that **Google Antigravity** can build perfect projects for you, strictly following your architectural requirements.

## 🛠 How to start your new project

1. Click the **"Use this template"** button at the top of this GitHub page.
2. Clone your newly generated repository to your machine.
3. Open the project folder in the **Google Antigravity** IDE.
4. **Install Dependencies:**
   In the terminal (or Agent chat), run:
   ```bash
   bun install
   ```
   *(Or type `/setup-project` in the Agent chat to let the AI verify the environment).*

5. **Define your Project:**
   Open the file `PROJECT_CONTEXT.md` in the root.
   - Paste your project requirements, API JSON responses, SQL queries, or business logic there.
   - This file serves as the "Source of Truth" for the Agent.

6. **Ignition:**
   In the Agent chat, type:
   > `/kickoff`

   **Sit back and watch:** The AI will analyze your context file, break it down into technical tasks, and populate the `TODO.md` file with a plan.

7. **Start Coding:**
   To begin implementation, type:
   > `/next`

## 🧠 How to interact with the Agent

Thanks to the `.agent/` folder, the Antigravity agent is trained on this specific stack.

### Workflows
- **/setup-project**: Verifies dependencies and environment health.
- **/kickoff**: Reads `PROJECT_CONTEXT.md` and generates a plan in `TODO.md`.
- **/next** (or **/todo**): Reads `TODO.md`, asks you which task to tackle, and implements it autonomously.

### Common Prompts
- *"Create the User Authentication module."* (The AI uses the scaffold skill, creates Zod validations, and writes native Bun tests).
- *"Check the code."* (The AI runs Biome to fix formatting/linting without asking).

## 📦 Enforced Stack
- **Runtime & Tests:** Bun (`bun:test`)
- **Language:** TypeScript (`strict: true`)
- **Validation:** Zod (Zero use of `any`)
- **Linter & Formatter:** Biome (Rust-based, ultra-fast)
- **Architecture:** Modular (Core/Infra/Interfaces)

## 📋 Prerequisites for Human Developers

To ensure maximum performance and compatibility with this boilerplate, make sure you have:

1. **[Bun](https://bun.sh/) installed:** (Version 1.0 or higher).
   - Install (Mac/Linux): `curl -fsSL https://bun.sh/install | bash`
   - Install (Windows): `powershell -c "irm bun.sh/install.ps1 | iex"`
2. **Biome Extension:** Install the **Biome** extension in your editor (VS Code, Cursor, Windsurf, or Antigravity). This replaces Prettier and ESLint.
   - *Note:* Disable Prettier/ESLint for this workspace to avoid conflicts.
3. **Google Antigravity IDE** (or your preferred Agent-First IDE) to fully utilize the automated workflows.