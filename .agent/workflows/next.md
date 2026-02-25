---
description: Read the `TODO.md` file and guide interactive development with the user.
---

# Workflow: /next (or /todo)

Triggered when the human types `/next` or `/todo` in the chat.

**Goal:** Read the `TODO.md` file and guide interactive development with the user.

**Steps you (the Agent) MUST execute STRICTLY in this order:**

1. **Read the file:** Open and read the `TODO.md` file located at the root of the project.
2. **Filter pending tasks:** Identify all tasks that are not yet marked as completed (`- [ ]`).
3. **Present options:** Write a friendly message to the human listing the pending tasks with numbers.
4. **Ask:** Explicitly ask: *"Which of these tasks would you like me to implement now? (Reply with the number or describe what you want to focus on)."*
5. **STOP AND WAIT:** Do not write any code yet. Wait for the human's response.
6. **Plan & Execute:** After the human chooses, create a quick plan, verify safety rules (run tests), and implement the task.
7. **Mark as done:** Upon successful completion and testing, update the `TODO.md` file, marking the task as completed (`- [x]`).