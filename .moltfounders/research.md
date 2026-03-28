# Research Loop Rules

## Purpose

Periodically discover new open-source AI projects worth adding to the list and open issues suggesting them.

## Frequency

Run the research loop less frequently than triage/PR review — roughly once per week is sufficient. Do not run if you already opened a research issue in the last 7 days.

## Sources to Check

In order of priority:

1. **GitHub Trending** — `https://github.com/trending` filtered to relevant languages (Python, Rust, C++, TypeScript) and timeframe (weekly)
2. **Hugging Face Papers** — `https://huggingface.co/papers` for models with released weights
3. **Papers with Code** — new SOTA results with open implementations
4. **r/LocalLLaMA** — top posts of the week for community-discovered tools
5. **Hacker News** — search for "open source AI", "open weights", "self-hosted" in recent Show HN posts

## Qualification Criteria

A project is worth suggesting if it meets **all** of the following:

- OSI-approved license (or clearly open-weights with permissive use)
- Last commit within 3 months
- Genuine adoption signal: >200 GitHub stars, OR featured on HN/Reddit front page, OR cited in a notable paper
- Not already in the list (search README before suggesting)
- Fits an existing category in the README

## How to Suggest

Open a GitHub issue with:
- **Title:** `[Research] Add: <Project Name>`
- **Body:**
  - Project name + GitHub URL
  - One-sentence description
  - License
  - Stars + last commit date
  - Suggested category
  - Why it belongs (what makes it notable)
  - Source where you found it

Apply label `agent:suggested` to the issue.

## Limits

- Open at most **3 research issues per cycle** — avoid flooding the issue tracker
- If you find more than 3 good candidates, pick the most notable ones
- Do not suggest projects you've already suggested (check existing issues with `agent:suggested` label first)

## Edge Cases

- **Project is brand new (<1 week old) but clearly notable:** Still suggest it, note recency explicitly
- **Project is from a major lab (Meta, Google, Microsoft) with open weights:** Strong signal, suggest it
- **Project overlaps heavily with an existing entry:** Note the overlap in the issue, let the maintainer decide
