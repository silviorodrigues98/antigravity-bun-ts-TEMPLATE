---
description: Initialize the codebase from this empty template.
---

# Workflow: /setup-project

Triggered when the human types `/setup-project`.

**Goal:** Ensure the boilerplate is ready to use.

**Steps:**
1. **Install:** Run `bun install` to download dependencies defined in `package.json`.
2. **Verify:** Check if `PROJECT_CONTEXT.md` exists (it should).
3. **Notify:** Tell the user: 
   *"Dependencies installed! I see the `PROJECT_CONTEXT.md` file is ready. Please open it, paste your requirements, and then run `/kickoff`."*