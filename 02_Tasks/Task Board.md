---
type: task-board
created: 2026-06-13
updated: 2026-06-13
tags: [task-board, gaia-coordinate]
---

# Task Board

## Inbox

- [ ] Confirm TA_YK can receive and respond to Gaia in Telegram group.
- [ ] Decide sync method for this shared vault: manual export, Git, Drive, Dropbox, iCloud, or server mount.
- [ ] Create first Air Conditioning task package for TA if needed.

## Active

- [ ] [[AC-TA-002 - TA Git Writeback and Air Conditioning Inventory]] — owner: TA_YK — verify git writeback and inventory Air Conditioning work

```dataview
TABLE owner, status, priority, project, due, file.mtime AS modified
FROM "02_Tasks"
WHERE type = "task" AND status = "active"
SORT priority ASC, due ASC
```

## Waiting

```dataview
TABLE owner, waiting_for, project, file.mtime AS modified
FROM "02_Tasks"
WHERE type = "task" AND status = "waiting"
SORT file.mtime DESC
```

## Done

```dataview
TABLE owner, project, completed, file.mtime AS modified
FROM "02_Tasks"
WHERE type = "task" AND status = "done"
SORT completed DESC
LIMIT 20
```
