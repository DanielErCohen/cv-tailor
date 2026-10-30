# Create and adapt CV artifacts

Read [CLAUDE.md](CLAUDE.md) and the matching [`skills/`](skills/) guide before writing. Use a local private working folder or a private repository for real CVs. This public repository holds templates and made-up examples only.

## Claims and evidence

- Start with the user's confirmed [`my-cv/main-cv.md`](my-cv/main-cv.md) and [`my-cv/achievements-bank.md`](my-cv/achievements-bank.md) in their private copy. Confirm that these contain the user's facts rather than the unchanged template.
- Tailoring may reorder, trim and reword supported experience. Never invent employers, titles, dates, qualifications, tools, numbers or impact. Add newly confirmed facts to the main CV or bank before using them elsewhere.
- Keep education, employers, titles and dates consistent with the main CV. Use job-description keywords only where real experience supports them. A missing fact becomes a question or bracketed placeholder in the draft and an open item in `changes.md`.
- Preserve provenance: link each tailored CV to its `job-description.md`, record the tailoring date and explain material changes in `changes.md`. Label recipient-panel feedback as simulated; it cannot establish hiring outcomes.
- Public previews, downloads and examples must be made up from scratch. Keep real contact details, private links, source extracts, employment history and private metrics out of public exports. Renaming a real person is insufficient.

## Sources and recipes

Paths below refer to this repository. Copy templates into the user's private working folder before adapting them.

| Artifact | Source or blank | Made-up example | Recipe |
|---|---|---|---|
| Main CV | [`my-cv/main-cv.md`](my-cv/main-cv.md), [`achievements-bank.md`](my-cv/achievements-bank.md) | [`examples/marlow-quinnet/main-cv.md`](examples/marlow-quinnet/main-cv.md) | Use [`skills/cv-intake/SKILL.md`](skills/cv-intake/SKILL.md), confirm claims, then run [`cv-review`](skills/cv-review/SKILL.md). |
| Tailored CV and change list | [`applications/_template/cv.md`](applications/_template/cv.md), [`changes.md`](applications/_template/changes.md) | [`examples/marlow-quinnet/cv.md`](examples/marlow-quinnet/cv.md), [`changes.md`](examples/marlow-quinnet/changes.md) | Follow [`cv-tailor`](skills/cv-tailor/SKILL.md) using the main CV, posting and company notes. Preserve gaps and show changes for review. |
| Posting and company notes | [`applications/_template/job-description.md`](applications/_template/job-description.md), [`company-notes.md`](applications/_template/company-notes.md) | [`examples/marlow-quinnet/job-description.md`](examples/marlow-quinnet/job-description.md), [`company-notes.md`](examples/marlow-quinnet/company-notes.md) | Follow [`company-research`](skills/company-research/SKILL.md); record sources and separate confirmed facts from interpretations. |
| Cover note | [`applications/_template/cover-note.md`](applications/_template/cover-note.md) | [`examples/marlow-quinnet/cover-note.md`](examples/marlow-quinnet/cover-note.md) | Follow [`cover-note`](skills/cover-note/SKILL.md); use the same confirmed claims as the CV. |
| Application status | [`applications/_template/status.md`](applications/_template/status.md) | None shipped | Follow [`application-tracker`](skills/application-tracker/SKILL.md); record actual actions and dates supplied by the user. |

## Preview and export

Use a labeled made-up preview with an empty starting state, **Download starter** and **Copy adaptation prompt**. A public starter includes templates, the made-up example, the adaptation prompt, validation instructions and `LICENSE`. The prompt requests a confirmed main CV, permitted job inputs, an editable tailored CV and `changes.md` with open items. Public previews never load the user's private CV automatically.

Keep the CV body in plain ATS-readable formatting: one column, standard headings, simple bullets, no tables, images, charts or rating bars. Preview controls sit outside the CV body. Save the editable Markdown before exporting through [guides/06-export.md](guides/06-export.md). Check the exported file with [guides/07-ats-checks.md](guides/07-ats-checks.md), including the order of text copied from the export.

Show the user the CV, `changes.md` and unresolved claims before sending. Remove unresolved placeholders before a final application. Sending or submitting remains the user's action. Return the saved paths and checks performed; creating a preview does not authorize publication, uploads, automatic storage or service connections.
