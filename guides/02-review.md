# 02 Review your main CV

A review gives you a score, an ordered list of fixes, and ATS findings. Run it after the main CV is built, and again after you fix the top items.

## Steps

1. Say:
   > Use cv-review on my-cv/main-cv.md.
2. Read the bottom line first. It names the one fix that would raise the score most.
3. Work through the fixes in order. Answer the questions Claude asks, since most fixes need a fact only you have.
4. Update `main-cv.md` and the achievements bank. Run the review again until the total reaches 40 out of 50 or the remaining items are ones you cannot change.
5. Commit: "Main CV v2 after review".

## The ten criteria

Outcomes, numbers, specificity, summary, relevance order, language, consistency, length and density, truth and checkability, ATS readiness. Each is scored 0 to 5. The full rubric lives in `skills/cv-review/SKILL.md`.

## How to read the score

- Under 25: rebuild with `cv-intake`.
- 25 to 39: fix the listed items, then tailor.
- 40 and above: ready to tailor.

A score is a guide. If Claude's suggestion changes the meaning of something you did, trust yourself and say why.

## Get a second opinion

Ask a friend in your field to read it for 60 seconds and tell you what they remember. If it does not match what you want to be known for, change the summary and the first bullets.

For a quicker first pass, ask Claude to have simulated readers go through it: "Use cv-review on my main CV, then run the panel for a [target role] role." The readers are a recruiter screen, HR, the PMs who would interview you and the hiring manager. Their output is a simulation, so a real friend's 60 seconds still counts.

Next: [03 Tailor to a role](03-tailor-to-role.md).
