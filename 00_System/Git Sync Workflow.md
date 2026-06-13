---
type: workflow
workflow: git-sync
created: 2026-06-13
updated: 2026-06-13
tags: [git, sync, gaia-coordinate]
---

# Git Sync Workflow

This vault is intended to be synchronized through a private Git repository so Gaia and TA_YK can collaborate across machines/servers.

## Local vault path

```text
/Users/pm/Documents/Gaia_Coordinate_Vault
```

## Recommended remote repo

Use a private GitHub/GitLab repository, e.g.

```text
gaia-coordinate-vault
```

## Current status

- Local Git repository initialized on 2026-06-13.
- Default branch: `main`
- Initial commit: `317f4f4` (`Initial Gaia Coordinate vault`)
- Remote URL: `git@github.com-gaia-coordinate:Piakman/Piakman.git`
- GitHub repo: `https://github.com/Piakman/Piakman`
- Latest pushed commit: `492abfd56c3ded4b8a527bcd527c0db3e7f19d64`
- Status: pushed successfully to GitHub on 2026-06-13

TA_YK clone command:

```bash
git clone git@github.com:Piakman/Piakman.git Gaia_Coordinate_Vault
cd Gaia_Coordinate_Vault
```

If TA_YK does not have SSH access to the repo yet, Piakman must grant access or add TA_YK server's SSH deploy key/user key to the GitHub repository.

## Standard workflow

### Gaia side

```bash
cd /Users/pm/Documents/Gaia_Coordinate_Vault
git pull --rebase
git add .
git commit -m "Update coordination vault"
git push
```

### TA_YK side

```bash
git clone <REMOTE_URL> Gaia_Coordinate_Vault
cd Gaia_Coordinate_Vault
git pull --rebase
# write outputs under 05_Outputs/TA_YK/ or assigned task files
git add .
git commit -m "TA_YK update"
git push
```

## Conflict rules

- Gaia owns dashboards, task board, decision log, and integration summaries.
- TA_YK should primarily write under:

```text
05_Outputs/TA_YK/
03_Projects/<Project>/TA_*.md
```

- If TA_YK needs to change task definitions or project direction, write a proposal note first instead of editing Gaia-owned decision logs directly.

## Never commit

- bot tokens
- API keys
- passwords
- private keys
- 2FA codes
- private credential files
- large raw data unless explicitly approved
