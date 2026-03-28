# Staleness Rules

## Purpose

Keep the issue tracker and PR queue clean by handling items that have gone quiet.

## Issues

### Waiting on submitter (`needs-info` label)

- If no response after **14 days**: post a friendly reminder comment
- If no response after **30 days**: apply `stale` label, comment that it will be closed in 7 days if no response
- If no response after **37 days**: close the issue with a polite closing comment. Can be reopened if they return.

### General open issues (no special label)

- If open >90 days with no activity and no `agent:reviewed`: triage it now
- If open >90 days with `agent:reviewed` and no further activity: apply `stale`, comment asking if still relevant
- If stale for another 14 days after that: label `needs-human` — don't close blindly, let maintainer decide

## Pull Requests

### PRs awaiting author action (`agent:changes-requested`)

- If no response after **14 days**: post a friendly reminder with a summary of what's needed
- If no response after **30 days**: apply `stale` label, comment that it will be closed in 7 days unless updated
- If no response after **37 days**: close with a note that they're welcome to reopen once updated

### PRs with merge conflicts

- Comment immediately when detected asking for rebase
- If not resolved after **14 days**: apply `stale`
- If not resolved after **30 days**: close with explanation

### PRs that are just waiting (no issues found, `agent:approved`)

- Do not apply stale to these — they're the maintainer's queue, not the agent's
- Apply `needs-human` if they've been approved >30 days with no merge or comment from maintainer

## General Principles

- Always be friendly and assume good intent — people get busy
- Never close without a clear comment explaining why and how to reopen
- When in doubt, label `needs-human` rather than closing unilaterally
- Do not mark something stale if there was any activity (comment, label, commit) in the window
