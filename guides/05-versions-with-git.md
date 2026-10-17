# 05 Keep versions with git

Git is a history book for a folder. Each time you save a snapshot, called a commit, git remembers what every file looked like. You can compare any two snapshots and go back to either.

You do not need to learn commands. GitHub Desktop does everything below with buttons. Commands are shown for people who want them.

## The three habits

1. **Commit after each finished version.** A short message says what the snapshot is: "Main CV v1", "Tailor: 2026-03-02-acme-analyst".
2. **Tag each application you send.** A tag is a name stuck to one snapshot, so you can always find exactly what the employer received: `sent-2026-03-02-acme-analyst`.
3. **Change the main CV in its own commit.** Do not mix main CV edits with an application. The history then shows how your main CV improved.

## Set up with GitHub Desktop (no terminal)

1. Install GitHub Desktop from desktop.github.com and sign in.
2. Make a **private** copy of this repo: on GitHub, click "Use this template" and choose Private (README, "Privacy").
3. In GitHub Desktop: File, Clone repository, choose your copy, and pick a folder on your computer.
4. Work in that folder with Claude or any editor.

## Commit

In GitHub Desktop, changed files appear on the left. Tick the ones you want, type the message at the bottom left, click **Commit to main**. That is the whole step.

Terminal version:

```bash
git add -A
git commit -m "Main CV v1"
```

## Tag the version you sent

GitHub Desktop: History tab, right-click the commit you sent, **Create Tag**, type `sent-2026-03-02-acme-analyst`.

Terminal version:

```bash
git tag sent-2026-03-02-acme-analyst
```

Tag right after you press send, so the tag matches what the employer has.

## Compare versions

GitHub Desktop: open the History tab, click a commit, and read the changed lines: red is removed, green is added. To compare a tailored CV with the main CV, open both files side by side in any editor, or ask Claude: "Compare applications/2026-03-02-acme-analyst/cv.md with my-cv/main-cv.md and list the differences." The `changes.md` file already holds the reasons.

Terminal version, comparing two tags:

```bash
git diff sent-2026-03-02-acme-analyst sent-2026-03-09-globex-manager -- applications
```

## Go back to an old version

GitHub Desktop: History tab, right-click a commit, **Revert changes in commit** undoes that one change and keeps everything after it. To only look at an old file, open the commit and view the file there.

Terminal version, to view a file as it was when you sent it:

```bash
git show sent-2026-03-02-acme-analyst:applications/2026-03-02-acme-analyst/cv.md
```

## When your main CV improves

Commit the main CV change with its own message ("Add 2025 project results"). Old applications keep the version they were sent with. For a live application you want to refresh, make a new folder with today's date.

## Backups and sharing

Pushing to your private GitHub repo (the **Push origin** button) gives you an off-site backup. Keep the repo private. If you would rather not use GitHub, git works fine locally and a normal folder backup is enough.

Next: [06 Export](06-export.md).
