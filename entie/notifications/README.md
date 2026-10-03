# Push notifications — live source of truth

The list of Entie notifications lives in a Google Sheet, not in this repo. **Always read the sheet before answering anything about notifications**, because it changes more often than this skill.

- **File:** "Entie | Push notifications"
- **Link:** https://docs.google.com/spreadsheets/d/1sKk0m2wH6y4I3p1ElYK-QMWr5qbfOa2taJWilgv3xTg/edit
- **File ID:** `1sKk0m2wH6y4I3p1ElYK-QMWr5qbfOa2taJWilgv3xTg`

## How to read it

Use the Google Drive connector: `read_file_content` with the file ID above (load the tool via ToolSearch if it is deferred). Do not guess the ID and do not search by name unless the ID stops working.

If the connector is unavailable, say so and ask the user to paste the table. Never answer from the snapshot below as if it were current.

## Sheets

| Sheet | Purpose |
|---|---|
| `Notifications` | The main table, one row per notification |
| `Легенда` | Legend for the copy-review colors and notes (RU) |

## Columns of `Notifications`

| Column | Meaning |
|---|---|
| Sender | `Device` = local notification sent by the app. `Back` = push sent by the backend |
| Platform | Usually `iOS & Android` or one of them |
| Gender | `Male`, `Female` or `Male & Female` (audience) |
| Trigger | When and under what conditions it is sent (timing, frequency, exclusions) |
| Title / Descriptions | The notification text. Variables: `[User's Name]`, `[Partner's Name]`, `[Low/Medium/High]` |
| Image | Optional image |
| Payload | Technical data, e.g. `redirect` target or `cancelPush` |
| Action buttons | Optional buttons |
| Status | See below |
| Comment | What happens on tap (deep link / screen) |

## Status values

| Value | Meaning |
|---|---|
| `Development` | Being built or already built, treat as included. The notifications is in development environment |
| `Production` | The notifications is in production environment |
| `Planned` | Agreed, not started |
| `In progress` | Being built right now, not live yet |
| `Stopped` (sic, means Stopped) | Turned off. Do not count it as active |
| empty | No status set. Say so, do not assume it is on or off or in any environment |


## What to do with it

When the user is designing a new notification or reviewing the current set:

1. **Read the sheet first**, then summarize what exists, grouped by trigger area (onboarding / paywall, pairing, cycle, daily tip, couple questions, chat).
2. **Check for overlap.** Same trigger, same audience, same time of day, or two notifications the same user could get within a short window. Call out frequency risk.
3. **Recommend what to enable or disable**, with a reason (e.g. a stopped notification that still fits the strategy, or two that compete).
4. **Write copy** for the new notification:
   - Follow `brand/voice-and-tone.md` and `brand/guardrails.md` (no medical claims, no gendered assumptions, no pressure).
   - Match the shape of existing rows: a short title, a description of one or two short sentences, same variable names.
   - Give the Trigger, Gender, Sender, Payload / tap destination and suggested Status alongside the text so it can be pasted into the sheet as a row.
   - Cycle notifications are sensitive: keep them neutral, use "your predictions", never imply diagnosis.
5. **Do not edit the sheet.** This skill only reads it. Give the user a row to paste.

## Known data quirks

- Trigger text is written by developers and is sometimes rough (typos, `12.00` instead of `12:00`). Interpret, do not quote it verbatim.
- Two rows (Male / Female follow-ups) share the same trigger and differ only by audience and copy.
- The connector returns text only, so cell fill colors from the `Легенда` sheet (yellow = polished copy, green = new copy) are not visible.
