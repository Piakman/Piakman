---
type: dashboard
created: 2026-06-13
updated: 2026-06-13
tags:
  - dashboard
  - gaia-coordinate
---

# Gaia Coordinate Dashboard

## Active coordination

- Telegram group: `Gaia_Coordinate`
- Gateway target from Gaia: `telegram:Gaia_Coordinate`
- Telegram chat ID: `-1004316359779`
- Agents:
  - [[Agents/Piakman|Piakman]]
  - [[Agents/Gaia_YK|Gaia_YK]]
  - [[Agents/TA_YK|TA_YK]]

## Main areas

- [[Agent Protocol]]
- [[Telegram Coordination]]
- [[Git Sync Workflow]]
- [[TA_YK Direct SSH Setup]]
- [[../02_Tasks/Task Board|Task Board]]
- [[../02_Tasks/Meeting Schedule|Meeting Schedule]]
- [[../02_Tasks/Decision Log|Decision Log]]
- [[../03_Projects/Air Conditioning/Air Conditioning Project Dashboard|Air Conditioning Project Dashboard]]
- [[../04_Research/Research Delegation Inbox|Research Delegation Inbox]]
- [[../05_Outputs/Output Index|Output Index]]

## Current priority

1. Confirm TA_YK/TA_TK can respond in Telegram group.
2. Use this vault as shared source of truth for tasks and outputs.
3. Decide later whether to upgrade from Telegram group coordination to SSH/API/Webhook/shared sync.

## Dataview placeholders

```dataview
TABLE status, owner, priority, file.mtime AS modified
FROM "02_Tasks"
WHERE type = "task"
SORT priority ASC, file.mtime DESC
```
