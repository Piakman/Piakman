---
type: collaboration-session
session_id: 254442
project: Air Conditioning
course: Air Conditioning
owner: Piakman
coordinator: Gaia_YK
assistant: TA_YK
status: active
created: 2026-06-13
updated: 2026-06-13
tags:
  - session/254442
  - air-conditioning
  - teaching-documents
  - gaia-coordinate
  - ta-yk
---

# 254442 - Air Conditioning Teaching Session

## Purpose

Session `254442` is the active Gaia ↔ TA_YK collaboration session for preparing teaching documents for the **Air Conditioning** course.

## Local Hermes review session

Opened on Piakman's Mac for live teaching-document review:

- Hermes process session handle: `proc_39c1f4db6aa1`
- PID: `73143`
- Working directory: `/Users/pm/Documents/Gaia_Coordinate_Vault`
- Activated skills: `obsidian`, `github-repo-management`
- Intended title: `254442`
- Role: standby assistant for reading, checking, and summarizing Air Conditioning teaching documents

Use this session when Piakman wants an additional Hermes instance to help inspect lesson documents while Gaia coordinates the shared vault.

## Communication channel

- Primary coordination: Telegram group `Gaia_Coordinate`
- Shared source of truth: Git/Obsidian vault branch `gaia-coordinate-vault`
- Repository: `https://github.com/Piakman/Piakman`

## Active agents

- Piakman — owner / instructor / final decision maker
- Gaia_YK — coordinator, editor, task manager, Obsidian maintainer
- TA_YK — Teaching Assistant, high-token drafting and production support

## Current confirmed TA_YK environment

TA_YK reported successful Git writeback on 2026-06-13.

| Item | Value |
|---|---|
| Shared vault clone | `/Users/classicman/Desktop/mywork/piakman/piakman_lessonPlan/Gaia_Coordinate_Vault` |
| Remote | `git@github.com:Piakman/Piakman.git` |
| Working repo / pipeline | `/Users/classicman/Desktop/mywork/piakman/piakman_lessonPlan` |
| Content vault | `~/Library/Mobile Documents/iCloud~md~obsidian/Documents/Obsidian Vault/Piakman/aircon` |
| Git branch | `gaia-coordinate-vault` |
| Git writeback | confirmed working |

## Current Air Conditioning status from TA_YK

- Subject/repo context: `aircon` is actively in production.
- Chapters 1–4 are drafted with full per-topic lesson sets.
- Total topics: 26.
- Completed: 26 content files, 26 examples files, 26 exercises files.
- Slides: 22/26 per-topic slides done.
- Gap: Chapter 2 per-topic `slides.md` missing for 4 topics.
- Existing sources: 10 OCR files plus วสท. standards digests:
  - `vsat_031001_aircon.md`
  - `vsat_031010_ventilation.md`

## Priority task sequence

1. Close Chapter 2 slide gap — generate 4 per-topic `slides.md` files:
   - 2.1 thermal comfort factors
   - 2.2 comfort chart
   - 2.3 IAQ standards
   - 2.4 ventilation standards
2. Draft Chapter 5 using exact load-calculation method sources.
3. Cross-check CLTD tables and ventilation rates against วสท. 031001/031010 digests; tag unconfirmed values with `⚠️verify`.

## Output conventions

TA_YK preferred format:

- Per-topic Markdown under `02_Topics/Chapter_NN/MM_<slug>/`
- Files: `content.md`, `examples.md`, `exercises.md`, `slides.md`
- Thai-primary explanations with English technical terms in parentheses on first use
- Cite source pages where possible
- Slides: Marp Markdown → PDF; chapter-level `.pptx` in English when needed
- Long detail goes into vault files; Telegram replies remain concise

## SSH / direct access upgrade path

Current workflow uses Git + Telegram group.

If Piakman later obtains an SSH authentication key/access path from the TA_YK machine, Gaia and TA_YK coordination can be upgraded. Possible upgrades:

1. Gaia can SSH to TA_YK machine for direct file/status checks.
2. Gaia can pull source/output artifacts directly from TA_YK working repo.
3. Gaia can verify build/export outputs without relying only on Telegram summaries.
4. Git remains the source-of-truth sync layer unless Piakman decides otherwise.

No SSH private keys or secrets should be stored in this vault.

## Related notes

- [[Air Conditioning Project Dashboard]]
- [[TA Task - Confirm Air Conditioning Status]]
- [[../../02_Tasks/AC-TA-002 - TA Git Writeback and Air Conditioning Inventory]]
- [[../../00_System/Git Sync Workflow]]
- [[../../00_System/Telegram Coordination]]
