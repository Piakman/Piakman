---
type: meeting-schedule
created: 2026-06-13
updated: 2026-06-13
tags:
  - meeting-schedule
  - zoom
  - general
---

# Meeting Schedule

ตารางนัดหมายทั่วไปของ Piakman / Gaia ไม่ผูกกับ project หรือ session ใดเป็นพิเศษ

| Date | Time | Open room | Topic | Host / Tool | Meeting ID / PMI | Link | Password | Status | Notes |
|---|---:|---:|---|---|---|---|---|---|---|
| 2026-06-15 Mon | 17:00 ICT | 16:55 ICT | Zoom meeting | Zoom PMI / Piakman host | `689 141 0214` | https://cmu-th.zoom.us/j/6891410214 | None requested | Scheduled | macOS Calendar event created in `Home`; Hermes cron job `77a1e4181fd1` will open Zoom 5 minutes before meeting. Invitation sent via Telegram DM; LINE deferred. |

## Zoom opening workflow

For the 2026-06-15 meeting, Gaia configured a local Hermes script and one-shot cron job.

### Script

```text
/Users/pm/.hermes/scripts/open_zoom_pmi_6891410214.sh
```

Behavior:

1. Opens the logged-in Zoom host meeting via URL scheme:

```text
zoommtg://zoom.us/start?confno=6891410214
```

2. Falls back to the web invitation link if needed:

```text
https://cmu-th.zoom.us/j/6891410214
```

3. Prints reminder text with meeting time, PMI, link, and password status.

### Hermes cron job

```text
job_id: 77a1e4181fd1
name: Open Zoom PMI 6891410214 before Monday meeting
schedule: once at 2026-06-15 16:55 ICT
mode: no_agent script-only
```

### Calendar

A macOS Calendar event was created in calendar `Home`:

- Title: `Host Zoom meeting - PMI 689 141 0214`
- Date/time: 2026-06-15 17:00 ICT
- Reminder: 5 minutes before
- Notes include PMI, invitation link, password status, and open-room instruction.

## Invitation text

```text
Zoom invitation ค่ะ

Topic: Host Zoom meeting
Time: Monday 15 Jun 2026, 17:00 น.
Open room: 16:55 น.
PMI: 689 141 0214
Link: https://cmu-th.zoom.us/j/6891410214
Password: ไม่มี / none requested
```

## Communication status

- Telegram DM: sent successfully.
- LINE: deferred because no unambiguous `Piakman` LINE chat target was found during GUI search; avoid sending to the wrong chat.
