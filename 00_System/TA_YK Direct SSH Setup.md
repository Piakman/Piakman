---
type: integration-setup
integration: ssh
agent: TA_YK
created: 2026-06-13
updated: 2026-06-13
tags:
  - ta-yk
  - ssh
  - direct-access
  - no-secrets
---

# TA_YK Direct SSH Setup

Purpose: upgrade Gaia ↔ TA_YK coordination from Git/Telegram-only to direct SSH verification/automation when authorized.

## Security rule

Do not store passwords, AnyDesk passwords, SSH private keys, API tokens, or other secrets in this vault.

## Gaia-side SSH key

Gaia created a dedicated SSH keypair on Piakman's Mac.

Private key path on Gaia/Piakman Mac:

```text
~/.ssh/gaia_ta_yk_ed25519
```

Public key to install on TA_YK machine:

```text
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOZVH0nMZ5P6yaxEhyCnBvz43ats4+HPfEM8w2qHsj6l gaia-to-ta-yk@piakman-mac
```

Local SSH config alias prepared:

```sshconfig
Host ta-yk
  HostName TODO_TA_YK_HOST_OR_IP
  User classicman
  IdentityFile ~/.ssh/gaia_ta_yk_ed25519
  IdentitiesOnly yes
  ServerAliveInterval 30
  ServerAliveCountMax 3
```

## Current status — 2026-06-13

- AnyDesk app was installed on Gaia/Piakman Mac.
- AnyDesk connection to TA_YK machine was established successfully.
- Remote desktop reached macOS lock screen for user `ClassicMan`.
- Blocker: macOS login password is required to unlock the TA_YK desktop. The AnyDesk unattended password is not enough to unlock macOS.
- SSH endpoint/host/IP/port is not yet known.

## Required TA_YK/admin action

On TA_YK machine, install Gaia's public key and enable SSH/Remote Login.

### macOS command option

Run on TA_YK machine as the target user, likely `classicman`:

```bash
mkdir -p ~/.ssh
chmod 700 ~/.ssh
grep -qxF 'ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOZVH0nMZ5P6yaxEhyCnBvz43ats4+HPfEM8w2qHsj6l gaia-to-ta-yk@piakman-mac' ~/.ssh/authorized_keys 2>/dev/null || echo 'ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOZVH0nMZ5P6yaxEhyCnBvz43ats4+HPfEM8w2qHsj6l gaia-to-ta-yk@piakman-mac' >> ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys
sudo systemsetup -setremotelogin on
```

Then provide Gaia:

```text
SSH host/IP:
SSH port: 22 unless changed
SSH username: classicman unless changed
```

### Verification from Gaia

After receiving the host/IP:

```bash
ssh -o BatchMode=yes ta-yk 'hostname; whoami; pwd'
```

If port 22 is not reachable, test:

```bash
nc -vz -G 5 <TA_YK_HOST_OR_IP> 22
```
