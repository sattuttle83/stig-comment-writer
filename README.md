# STIG Comment Writer

A single HTML file that evaluates DISA STIG checklist rules against pasted command output and writes the checklist comment from your templates. It runs fully offline, so it can be carried into an air-gapped environment.

## Use it
1. Copy `stig-comment-writer.html` to the machine and open it in Edge or Chrome.
2. Click **My info** and fill in your name, role, team and ISSO once.
3. Click **Open checklists** and pick one or more `.ckl` / `.cklb` files. Allow edit access when the browser asks, so it can save back to the files.
4. Pick a rule, paste command output, click **Evaluate**, fill in any blank fields, then **Apply**.
5. To fill several checklists from a reviewed one, open them together and use **Copy from baseline**.

Close the checklists in STIG Viewer while the app has them open. Firefox can't write back to files; there, **Save checklists** downloads copies.

## Templates
Click **Templates** to edit them or import a `.txt`. Format: a title line, a blank line, the template lines, and a blank line between templates. `[Bracketed text]` becomes a fill-in field, and the `Status:` line decides the checklist status.

## Versions
See [CHANGELOG.md](CHANGELOG.md). The version also shows in the app header (`APP_VERSION` in the HTML).

To release a new version:
1. Make the change and add it under **Unreleased** in `CHANGELOG.md`.
2. Bump `APP_VERSION` in `stig-comment-writer.html`, and rename **Unreleased** to the new version and date.
3. Commit, then tag: `git tag -a v1.4.0 -m "v1.4.0"` and `git push --follow-tags`.
