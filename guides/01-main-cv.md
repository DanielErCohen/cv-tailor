# 01 Build your main CV

The main CV is the one document you improve carefully, once. Every tailored version comes from it, so time spent here pays off in every application.

## What you need

- Your old CV, a LinkedIn profile export, or both. To export from LinkedIn: Me, Settings and privacy, Data privacy, Get a copy of your data, or use "Save to PDF" on your profile page.
- 30 minutes and a quiet place. The interview asks about your work in detail.

## Steps

1. Open `my-cv/main-cv.md` and `my-cv/achievements-bank.md`. They hold the structure.
2. Start the interview. In Claude Code, with the repo open, say:
   > Use cv-intake to build my main CV. My old CV is attached.

   In the Claude app, upload the `cv-intake` skill (README, "Install") and send the same message with your files attached. With no install, paste the body of `skills/cv-intake/SKILL.md` first.
3. Answer the questions for each role, newest first. Claude asks what you owned and what changed. Give numbers with units and periods: "from 14 to 9 minutes", "about 40 customers a week", "over 6 months".
4. If you do not know a number, say so. Claude will ask for an estimate or leave a placeholder like `[N]`. It will not invent one.
5. Read the result line by line and ask yourself: can I explain this in an interview? Change or delete anything you cannot.
6. Save it as `my-cv/main-cv.md`, and keep raw outcomes in `achievements-bank.md`.
7. Commit: "Main CV v1" (guide 05).

## What good looks like

- Each bullet shows an action and a result.
- Most recent roles have the most detail.
- One job title in the summary, matching the work you want next.
- No tables, columns or images.

## Where to find missing numbers

Old performance reviews, dashboards you used, emails thanking you, project reports, job ads for your old role, and colleagues who remember. Write the source next to each number in the achievements bank.

Next: [02 Review](02-review.md).
