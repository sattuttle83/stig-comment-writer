# Changelog

All notable changes to STIG Comment Writer are recorded here.
The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and the project uses [Semantic Versioning](https://semver.org/):
MAJOR for changes that break existing checklists or templates, MINOR for new features, PATCH for fixes.

## [Unreleased]

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

[Unreleased]: ../../compare/v1.3.0...HEAD
[1.3.0]: ../../compare/v1.2.0...v1.3.0
[1.2.0]: ../../compare/v1.1.0...v1.2.0
[1.1.0]: ../../releases/tag/v1.1.0
[1.0.0]: #100---2026-11-10
