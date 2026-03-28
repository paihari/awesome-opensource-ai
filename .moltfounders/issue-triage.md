# Issue Triage Rules

## When to Run

On every agent loop cycle, scan all open issues.

## Skip Conditions (do not process if any apply)

- Issue already has the `agent:reviewed` label → skip entirely, do not re-comment
- Issue was opened by an agent (check author against known agent names) → skip
- Issue is a GitHub-generated issue (dependabot, etc.) → skip

## Triage Steps

For each issue not skipped:

### 1. Classify the issue type

- **Addition request** — someone wants a new project added
- **Removal request** — someone wants an existing entry removed (outdated, no longer open-source, etc.)
- **Correction** — fixing a description, link, or category placement
- **Question / discussion** — not a concrete change request
- **Spam / off-topic** — unrelated to the repo purpose

### 2. Evaluate based on type

**Addition requests:**
- Does the suggested project have an OSI-approved license?
- Is it genuinely open-source (full weights/code publicly available, not "open" marketing)?
- Last commit within 6 months? (Check GitHub API)
- Does it fit an existing category in the README?
- Is it already in the list? (Search README for project name and GitHub URL)
- Does it have real adoption (stars, downloads, community)? Use judgment — a genuinely novel tool with fewer stars is ok.

**Removal requests:**
- Is the reason valid? (project dead, license changed, moved closed-source)
- Verify the claim independently if possible.

**Corrections:**
- Is the correction factually accurate?
- Does it follow the existing format?

**Questions/discussions:**
- Acknowledge, answer if you can, label `needs-human` if it requires maintainer judgment.

**Spam/off-topic:**
- Label `needs-human`, leave a polite comment explaining the repo's scope.

### 3. Comment

Leave a clear, helpful comment:
- What you found
- Your verdict (looks good / issues found / needs more info)
- Specific actionable feedback if changes are needed
- If the submission looks solid, say so clearly and that it's ready for a PR

Be friendly and constructive. Contributors put effort in — acknowledge that.

### 4. Apply labels

- Always apply `agent:reviewed` after handling
- Apply `agent:commented` if you left a comment
- Apply `duplicate`, `not-open-source`, `not-actively-maintained`, or `needs-info` as appropriate
- Apply `needs-human` if you cannot resolve it confidently

## Edge Cases

- **Ambiguous license:** Label `needs-human`, comment asking for clarification
- **Project is popular but license is unclear:** Same as above — do not approve without confirmed OSI license
- **Issue is very old (>90 days, no activity):** Follow staleness rules in `staleness.md`
- **Submitter is aggressive or rude:** Stay professional, label `needs-human`, do not engage further
