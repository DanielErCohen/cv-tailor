# 07 ATS checks

An ATS (applicant tracking system) is software that reads your CV into fields and often ranks candidates. Many companies use one. The checks below make your CV easy to read for a parser and for a person.

Nobody outside each vendor knows exactly how every system ranks, so treat these as good practice.

## Layout checks

- [ ] One column. No tables, text boxes, or side panels.
- [ ] No images, icons, charts or skill-rating bars. They are skipped or turned into noise.
- [ ] Contact details sit in the body of the document. Headers and footers are often skipped.
- [ ] Standard fonts (Arial, Calibri, Georgia, Times) at 10 to 12 pt.
- [ ] Simple bullets (round or dash). No unusual symbols.
- [ ] Margins at least 1.5 cm.

## Heading checks

- [ ] Standard section names: Summary, Experience (or Work Experience), Skills, Education.
- [ ] Each job shows title, company, and dates in one consistent pattern.
- [ ] Dates in one format, for example "Mar 2021 - Jun 2024".

## Content checks

- [ ] Keywords from the posting appear where your real work supports them, with the posting's spelling and acronyms. If the posting says "search engine optimization (SEO)", include both forms once.
- [ ] Skills use the standard spelling, such as "JavaScript" in full.
- [ ] Numbers carry units and periods.
- [ ] No keyword stuffing, no hidden white text. Systems and recruiters both penalize it.
- [ ] Job titles are real. If your internal title was unusual, you may add the common equivalent in brackets, such as "Growth Wizard (Marketing Manager)", only if it describes the same job.

## File checks

- [ ] File type matches the posting (DOCX or PDF). When unspecified, use a text-based PDF exported from a document. Avoid scans and pictures.
- [ ] File name is `Firstname-Lastname-CV`.
- [ ] Copy all text from the file into a plain text editor. The order should read correctly: name, contact, summary, experience newest first.
- [ ] Length: one page up to about 8 years of experience, two pages beyond.

## Quick test with Claude

> Here is my CV as pasted from the PDF. Read it like an ATS parser. List the name, email, each job title, company and dates you extracted, and anything that looks scrambled or missing.

If the extracted details are wrong, simplify the layout and test again.

## Keyword check against a posting

> Compare the keywords and phrases in job-description.md with cv.md. List the ones present, the ones missing that I genuinely have experience for, and the ones I should leave out because I lack evidence.

Add only the second group.
