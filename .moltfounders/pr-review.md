# PR Review Rules

## When to Run

On every agent loop cycle, scan all open pull requests.

## Skip Conditions (do not process if any apply)

- PR already has `agent:reviewed` label → skip entirely
- PR is a draft → skip (wait until it's marked ready)
- PR was opened by an agent → skip (avoid self-review loops)
- PR is from a bot (dependabot, renovate, etc.) → label `needs-human`, skip
- **PR has merge conflicts** (`mergeable = false`) → comment asking author to rebase, apply `needs-info` label, do NOT approve, skip remaining review steps entirely

## Review Steps

For each PR not skipped:

### 1. Understand what the PR does

- Read the PR title and description
- Read the diff carefully — what entries are being added, removed, or changed?

### 2. Structural checks

- Does the PR follow the format in `CONTRIBUTING.md`?
- Is the entry placed in the correct section and category?
- Does it use the correct badge format (GitHub stars badge, etc.)?
- Is the link valid? (Check the URL resolves to the right repo)
- Is the description concise and factual (not marketing language)?
- Does it include the project name in bold + link format?

### 3. Content checks (for additions)

**Open source verification:**
- Is the license OSI-approved? Check the repo's LICENSE file directly.
- Is the full code/model publicly available, or is it "open-ish" (API-only, partial weights)? If the latter → request changes, explain the standard.

**Activity check:**
- When was the last commit? If >6 months → request changes with `not-actively-maintained` label
- Are there recent releases or activity? Stars alone are not enough.

**Duplicate check:**
- Search the current README (not just the PR diff) for the project name and GitHub URL
- If duplicate → comment clearly, apply `duplicate` label, request closure

**Category fit:**
- Does it belong in the section it was placed in?
- If it could fit better elsewhere, suggest the right section

**Quality bar:**
- Is this project genuinely notable? Real adoption, useful to the community?
- Avoid listing every possible project — the list should stay curated and high-signal

### 4. For removals

- Is the reason stated? If not, ask.
- Verify the claim: is the project actually dead/closed-source/abandoned?
- If valid → approve with a note confirming your verification

### 5. For corrections

- Is the correction accurate?
- Does it maintain correct formatting?

### 6. Leave your review comment

Be specific:
- List each issue found with a clear explanation
- If approving: say exactly why it meets the bar
- If requesting changes: give actionable, friendly guidance

**Do not:** leave vague comments like "looks good" or "needs work" without detail.

### 7. Apply labels and set review status

- Always apply `agent:reviewed`
- Apply `agent:approved` if the PR meets all criteria
- Apply `agent:changes-requested` if changes are needed
- Apply relevant issue labels (`duplicate`, `not-open-source`, etc.) as needed
- Apply `needs-human` for anything that requires maintainer judgment (borderline cases, disputes, etc.)

## Important: Agent approval ≠ merge

An `agent:approved` label means the PR passed automated review. **Only the maintainer merges.** The agent never merges PRs directly.

## Edge Cases

- **PR has merge conflicts:** Already handled as a skip condition above — never approve a PR with conflicts.
- **PR fixes a broken link only:** Fast-track approve, these are unambiguously good.
- **Author disagrees with feedback:** Acknowledge their perspective, stand firm on objective criteria (license, activity), label `needs-human` for subjective disputes.
- **PR has been open >30 days with no author response:** Follow staleness rules in `staleness.md`.
- **PR adds a commercial product with an "open-source" tier:** Reject unless the core product is fully open-source. Freemium ≠ open-source.
- **PR adds something already on a sister list (e.g. awesome-llm):** Not a disqualifier — if it fits this list's scope and quality bar, it's fine.
