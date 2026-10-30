# cv-tailor: map for Claude

This repo takes a job seeker from an old CV to tailored applications, with versions kept in git. The user may not be technical. Use plain words, explain any git step in one sentence, and do the git work yourself when asked.

## Folders

| Folder | Purpose |
|---|---|
| `my-cv/main-cv.md` | The main CV. Single source of truth for every claim. |
| `my-cv/achievements-bank.md` | Raw outcomes with numbers. Bullets are picked from here. |
| `applications/_template/` | Copy this per application. Never edit the template for one job. |
| `applications/YYYY-MM-DD-company-role/` | One folder per application, named with the date started. |
| `skills/` | The six skills. Read the matching `SKILL.md` before doing a step. |
| `guides/` | Plain-language walkthroughs for the user. |
| `examples/` | Made-up worked example. Use it as a format reference only. |

## Workflow order

1. `cv-intake`: build or improve `my-cv/main-cv.md` and the achievements bank.
2. `cv-review`: score the main CV, list fixes, run ATS checks.
3. `company-research`: fill `company-notes.md` in the application folder.
4. `cv-tailor`: write `cv.md` and `changes.md` from the main CV, the job description and the notes. Then run the recipient panel (CV preset), which reads it as the recipients (recruiter screen, HR, interviewing PMs, hiring manager) with read-only subagents, and record their objections and your changes in `changes.md`. Then run the ATS checks.
5. `cover-note`: write `cover-note.md`.
6. `application-tracker`: update `status.md` and the log.

Run a step only when its inputs exist. If `main-cv.md` is still a template, start at step 1.

## Rules

- Never invent experience, employers, titles, dates, tools or numbers.
- When a metric is missing, ask the user. If they do not know, leave a bracketed placeholder such as `[N]` and list it in `changes.md` under open items.
- Keep `my-cv/main-cv.md` as the single source of truth. A tailored CV may reorder, trim and reword. It may not add a claim the main CV or achievements bank does not support. New facts go into the main CV or bank first.
- Every tailored version references the job description it was tailored to: the first lines of `cv.md` link to `job-description.md` and record the date.
- Reproduce education, employers, titles and dates exactly as in the main CV.
- Domain gaps: if the job asks for something the user has no evidence for, say so in `changes.md`. Do not add the keyword.
- Use plain formatting that ATS parsers read: standard headings, no tables, no columns, no images in the CV body.
- No em-dashes in CV text. Use a comma, colon or hyphen.
- Panel objections follow the same truth rules: a fix may reorder, trim or reword real evidence. A missing fact becomes a question or a gap. Label panel output as simulated.
- Show `changes.md` to the user before they send anything. Never send or submit on their behalf.

## Git

- Commit after each finished step with a short message: `Main CV v1`, `Tailor: 2026-03-02-acme-analyst`.
- Tag the version that was actually sent: `sent-2026-03-02-acme-analyst`.
- Before the first write in a session, run `gh repo view --json isPrivate -q .isPrivate`. If it prints `true`, continue. If it prints `false`, stop and warn the user that the repo is public and a CV must not be written to it. If `gh` is not installed or not signed in, skip the check and say so.
- Never add a remote, push, or change repo visibility unless the user asks. Remind them the repo should be private.
