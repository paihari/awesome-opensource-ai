# Research Loop Rules

## Purpose

Periodically discover new open-source AI projects worth adding to the list and add them directly via a single PR.

## Frequency

Run once per week. Do not run if you already opened a research PR in the last 7 days (check open PRs with title starting with `[Research]`).

## Sources to Check

In order of priority:

1. **GitHub Trending** — `https://github.com/trending` filtered to relevant languages (Python, Rust, C++, TypeScript) and timeframe (weekly)
2. **Hugging Face Papers** — `https://huggingface.co/papers` for models with released weights
3. **Papers with Code** — new SOTA results with open implementations
4. **r/LocalLLaMA** — top posts of the week for community-discovered tools
5. **Hacker News** — search for "open source AI", "open weights", "self-hosted" in recent Show HN posts

## Qualification Criteria

A project is worth adding if it meets **all** of the following:

- OSI-approved license (or clearly open-weights with permissive use)
- Last commit within 3 months
- Genuine adoption signal: >200 GitHub stars, OR featured on HN/Reddit front page, OR cited in a notable paper
- Not already in the list (search README before adding)
- Fits an existing category in the README

## How to Add — Single PR

**Do not open issues.** Instead, open **one PR** adding all qualified entries directly to README.md:

1. Clone/pull the repo locally
2. Collect all qualifying candidates (max 5 per cycle)
3. Add each to the correct section in README.md following the existing format
4. Open a single PR titled `[Research] Add N new entries — <date>`
5. PR body lists each addition with: name, link, license, stars, why it qualifies

One PR per research cycle. Do not open individual issues or individual PRs per entry.

## Limits

- Max **5 entries per PR**
- Check existing open PRs with `[Research]` in the title — if one is already open and unmerged, do not open another
- Do not add projects already suggested in an open unmerged PR

## Edge Cases

- **Project is brand new (<1 week old) but clearly notable:** Still add it, note recency in PR body
- **Project overlaps with an existing entry:** Note the overlap in PR body, let the maintainer decide
- **No qualifying projects found this cycle:** Do nothing — do not open an empty PR
