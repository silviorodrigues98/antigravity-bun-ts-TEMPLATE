# 🚀 Antigravity Agent-First Boilerplate

A boilerplate architected **to be read and operated by Artificial Intelligence**. 
Built on top of **Bun**, **TypeScript**, **Biome**, and **Zod**.

This repository contains **no application code**. It contains the "Mind" (rules, workflows, and skills in the hidden `.agent/` folder) so that **Google Antigravity** can build perfect projects for you, without hallucinating dependencies or breaking architectural patterns.

## 🛠 How to start your new project

1. Click the **"Use this template"** button at the top of this GitHub page.
2. Clone your newly generated repository to your machine.
3. Open the project folder in the **Google Antigravity** IDE.
4. In the Agent Manager chat, type exactly the following command:
   
   > `/setup-project`

5. **Sit back and watch:** The AI will read the repository rules, perform the initial installations (Bun, Zod, Biome), configure the `package.json`, and scaffold a clean folder architecture.

## 🧠 How to interact with the Agent in this project

Thanks to the `.agent/` folder, the Antigravity agent is already trained on this repository's stack. You can prompt things like:

- *"Create the User Authentication module."* (The AI will use the scaffold skill, create Zod validations, and write native Bun tests).
- *"Check the code."* (The AI will run Biome and adjust formatting/linting without ever touching ESLint/Prettier).

## 📦 Enforced Stack
- **Runtime & Tests:** Bun (`bun:test`)
- **Language:** TypeScript (`strict: true`)
- **Validation:** Zod (Zero use of `any`)
- **Linter & Formatter:** Biome (Rust-based, ultra-fast)

## 📋 Prerequisites for Human Developers

To ensure maximum performance and compatibility with this boilerplate, make sure you have:

1. **[Bun](https://bun.sh/) installed:** (Version 1.0 or higher).
   - Install (Mac/Linux): `curl -fsSL https://bun.sh/install | bash`
   - Install (Windows): `powershell -c "irm bun.sh/install.ps1 | iex"`
2. **Biome Extension:** Install the **Biome** extension in your editor (VS Code, Cursor, Windsurf, or Antigravity). This replaces Prettier and ESLint.
   - *Note:* Make sure to disable Prettier/ESLint for this workspace to avoid formatting conflicts.
3. **Google Antigravity IDE** (or your preferred Agent-First IDE) to fully utilize the automated workflows in the `.agent/` folder.