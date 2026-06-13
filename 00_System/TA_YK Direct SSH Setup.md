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
- Piakman unlocked the remote macOS screen for user `ClassicMan`.
- Gaia-side SSH alias `ta-yk` is configured for:
  - HostName: `10.121.33.69`
  - User: `classicman`
  - Port: `22`
  - IdentityFile: `~/.ssh/gaia_ta_yk_ed25519`
- TA_YK-side script output confirmed:
  - SSH daemon listening locally: `127.0.0.1:22` succeeded
  - reported IP: `10.121.33.69`
- Blocker: Gaia cannot reach `10.121.33.69:22` from Piakman's Mac. `nc -vz -G 5 10.121.33.69 22` timed out.
- Network diagnosis on Gaia:
  - Gaia local LAN: `192.168.1.173`
  - Gaia VPN/interface seen: `10.200.12.179`
  - route to `10.121.33.69` goes via default gateway `192.168.1.1`, not a working VPN route.

## Network reachability options

Because TA_YK reported `10.121.33.69`, direct SSH only works if Gaia/Piakman's Mac is on a route/VPN that can reach that private subnet.

Choose one:

1. Provide a reachable SSH host/IP for TA_YK from Piakman's Mac, plus port 22.
2. Connect Piakman's Mac to the same VPN/subnet as TA_YK so route to `10.121.33.69` works.
3. Install a mesh VPN on both sides, e.g. Tailscale or ZeroTier, then use the mesh IP/hostname for `HostName`.
4. Set up a reverse SSH tunnel from TA_YK to a reachable bastion/server, then Gaia connects through that bastion.
5. Continue using AnyDesk + Git/Obsidian until direct network path is available.

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
