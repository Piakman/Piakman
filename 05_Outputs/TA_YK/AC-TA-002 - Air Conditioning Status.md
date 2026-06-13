---
type: output
task: AC-TA-002
owner: TA_YK
project: Air Conditioning
status: done
created: 2026-06-13
tags: [output, air-conditioning, ta, git-sync, status]
---

# AC-TA-002 — Air Conditioning Status (TA_YK)

Git writeback verification + inventory of the Air Conditioning teaching-document work, reported by **TA_YK**.

## 1. Repo path on TA_YK server

| Item | Value |
|---|---|
| Shared vault clone | `/Users/classicman/Desktop/mywork/piakman/piakman_lessonPlan/Gaia_Coordinate_Vault` |
| Remote | `git@github.com:Piakman/Piakman.git` |
| Working repo (pipeline) | `/Users/classicman/Desktop/mywork/piakman/piakman_lessonPlan` |
| Content vault (Obsidian, iCloud) | `~/Library/Mobile Documents/iCloud~md~obsidian/Documents/Obsidian Vault/Piakman/aircon` |

Writeback confirmed in both directions: `pull --rebase` ✓, create file ✓, commit + push ✓.

## 2. Branch + latest commit before editing

- Branch: `gaia-coordinate-vault`
- Latest commit before this edit (after `git pull --rebase`): `22dc0f8` — *Add TA_YK git writeback task AC-TA-002*

## 3. Current Air Conditioning teaching-document status

Subject `aircon` ("Air Conditioning") is **actively in production**. 4 of the planned chapters are drafted with full per-topic lesson sets. Source is OCR-digested; international standards (วสท.) are digested for reference.

| Chapter | Title | Topics | content | examples | exercises | slides(md) | Chapter deliverables |
|---|---|---|---|---|---|---|---|
| 1 | การปรับสภาวะอากาศ และระบบปรับอากาศ | 6 | 6 | 6 | 6 | 6 | chapter.pdf, sheet.pdf, EN .pptx |
| 2 | สภาวะความสบายฯ + คุณภาพอากาศ/ระบายอากาศ | 4 | 4 | 4 | 4 | 0 | chapter.pdf, EN .pptx |
| 3 | การรวบรวมข้อมูลสำหรับออกแบบ | 4 | 4 | 4 | 4 | 4 | chapter.pdf |
| 4 | การคำนวณภาระทำความเย็น (CLTD) | 12 | 12 | 12 | 12 | 12 | chapter.pdf |

**Totals:** 26 topics, 26× content / 26× examples / 26× exercises, 22× per-topic slides.
**Only gap:** Chapter 2 per-topic `slides.md` missing (4 files) — chapter EN .pptx exists, so it is partially covered.

## 4. Existing sections / drafts

**Source (`00_Source/`):** 10 OCR'd source files (AC intro, thermal comfort, site survey, load calc, standard design condition, solar heat gain glass/walls, infiltration/ventilation, duct design) + กฎกระทรวง ฉบับที่ 33.pdf + `figures/`.

**Digests (`00_Source/_digest/`):**
- `vsat_031001_aircon.md` — วสท. 031001-21 (มาตรฐานระบบปรับอากาศและระบายอากาศ)
- `vsat_031010_ventilation.md` — วสท. 031010-60 (มาตรฐานการระบายอากาศ/IAQ, adopts ASHRAE 62.1)

**Syllabus (`01_Syllabus/`):** Chapter_01–04 topic proposals.

**Topics (`02_Topics/`):** Chapter_01–04 directories, each topic folder = `content.md` + `examples.md` + `exercises.md` (+ `slides.md` where built).

## 5. Proposed next 3 tasks for TA_YK

1. **Close Chapter 2 slide gap** — generate 4× per-topic `slides.md` (2.1 thermal comfort factors, 2.2 comfort chart, 2.3 IAQ standards, 2.4 ventilation standards) to match Ch1/3/4.
2. **Draft Chapter 5 (Load Calculation, exact method)** — source (`Source_04b–04e`, duct design) is already digested; propose topics → work topics.
3. **Standards cross-check pass** — verify CLTD tables + ventilation rates in Ch4 against วสท. 031001/031010 digests, tag `⚠️verify` on any unconfirmed value.

## 6. Preferred output format for long teaching documents

- **Per-topic Markdown** under `02_Topics/Chapter_NN/MM_<slug>/`: `content.md` / `examples.md` / `exercises.md` / `slides.md` — Thai-primary, English technical terms in parentheses on first use, cite source pages.
- **Slides:** Marp Markdown → PDF; chapter-level **`.pptx` (EN)** for sharing.
- **Chapter bundle:** `chapter.pdf` (compiled) + `Chapter_NN_sheet.pdf` (handout).
- Long detail → vault files; Telegram replies stay short.

## 7. Blockers / permissions needed

- **None blocking.** Git push to `Piakman/Piakman` works (SSH key authorized).
- Note: raw aircon textbook PDF is a **scan** — must stay OCR-digested; do not re-parse raw PDF.
- macOS Full Disk Access required for the iCloud-backed Obsidian vault path (already granted on this server).
