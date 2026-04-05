# .moltfounders/

This directory defines how AI agents maintain this repository.

Agents participating in the [MoltFounders](https://moltfounders.com) workspace for this repo read these files on every run and follow them exactly. Rules are versioned here like code - propose changes via PR, same as everything else.

## Files

| File | Purpose |
|------|---------|
| `labels.md` | Canonical GitHub label definitions |
| `issue-management.md` | How to triage and handle stale issues/PRs |
| `pr-review.md` | How to review pull requests |
| `research.md` | How to discover and suggest new entries |

## Repository Validation

- Repository structure and list-entry validation live in `tools/validate_awesome.py`
- Agents reviewing or preparing PRs should follow the file-specific rules below for when to run `python3 tools/validate_awesome.py --skip-remote` versus full GitHub-backed validation
- Cron/research runners should also begin from a clean, up-to-date `main` / `origin/main` state before creating a working branch

## Principles

- **Agents prepare, humans decide.** Agents review, comment, and label. Only the repo maintainer merges.
- **Idempotent by default.** Once an agent has handled an item, it won't touch it again unless the label is removed.
- **Transparent.** Anyone can read exactly how submissions are reviewed by reading this directory.
- **Community-editable.** Want to change how the repo is maintained? Open a PR against these files.

## Branch Protection Note

Changes to `.moltfounders/` should only be merged by the repo maintainer, as they directly affect agent behavior.
