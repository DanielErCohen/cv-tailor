# 06 Export to DOCX or PDF

Your CV lives as markdown, which is plain text with simple marks. Most employers want DOCX or PDF. Two ways to get there.

## Option A: paste into Google Docs (no install)

1. Open `cv.md` in any text editor or on GitHub. Copy the whole text.
2. In Google Docs: Tools, Preferences, tick **Enable Markdown**, then paste with Edit, **Paste from Markdown**. Headings and bullets convert.
3. Choose a plain font such as Arial, Calibri or Georgia at 10 to 11 pt. Margins of about 2 cm.
4. Delete the "Tailored for" lines and any leftover comments.
5. File, Download, as .docx or PDF.

Word also works: paste the text, then apply Heading 1, Heading 2 and bullet styles.

## Option B: pandoc (one command)

Pandoc is a free converter. Install from pandoc.org, or `brew install pandoc` on Mac.

```bash
pandoc cv.md -o cv.docx
```

For PDF you need a PDF engine such as `weasyprint` or a LaTeX install:

```bash
pandoc cv.md -o cv.pdf --pdf-engine=weasyprint
```

To use your own look, make one DOCX styled the way you like, then reuse it:

```bash
pandoc -o reference.docx --print-default-data-file reference.docx
# edit reference.docx styles in Word, then
pandoc cv.md -o cv.docx --reference-doc=reference.docx
```

## Before you send

- Remove the "Tailored for" header lines and HTML comments. A recruiter does not need them.
- Name the file `Firstname-Lastname-CV.pdf`.
- Run the checks in [07 ATS checks](07-ats-checks.md) on the exported file: select all text in the PDF and paste it into a plain text editor. If the order is scrambled, fix the layout.
- Send DOCX when the posting asks for it or says the system parses CVs. Send PDF otherwise, since it keeps its layout.
- Save the exported file in the application folder and commit, then tag (guide 05).
