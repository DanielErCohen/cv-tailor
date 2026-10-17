---
name: cv-review
description: Score the user's main CV against clear criteria, list the highest-value fixes in order, and run ATS formatting checks. Use when the user asks if their CV is good, wants feedback, or after cv-intake has produced a main CV.
---

# CV review

Review `my-cv/main-cv.md`, or the CV the user pastes. Do not rewrite it unless asked. Produce a score, fixes and ATS findings.

## Scoring

Score each criterion from 0 to 5. Give one sentence of evidence per score, quoting the CV.

| Criterion | 5 means |
|---|---|
| Outcomes | Most bullets show a result next to the duty |
| Numbers | At least half of recent bullets carry an honest number with its scale or period |
| Specificity | The reader can tell the domain, scale and your ownership without guessing |
| Summary | Two to three sentences, one target title, one concrete proof point |
| Relevance order | Strongest and most recent evidence comes first in each role |
| Language | Strong verbs, consistent tense, no filler, no clichés |
| Consistency | Dates, formats, naming and punctuation follow one pattern |
| Length and density | One page for up to about 8 years of experience, two pages beyond; no padding |
| Truth and checkability | Every claim is something the user can explain in an interview |
| ATS readiness | Passes every check on the ATS checklist (see "ATS checklist" below) |

Total out of 50. Say what the total means in one line: under 25 needs a rebuild with `cv-intake`, 25 to 39 needs targeted fixes, 40 and above is ready to tailor.

## Output format

1. **Bottom line**: score, and the one thing that would raise it most.
2. **What is strong**: two or three items, first.
3. **Scores**: the table with evidence.
4. **Fixes**: a numbered list in order of impact. Each fix names the line, the problem and a concrete suggestion. Where a fix needs a number, ask the user for it. Do not guess.
5. **ATS checks**: pass or fail for each item on the ATS checklist, with the line that failed.
6. **Questions**: up to five, each one unlocking a fix.

## ATS checklist

The checklist is `ats-checks.md` beside this `SKILL.md` when the skill was installed from the zip. In the repo it is `guides/07-ats-checks.md`. If neither is available, ask the user to attach it.

## Optional panel

After the score, offer a read by the people who will screen the CV: run the recipient panel (CV preset) from the `recipient-panel` skill (recruiter screen, HR, the interviewing PMs, the hiring manager) on the main CV with a target role in mind. The brief and report format are in the `recipient-panel` skill and in step 7 of `cv-tailor`. Add the merged objections to the fixes list and label them as simulated.

## Rules

- Quote the CV. Do not give advice that could apply to any CV.
- Never invent numbers or experience in a suggested rewrite. Use `[N]` placeholders.
- Flag anything that looks inconsistent, such as overlapping dates, and ask. Do not assume it is an error.
