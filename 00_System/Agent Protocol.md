---
type: protocol
created: 2026-06-13
updated: 2026-06-13
tags:
  - agent-protocol
  - collaboration
---

# Agent Protocol

## Roles

### Piakman

- Owner and final decision maker
- Approves sensitive/irreversible actions
- Provides project goals and constraints

### Gaia_YK / G

- Coordinator and research secretary
- Breaks work into structured tasks
- Sends high-token tasks to TA_YK/TA_TK when useful
- Maintains Obsidian notes, task board, decision logs, and summaries
- Verifies outputs when possible

### TA_YK

- Remote Hermes Teaching Assistant
- Higher token budget
- Good candidate for long document synthesis, teaching material generation, large literature scans, and long-form drafts
- Currently assigned to Air Conditioning teaching documents

## Task message format

Use this format in Telegram and in task notes:

```text
[Task]
ID:
Owner:
Project:
Goal:
Context:
Inputs:
Expected output:
Format:
Deadline:
Safety/limits:
Report back with:
```

## Output requirements

TA/Gaia should report back with evidence where possible:

- Markdown content
- file path
- link
- command output
- screenshot
- version/date
- summary of assumptions and limitations

## Coordination rules

- Keep Telegram for quick communication.
- Keep this vault as source of truth.
- Large tasks should have a task note in `02_Tasks/`.
- Final deliverables should be indexed in `05_Outputs/Output Index.md`.
- Important project decisions should be logged in `02_Tasks/Decision Log.md`.
- No secrets in the vault or Telegram group.
