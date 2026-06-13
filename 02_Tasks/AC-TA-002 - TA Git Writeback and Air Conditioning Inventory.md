---
type: task
id: AC-TA-002
status: active
owner: TA_YK
project: Air Conditioning
priority: 1
created: 2026-06-13
due:
tags: [task, air-conditioning, ta, git-sync]
---

# AC-TA-002 - TA Git Writeback and Air Conditioning Inventory

## Goal

Verify that TA_YK can use the shared Git/Obsidian vault in both directions and start an inventory of the Air Conditioning teaching-document work.

## Context

TA_YK has cloned the shared vault from:

```text
https://github.com/Piakman/Piakman
branch: gaia-coordinate-vault
```

Next step is to prove TA_YK can:

1. pull latest branch state
2. create/edit files in the vault
3. commit and push back to GitHub
4. report the commit hash in Telegram

## Required TA_YK output

Create this file in the cloned vault:

```text
05_Outputs/TA_YK/AC-TA-002 - Air Conditioning Status.md
```

The file should contain:

1. Confirmation of repo path on TA_YK server
2. Current branch name and latest commit before editing
3. Current Air Conditioning teaching-document status
4. Existing sections/drafts already created
5. Proposed next 3 tasks for TA_YK
6. Preferred output format for long teaching documents
7. Any blockers or permissions needed

## Commands for TA_YK

```bash
cd Gaia_Coordinate_Vault
git checkout gaia-coordinate-vault
git pull --rebase
mkdir -p 05_Outputs/TA_YK
```

Then create/edit:

```text
05_Outputs/TA_YK/AC-TA-002 - Air Conditioning Status.md
```

Commit and push:

```bash
git add 05_Outputs/TA_YK/AC-TA-002\ -\ Air\ Conditioning\ Status.md
git commit -m "TA_YK Air Conditioning status inventory"
git push
```

## Telegram report requested

After pushing, TA_YK should reply in `Gaia_Coordinate` with:

```text
AC-TA-002 done
commit: <commit hash>
file: 05_Outputs/TA_YK/AC-TA-002 - Air Conditioning Status.md
blockers: <none/list>
```

## Gaia verification plan

After TA_YK reports completion, Gaia will:

1. `git pull --rebase`
2. verify the output file exists
3. read and summarize TA_YK status for Piakman
4. update task board / decision log if needed
