---
description: Sync the human context with the actionable backlog.
---

# Workflow: /kickoff

**Goal:** Sync the human context with the actionable backlog.

**Steps:**
1. **Read:** Read the current state of `PROJECT_CONTEXT.md`.
2. **Persistence Check:** Do NOT delete or clear `PROJECT_CONTEXT.md`. Treat it as a permanent reference.
3. **Task Generation:**
   - Compare the requirements in `PROJECT_CONTEXT.md` with the current code and the existing `TODO.md`.
   - Identify new requirements that haven't been turned into tasks yet.
4. **Update TODO.md:** 
   - Append new tasks to the "Pending" section of `TODO.md`.
   - If a task in `TODO.md` is no longer relevant based on the updated context, mark it as "Deprecated" or ask for confirmation to remove it.
5. **Report:** Summary what you understood from the context and what the next three steps are.