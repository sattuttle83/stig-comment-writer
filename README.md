# STIG Comment Writer

A single HTML file that evaluates DISA STIG checklist rules against pasted command output and writes the checklist comment from your templates. It runs fully offline, so it can be carried into an air-gapped environment.

## Use it
1. Download `stig-comment-writer-v1.3.4.html` (the version is in the file name), copy it to the machine, and open it in Edge or Chrome.
2. Click **My info** and fill in your name, role, team and ISSO once.
3. Click **Open folder** and pick your Evaluate-STIG output folder (or **Open files** for individual checklists). Allow edit access when the browser asks, so it can save back to the files.
   In the picker, tick checklists by STIG (every server's copy at once) or by server. Combined checklists and older scans in `Previous` folders start unticked.
4. Pick a rule, paste command output, click **Evaluate**, fill in any blank fields, then **Apply**.
5. To fill several checklists from a reviewed one, open them together and use **Copy from baseline**.

Close the checklists in STIG Viewer while the app has them open. Firefox can't write back to files; there, **Save checklists** downloads copies.

## Templates
Click **Templates** to edit them or import a `.txt`. Format: a title line, a blank line, the template lines, and a blank line between templates. `[Bracketed text]` becomes a fill-in field, and the `Status:` line decides the checklist status. `[Rule Title]`, `[Discussion]`, `[Vuln ID]` and `[Rule Version]` fill in from the rule.

## Versions
See [CHANGELOG.md](CHANGELOG.md). The version is in the file name and also shows in the app header (`APP_VERSION` in the HTML).

Versions stay in the 1.3 series; each release bumps the last number (1.3.4 → 1.3.5).

To release a new version:
1. Make the change and add it under **Unreleased** in `CHANGELOG.md`.
2. Bump `APP_VERSION` in the HTML, and rename **Unreleased** to the new version and date.
3. Rename the file to the new version with `git mv`, e.g. `git mv stig-comment-writer-v1.3.4.html stig-comment-writer-v1.3.5.html`, and update the file name in this README. (`git log --follow` still shows the full history across renames.)
4. Commit, then tag: `git tag -a v1.3.5 -m "v1.3.5"` and `git push --follow-tags`.
