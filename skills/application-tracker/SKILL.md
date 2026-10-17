---
name: application-tracker
description: Log job applications and their status over time, in each application's status.md and a single applications/log.md table. Use when the user sent an application, got a reply, scheduled an interview, or asks where their applications stand.
---

# Application tracker

Each application has a `status.md`. The file `applications/log.md` lists all of them in one table. Create `log.md` on first use.

## Statuses

`Draft` then `Applied` then `Screening` then `Interview` then `Offer`, or `Rejected`, `Withdrawn`, `No reply`. Use these words only so the log stays sortable.

## Steps

### Log a new application
1. Make sure the folder is named `applications/YYYY-MM-DD-company-role/`.
2. Fill `status.md`: company, role, link to the posting, date applied, where it was submitted, contact if any, status.
3. Add one row to `log.md`: folder, company, role, status, date applied, next action, next action date.
4. Suggest tagging the commit that holds the CV as sent: `sent-YYYY-MM-DD-company-role`.

### Update an application
1. Add a dated line to the history in `status.md`: what happened, who said it, what is next.
2. Update status and next action in `status.md` and in the matching row of `log.md`.
3. After an interview, ask for three notes: questions asked, what went well, what to improve. Add them under the history.

### Review the pipeline
Read `log.md`. Report: counts per status, applications with no reply after 10 working days, next actions due this week. Suggest a follow-up message for each overdue one if the user wants.

## Rules

- Record only what the user tells you. Never guess a status.
- Do not send follow-ups. Draft them for the user to send.
- Keep dates in `YYYY-MM-DD`.
