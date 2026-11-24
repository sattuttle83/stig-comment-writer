# Changelog

All notable changes to STIG Comment Writer are recorded here.
The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Versions stay in the 1.3 series: each release bumps the last number (1.3.2, 1.3.3, …).

## [Unreleased]

## [1.3.4] - 2026-11-24
### Added
- Rule title and Discussion shown at the top of "Fill in the template", so they're in view while writing the comment.
- Discussion shown in the rule card above the check text (read from Vuln_Discuss in .ckl and discussion in .cklb).
- Templates can use [Rule Title], [Discussion], [Vuln ID] and [Rule Version]; these fill in from the rule automatically.

## [1.3.3] - 2026-11-23
### Fixed
- Evidence now follows the selected system. Each system keeps its own pasted output and evaluation result, and switching systems loads that system's output (or its existing Finding Details) instead of keeping the first system's.
### Added
- Host names in "Checklists with this rule" are clickable to switch systems, with an Evaluated column showing each system's result.
- Apply warns when a ticked system's evaluation disagrees with the status being applied.
### Changed
- Finding Details default is now "Each system gets the output pasted for it". Systems with nothing pasted keep their existing Finding Details.
- Unfinished work saves each system's output separately.

## [1.3.2] - 2026-11-20
### Added
- **Open folder**: pick an Evaluate-STIG output folder and the app finds every .ckl/.cklb under it, for every server.
- Checklist picker: tick by STIG (every server's copy at once) or by server, filter by server, STIG, SQL instance or database name, with Tick all / Untick all for what's shown.
- Single checklists are selected by default. Combined checklists are shown but left unticked and kept out of the by-STIG list. Older scans in `Previous` folders are hidden unless you ask for them.
- SQL Server Instance and Database checklists show their instance and database name everywhere (picker, checklist table, baseline dialog), and the Where field uses host plus instance/database.
- Opening a folder with edit access lets every checklist in it auto-save.
### Changed
- Copy from baseline also swaps the SQL instance and database names, and only pre-ticks checklists of the same STIG as the baseline.
- Header shows how many servers are open instead of repeating host names.
- "Open checklists" is now "Open files"; "Open folder" is the main way in.

## [1.3.1] - 2026-11-20
### Changed
- The app file is now named with its version (`stig-comment-writer-v1.3.1.html`), so a downloaded copy shows which version it is.
- README release steps include renaming the file for each new version.

## [1.3.0] - 2026-11-20
### Added
- **Copy from baseline**: copy status and comments from one baseline checklist to any number of other open checklists, matched by Vuln ID.
- Options to copy status, comments and Finding Details, and to swap the baseline's host name for each target's host name.
- Choice of which rules to copy: only Not Reviewed on the target (default), only rules with no comment, or every matching rule.
- Preview of how many rules each checklist will get before copying.
- The app remembers the last baseline used and prefers a file with "base" in its name.
- Version number shown in the header.

## [1.2.0] - 2026-11-19
### Added
- Open several checklists at once and work on them together.
- Rule list shows each Vuln ID once, with a "Mixed" status when hosts differ and a count of how many open checklists have the rule.
- "Checklists with this rule" table: tick which hosts get the comment, see each host's status and current comment.
- "Edit this one" loads a host's existing comment into the comment box for editing.
- One Apply writes to every ticked checklist; host-specific fields (Where) get each host's name.
- Choose which host pasted output came from, and whether it goes to that host's Finding Details only, every ticked checklist, or none.
- Close all button.
### Changed
- Unfinished work is now kept per Vuln ID, so it comes back whichever checklists you reopen.
- Asks before replacing different existing comments on more than one checklist.

## [1.1.0] - 2026-11-18
### Added
- Auto-save: in Edge and Chrome, Apply writes straight back to the opened .ckl/.cklb file (File System Access API).
- Save status shown in the header, with a warning if a save fails.
- Unfinished work (pasted output, fields, chosen template) kept in the browser between sessions.
### Notes
- Firefox, or a browser where Group Policy blocks file writes, falls back to downloading the checklist.

## [1.0.0] - 2026-11-10
### Added
- Single offline HTML file; no network or install needed.
- Load .ckl (STIG Viewer 2) and .cklb (STIG Viewer 3 / STIG Manager) checklists, or paste a single rule.
- Evaluate pasted command output against the check text: registry values, "If the value for X is less than Y" policy checks, must-not-be-installed roles/features, and `Status :` output from check scripts.
- Comment templates: Open (remediation deferred), Remediated, Not Applicable, Risk acceptance, plus Not a Finding (compliant at review). Bracketed fields become fill-in boxes, auto-filled where possible.
- My info (name, role, team, ISSO, AO, environment, date format) saved in the browser.
- Template editor with .txt import.
- Apply sets status, comment and Finding Details; Save checklist exports the updated file.

[Unreleased]: ../../compare/v1.3.4...HEAD
[1.3.4]: ../../compare/v1.3.3...v1.3.4
[1.3.3]: ../../compare/v1.3.2...v1.3.3
[1.3.2]: ../../compare/v1.3.1...v1.3.2
[1.3.1]: ../../compare/v1.3.0...v1.3.1
[1.3.0]: ../../compare/v1.2.0...v1.3.0
[1.2.0]: ../../compare/v1.1.0...v1.2.0
[1.1.0]: ../../releases/tag/v1.1.0
[1.0.0]: #100---2026-11-10
