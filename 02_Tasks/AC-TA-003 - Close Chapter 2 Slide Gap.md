---
type: task
id: AC-TA-003
session_id: 254442
status: active
owner: TA_YK
project: Air Conditioning
priority: 1
created: 2026-06-13
tags: [task, air-conditioning, session-254442, slides, ta]
---

# AC-TA-003 - Close Chapter 2 Slide Gap

## Goal

Create the 4 missing per-topic `slides.md` files for Chapter 2 of the Air Conditioning teaching materials.

## Context

This task belongs to collaboration session [[../03_Projects/Air Conditioning/254442 - Teaching Session|254442]].

TA_YK reported that Chapters 1–4 have complete content/examples/exercises, but Chapter 2 is missing 4 per-topic `slides.md` files.

## Required outputs

Create/update the 4 missing Chapter 2 slide files in the TA_YK `aircon` content vault/working repo:

1. Topic 2.1 — thermal comfort factors
2. Topic 2.2 — comfort chart
3. Topic 2.3 — IAQ standards
4. Topic 2.4 — ventilation standards

## Format requirements

- Use the same per-topic `slides.md` style as Chapters 1, 3, and 4.
- Thai-primary, with English technical terms in parentheses on first use.
- Keep slide text concise and teaching-friendly.
- Use Marp-compatible Markdown if that is the established slide format.
- Cite source pages or digest references when values/standards are used.
- Tag uncertain values with `⚠️verify`.

## Report back

After completion, TA_YK should push and report:

```text
AC-TA-003 done
commit: <commit hash>
files:
- <path to topic 2.1 slides.md>
- <path to topic 2.2 slides.md>
- <path to topic 2.3 slides.md>
- <path to topic 2.4 slides.md>
blockers: <none/list>
```

## Gaia verification plan

1. Pull latest `gaia-coordinate-vault` branch if TA_YK writes status/output here.
2. Review TA_YK summary and file paths.
3. Ask TA_YK for exported PDF/PPTX if needed.
4. Update session `254442` and project dashboard.
