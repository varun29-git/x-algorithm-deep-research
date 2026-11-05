# X Algorithm Deep Research & 5-Week Organic Growth Plan

**By [Compact Intelligence](https://compactintelligence.in)** — builders of **Terminus**, a 1.5B-parameter, sub-400MB-RAM, Indic-first on-device language model. *Maximum Intelligence per Watt.*

Launching at **E-Summit'26, IIT Bombay — December 12–13, 2026**.

---

## What's in this repo

[**Compact-Intelligence-X-Deep-Research-and-5-Week-Plan.md**](Compact-Intelligence-X-Deep-Research-and-5-Week-Plan.md) — an extensive, source-code-grounded study of the open-sourced X (Twitter) recommendation algorithm, plus a complete 5-week organic growth playbook we are executing in public ahead of our launch.

The research is based on a first-hand read of [`xai-org/x-algorithm`](https://github.com/xai-org/x-algorithm) (commit `021afa4`, production defaults synced 2026-11-04), large-N posting datasets (Buffer, Sprout Social), X's official policies, and documented founder case studies.

## The short version

- The 2026 X algorithm is a **Grok-derived transformer** ("Phoenix") — no hand-engineered features. Posts are indexed by **semantic content**, so unknown accounts *can* get distribution without followers.
- Heaviest positive ranking weights: **copy-link share (20.0)**, **mutual-follow reply (20.0)**, **quote (5.0)**, **reply (5.0)**, **DM share (5.0)**, **follow-author (4.0)**. Likes: 0.708.
- A built-in **author cold-start boost** lifts original posts from accounts <50k followers into the feed — the first 2 hours decide it.
- **No verified/Premium multiplier exists in the code.** Bookmarks have no ranking weight. Every post dies in 48 hours.
- Strategy that follows: topical coherence, conversation-starting substance, dwell-optimized writing, founder-led posting, relentless consistency.

## Follow the build

- X: [@thinkcompact](https://x.com/thinkcompact) (company) · [@varundaiya](https://x.com/varundaiya) (founder)
- Web: [compactintelligence.in](https://compactintelligence.in) · [The thesis: "After the Wall"](https://compactintelligence.in/blog/after-the-wall)

*The full xAI algorithm source studied for this report (commit `021afa4`, Apache-2.0) is vendored in [`x-algorithm/`](x-algorithm/) with its license intact; the upstream lives at [github.com/xai-org/x-algorithm](https://github.com/xai-org/x-algorithm). All file:line citations in the report refer to that tree.*
