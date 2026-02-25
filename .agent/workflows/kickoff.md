---
description: Ingest the `PROJECT_CONTEXT.md` and populate the `TODO.md`
---

# Workflow: /kickoff

Triggered when the human types `/kickoff`.

**Goal:** Ingest the `PROJECT_CONTEXT.md` and populate the `TODO.md`.

**Steps:**
1. **Read Context:** Read `PROJECT_CONTEXT.md`.
2. **Check Content:** If the file still contains the default template text (like "Describe high-level logic"), STOP and ask the user to fill it out first.
3. **Analyze & Plan:** Break down the requirements into technical tasks (Schema creation, Service implementation, Tests).
4. **Update TODOs:** Clear the "Pending" section of `TODO.md` and insert the new tasks.
5. **Start:** Ask: *"Plan created in TODO.md. Ready to start? (Type `/next`)"*.