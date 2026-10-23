# cv-tailor

Build one strong main CV, tailor it to each posting and keep every version. The skills work best adapted to you: [Make it yours](#make-it-yours) has a prompt for your AI.

<details>
<summary><b>Why I built it:</b> I sent over 100 CVs and got back barely a handful of replies, so I rebuilt my CV for the software that screens it.</summary>

- After the change, about 1 in 5 got a reply.
- The structure of my CV was hard for that software to read.
- It used my wording where each posting had its own. One version went to every role.
- In Harvard Business School's Hidden Workers survey (2021) of employers in the US, UK and Germany, about 6 in 10 used recruitment software. More than 9 in 10 of those let it make the first cut of applicants.
- I first built this as an app, LandMyCV, to help myself and others find a relevant job. In Apr '26 I paused the app and kept its steps here as plain files that Claude follows.

</details>

- Toolkit page: https://danielercohen.github.io/ai-pm/toolkit/cv-tailor.html
- LandMyCV write-up: https://danielercohen.github.io/ai-pm/projects/landmycv.html
- LandMyCV is the app these steps came from. I paused its development in Apr '26 and it is still online at landmycv.com.

## Who it is for

Job seekers, including people who have never used a terminal. If you can paste text into a chat, you can use it. If you can install GitHub Desktop, you get full version history with no commands.

## What you get

Six Claude skills that take you from one main CV to a tailored CV per role.

- A `changes.md` with every tailored CV, listing what changed against the main CV and why. Read it before you send.
- A "read it as them" step: simulated readers (a recruiter screen, HR, the interviewing PMs, the hiring manager) list their objections.
- An ATS formatting check.
- Templates for the main CV, an achievements bank and one folder per application.
- Seven short guides and one fictional worked example.
- The skills use only the experience and numbers you provide.

## How it works

```
my-cv/main-cv.md              the single source of truth, improved once
        |
        +-- applications/2026-03-02-acme-analyst/    tailored CV + change log, per role
        +-- applications/2026-03-09-globex-manager/
```

1. Build the main CV from your old CV or LinkedIn export (`cv-intake`).
2. Review it against clear criteria and fix the gaps (`cv-review`).
3. For each job, copy `applications/_template/`, paste the job description, research the company, and tailor (`company-research`, `cv-tailor`).
4. `cv-tailor` then has simulated readers go through the tailored CV: a recruiter screen, HR, the PMs who will interview you and the hiring manager. Their objections and what you changed go into `changes.md`.
5. Write a short cover note (`cover-note`) and log the application (`application-tracker`).
6. Commit after each step. Tag the version you actually sent.

Every tailored CV comes with `changes.md`, which lists what changed against the main CV and why, plus the simulated readers' objections. You read it before you send anything. The readers are a simulation: they show where a CV is likely to lose someone and cannot predict a hiring decision. The skills instruct Claude to use only experience and numbers you supplied. Check every claim before sending a CV.

## Quick start (15 minutes)

1. **Get the repo (2 min).** On GitHub, click "Use this template" and choose a private repository, then clone it with GitHub Desktop. Or download the repository ZIP and extract it into a local folder.
2. **Install the skills (3 min).** Pick one path under "Install".
3. **Build your main CV (6 min).** Tell Claude: "Use cv-intake to build my main CV." Attach your old CV or a LinkedIn export. Answer its questions about outcomes and numbers. Save the result as `my-cv/main-cv.md`.
4. **Review it (2 min).** Tell Claude: "Use cv-review on my main CV." Fix the top items.
5. **Save the version (2 min).** In GitHub Desktop, write "Main CV v1" and click Commit. Guide 05 covers this.

Then, per job: copy `applications/_template/` to `applications/YYYY-MM-DD-company-role/`, paste the job description into `job-description.md`, and tell Claude: "Use cv-tailor on this application folder." The "read it as them" step is part of that run. To run it on its own, or on a doc other than a CV, use the [`recipient-panel` skill](https://github.com/DanielErCohen/how-i-work/tree/main/skills/recipient-panel).

## Install

**Claude Code.** Open your copy of this repo in Claude Code. `CLAUDE.md` tells Claude to read the matching `skills/<name>/SKILL.md` before each step. To use the skills in any folder, copy them to your global skills folder. This works from any folder on a fresh Mac and clones the repo first if you have not got it:

```bash
[ -d ~/cv-tailor ] || git clone https://github.com/DanielErCohen/cv-tailor.git ~/cv-tailor
mkdir -p ~/.claude/skills
cp -Rn ~/cv-tailor/skills/* ~/.claude/skills/
cp -n ~/cv-tailor/guides/07-ats-checks.md ~/.claude/skills/cv-review/ats-checks.md
cp -n ~/cv-tailor/guides/07-ats-checks.md ~/.claude/skills/cv-tailor/ats-checks.md
```

The `-n` flag keeps any skill you already have with the same name. The last two lines put the ATS checklist beside `cv-review` and `cv-tailor`, where their `SKILL.md` files look for it when they run outside the repo.

**Claude app (desktop and web).** Download the six skill zips and upload each one: [cv-intake](https://danielercohen.github.io/ai-pm/downloads/cv-intake.zip), [cv-review](https://danielercohen.github.io/ai-pm/downloads/cv-review.zip), [cv-tailor](https://danielercohen.github.io/ai-pm/downloads/cv-tailor.zip), [cover-note](https://danielercohen.github.io/ai-pm/downloads/cover-note.zip), [company-research](https://danielercohen.github.io/ai-pm/downloads/company-research.zip) and [application-tracker](https://danielercohen.github.io/ai-pm/downloads/application-tracker.zip). In the app open Customize, then Skills, select "+", then "Create skill", then "Upload a skill", and choose the zip. Code execution must be on (Settings, then Capabilities; it is on by default, and on Team and Enterprise plans an admin turns it on). In the app, Claude cannot see your files unless you attach them, so paste or attach your main CV, the job description and company notes when a skill asks.

The ready zips are on the site: https://danielercohen.github.io/ai-pm/toolkit/cv-tailor.html. To build them yourself, run `bash tools/build-skill-zips.sh` in the [ai-pm](https://github.com/DanielErCohen/ai-pm) repo. A plain `zip` of a skill folder does not work, because the Claude app rejects some frontmatter keys, and `cv-review` and `cv-tailor` need `ats-checks.md` added. The script handles both.

**Any chat, no install.** Open a skill's `SKILL.md`, paste everything below the `---` header into a chat as your first message, then attach or paste your material. The guides in `guides/` show the exact messages.

## Make it yours

A tool works best when it fits how you work. After you set one up, paste this into your AI to adapt it to your role, your tone and your tools:

```text
I set up the cv-tailor skills from this repo. Read them, then ask me three questions about my role, my tone and the tools I use. Wait for my answers, then adapt them to fit me and tell me what you changed and why. Keep the rules that stop them from inventing experience or numbers.
```

## Versions

Your main CV changes slowly. Each application gets its own folder with a tailored CV that points at the job description it answers. Git records every change, so you can see what you sent to whom and go back to any earlier version. Guide 05 explains it in plain language.

## Create a CV artifact

Read [ARTIFACTS.md](ARTIFACTS.md) for the template and example paths, adaptation rules and preview, download and copy pattern. Build real applications from your confirmed main CV in a private working copy. Public previews and starter packs use synthetic examples only; review the CV and `changes.md` before sending.

## Privacy

A CV holds your name, contact details, employers and history. Keep it in a private place.

- Use a local folder or a private copy for your CV. On GitHub, click "Use this template" and choose Private. GitHub does not allow private forks of public repositories, and a fork of this one would stay public.
- The `.gitignore` here ignores nothing personal by default, so your files are versioned. It includes a commented option to keep `my-cv/` and `applications/` untracked instead.
- When you paste a CV into a chat, it goes to the provider you chose. Read their data settings first, and remove details you do not want shared, such as your home address.
- `examples/` is fictional. Delete it from your copy if you like.

## Guides

| # | Guide | What it covers |
|---|---|---|
| 01 | [Main CV](guides/01-main-cv.md) | Build the base CV and achievements bank |
| 02 | [Review](guides/02-review.md) | Score it and fix the gaps |
| 03 | [Tailor to a role](guides/03-tailor-to-role.md) | Match a job description honestly |
| 04 | [Tailor to a company](guides/04-tailor-to-company.md) | Research, then adjust emphasis and cover note |
| 05 | [Versions with git](guides/05-versions-with-git.md) | Commits, tags, comparing versions, GitHub Desktop |
| 06 | [Export](guides/06-export.md) | Markdown to DOCX or PDF |
| 07 | [ATS checks](guides/07-ats-checks.md) | Formatting and keyword checks |

## Layout

| Folder | Purpose |
|---|---|
| `skills/` | The six Claude skills |
| `my-cv/` | Your main CV and achievements bank |
| `applications/` | One folder per application, copied from `_template/` |
| `guides/` | The workflow in plain language |
| `examples/` | A fictional worked example |

## License

MIT, copyright Daniel Cohen 2026. See [`LICENSE`](LICENSE).
