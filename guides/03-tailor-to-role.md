# 03 Tailor to a role

Tailoring means choosing which true things to show first and using the employer's words for work you really did.

## Steps

1. Copy `applications/_template/` to `applications/YYYY-MM-DD-company-role/`, for example `applications/2026-03-02-acme-analyst/`. Use the date you start.
2. Paste the full job description into `job-description.md`, with the link and the date you saved it.
3. Optional but recommended: do guide 04 now, so `company-notes.md` is filled.
4. Say:
   > Use cv-tailor on applications/2026-03-02-acme-analyst.
5. Claude maps each requirement to evidence in your main CV and achievements bank. It asks up to five questions where a fact from you would turn a partial match into a strong one.
6. Claude then runs a recipient panel (CV preset) on `cv.md`, with four simulated readers: a recruiter screen, HR, the PMs who will interview you and the hiring manager. It fixes what two or more of them raise, as long as the fix uses true evidence, and writes the rest into `changes.md`.
7. Read `changes.md` first. It lists every change with before, after and why, the keywords used and left out, gaps, the readers' objections and open items.
8. Read `cv.md`. Correct anything that is not exactly true. If you remember a new fact, add it to your main CV or achievements bank, then ask Claude to update the tailored CV.
9. Run the ATS checks (guide 07) and export (guide 06).
10. Commit: "Tailor: 2026-03-02-acme-analyst". After you send it, tag the commit (guide 05).

## What Claude changes

- The summary: one title matching the posting, written for this role.
- The order of bullets, so the best evidence comes first.
- Wording, to match the posting where you did the same work.
- Which achievements from your bank appear.

## What Claude does not change

- Employers, titles, dates and education.
- Anything that would claim experience you do not have.
- Your main CV.

## The simulated readers

Claude runs a recipient panel (CV preset): four readers, each reading your CV and the posting cold as one role. They are the recruiter screen, HR, the PMs who will interview you and the hiring manager. Where Claude can start subagents (Claude Code, Cowork), it starts one per reader. They are a simulation. They show where a CV is likely to lose someone and cannot predict a hiring decision, and anything a reader says about the company needs checking. The method lives in the [`recipient-panel` skill](https://github.com/DanielErCohen/how-i-work/tree/main/skills/recipient-panel).

A chat in the Claude app does not start subagents. Fill in this brief once per reader:

```
You are <role: for example the recruiter who screens this CV>. You must decide <what they decide: for example whether to forward it to the hiring manager>. You already know <their context: for example the posting and the company>. You have <their patience: for example 30 seconds>. You say no when <their reasons>.

Read the CV below once, as this person. Then reply in under 300 words:
1. The line where you would stop reading, quoted.
2. Up to five objections, each with the line it rests on and one fix.
3. What would make you say yes.
4. One thing that works.

Posting: <paste it>
CV: <paste it>
```

Open a new chat for each reader and paste the brief with your CV. Then paste all the answers into one chat and ask it to merge the objections two or more readers share.

## Gaps

If the posting asks for something you have never done, `changes.md` lists it as a gap. Options: leave it out and apply anyway, mention related experience in the cover note, or skip the role. Adding the keyword anyway is the one option that is off the table: interviews find it quickly.

## Keywords

Use the posting's wording for work you did. If the posting says "stakeholder management" and your CV says "worked with senior leaders", switch to their phrase. Do not repeat a keyword to pad. Once per place it fits is enough.

Next: [04 Tailor to a company](04-tailor-to-company.md).
