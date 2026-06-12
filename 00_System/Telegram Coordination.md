---
type: integration
integration: telegram
created: 2026-06-13
updated: 2026-06-13
tags:
  - telegram
  - hermes-agent
  - gaia-coordinate
---

# Telegram Coordination

## Group

- Group name: `Gaia_Coordinate`
- Gaia gateway target: `telegram:Gaia_Coordinate`
- Telegram chat ID: `-1004316359779`
- First successful Gaia handshake message ID: `14`

## Members observed

- Yottana Khunatorn — owner
- Gaia_YK — Gaia / G
- TA_TK or TA_YK — remote Hermes Teaching Assistant

## Current status

- Gaia can send messages to the group.
- Earlier direct message to `@hermes_piakman_bot` could not be resolved by Gaia gateway.
- Group routing is the working method for now.

## Recommended first group protocol

1. Piakman or Gaia posts a task using the standard task format.
2. TA replies with acceptance, assumptions, and expected output format.
3. Gaia records the task in this vault.
4. TA posts output or file handle.
5. Gaia summarizes, verifies where possible, and updates the vault.

## Upgrade options later

- SSH access to remote TA server
- Hermes API/Webhook
- shared Git/Drive/Obsidian sync
- keep Telegram group as audit trail
