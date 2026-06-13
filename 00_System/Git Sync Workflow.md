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
- Repository default/general branch: `main` is reserved for future repo-level or other-project use.
- Active vault branch: `gaia-coordinate-vault`
- Initial commit: `317f4f4` (`Initial Gaia Coordinate vault`)
- Remote URL used by Gaia: `git@github.com-gaia-coordinate:Piakman/Piakman.git`
- GitHub repo: `https://github.com/Piakman/Piakman`
- Latest vault branch before this note update: `99df45bca6f4de523eca56b8aae55cbc0823b473`
- Status: vault moved from `main` workflow to dedicated branch `gaia-coordinate-vault` on 2026-06-13

TA_YK clone command:

```bash
git clone --branch gaia-coordinate-vault git@github.com:Piakman/Piakman.git Gaia_Coordinate_Vault
cd Gaia_Coordinate_Vault
```

If TA_YK does not have SSH access to the repo yet, Piakman must grant access or add TA_YK server's SSH deploy key/user key to the GitHub repository.

## TA_YK write access setup

TA_YK has cloned successfully, but push requires write permission.

Known blocker from AC-TA-002:

- TA_YK server authenticates to GitHub as `ClassicmanJames`
- `ClassicmanJames` currently has pull-only access to `Piakman/Piakman`
- TA_YK local commit waiting to push: `1eec43c`

Fix options:

1. Add GitHub user `ClassicmanJames` as collaborator with **Write** access to `Piakman/Piakman`.
2. Or add TA_YK server SSH public key as a repository deploy key with **Allow write access**.

After permission is fixed, TA_YK should run:

```bash
cd Gaia_Coordinate_Vault
git push
```

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
