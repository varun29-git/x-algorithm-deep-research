# Deep Research: The Open-Sourced X Algorithm & A 5-Week Organic Growth Plan for Compact Intelligence

**Prepared:** November 5, 2026
**Objective:** Grow Compact Intelligence's X presence organically and credibly from ~zero before the Terminus model launch at IIT Bombay's E-Summit'26 (December 12–13, 2026).
**Method:** First-hand study of the actual open-sourced algorithm source code (`xai-org/x-algorithm`, cloned and read locally at commit `021afa4`, synced to production defaults 2026-11-04), plus third-party analyses, large-N posting datasets (Buffer 18.8M posts, Sprout ~2B engagements), founder case studies, X's official policy documents, and a full audit of Compact Intelligence's public footprint.

---

## 1. Executive Summary

The 2026 open-sourced X algorithm is a fundamentally different machine from the 2023 `twitter/the-algorithm` release. It is a Grok-derived **transformer** system ("Phoenix") that has eliminated hand-engineered engagement features. Everything an account needs to know to grow is now, for the first time, readable in actual production code — including the real numeric ranking weights, which were only published on August 13, 2026 and are cron-synced from production.

The core findings that should drive Compact Intelligence's strategy:

1. **With 0 followers, in-network distribution is exactly zero.** The in-network source (Thunder) only serves posts from accounts a viewer follows. All early reach must come from **Phoenix content-based retrieval** (which indexes every new post by *semantic content*, not popularity) and the **author cold-start boost** (a real slot-injection mechanism for authors under 50k followers). This is genuinely good news: the 2026 system is *designed* to surface unknown accounts if the content reads well to the model.
2. **The ranking score is a weighted sum of predicted engagement probabilities.** The five biggest positive weights are: **share-via-copy-link (20.0)**, **reply from a mutual-follow viewer (5.0 + 15.0 boost = 20.0)**, **quote (5.0)**, **share-via-DM (5.0)**, **reply (5.0)**, **follow-author (4.0)**. Likes are worth 0.708. The practical translation: write posts people *send to friends* and *talk back to*, not posts people merely like.
3. **Dwell is now a first-class citizen.** As of the Oct 8/13, 2026 updates, retrieval is trained to surface "posts people read all the way through," and ranking carries explicit dwell terms. Substance is literally algorithmically rewarded — this favors Compact Intelligence's thesis-driven, technical content over engagement bait.
4. **There is no verified/Premium multiplier anywhere in the 2026 ranking code.** The 2023-era 2–4× blue-tick boost is gone. Premium still matters behaviorally (longer posts, edit, and a large correlational reach gap in Buffer's 18.8M-post study), but the tick itself buys nothing in the scoring function.
5. **Bookmarks have no ranking weight** (they feed the model as an input feature only); "1 report = −468 likes" is a viral misreading (weights multiply *predicted probabilities*, not counts); there is no explicit external-link penalty in the new code (though free-account link posts still perform terribly in practice — put links in the first reply).
6. **Every post dies in 48 hours** (hard age filter), and **a viewer never sees the same post twice** (seen-posts filters). There is no back-catalog compounding. Growth = relentless consistency + topical coherence so the transformer learns exactly who to show you to.
7. **Realistic outcome for 5 weeks of disciplined execution: 300–1,000 followers; 1,000–3,000 if one post breaks out.** No verified case study reached 10k in 5 weeks. The durable assets built in this window are the reply-network, the content archive, and the launch-day distribution template.
8. **The launch weekend (Dec 12–13) is a Saturday–Sunday** — the weakest engagement window of the week. The plan therefore treats the event as a *content-generation engine* and pushes the biggest algorithmic strikes on the Tue–Thu before and the Tuesday (Dec 15) after.

The full 5-week, phase-by-phase playbook is in Section 7; the event playbook in Section 8; credibility fixes (your website currently has placeholder social links and a `hello@gmail.com` contact — these *will* get noticed when a post travels) in Section 9.

---

## 2. How This Research Was Done (and What Couldn't Be Verified)

**Primary source — the code.** The repository `github.com/xai-org/x-algorithm` (created Jan 19, 2026; ~34k stars) was cloned locally and studied directly. All weights, filter lists, and constants below carry `file:line` citations from that clone. Per the repo README, `home-mixer/params/param.rs` is "mirrored from config feature-switch defaults" and cron-synced from production (last sync stamp: 2026-11-04). X's own caveat applies: live experiments on ≥10% of traffic "aim" to be visible but overrides can exist; the Grox LLM classifier prompts and some botmaker rules are withheld.

**Company audit.** Live fetches of compactintelligence.in (all pages + blog), MCA/registry aggregators (Tracxn, QorpIQ), X profiles, LinkedIn, E-Cell IIT Bombay's official site, and Indian startup press.

**Growth evidence.** X's official policy pages (authenticity, automation, search), Buffer's 18.8M-post and 1.7M-post studies, Sprout Social's 2026 timing study, on-record founder interviews (Tony Dinh, Arvid Kahl, Dagobert Renouf), press-documented launches (Devin, Sora, Sarvam, Krutrim, Cluely), and third-party algorithm analyses (HN threads, MediaNama, doomers.ai).

**Could not verify (and treated as unknown):** Instagram presence for the brand (login-walled); any public confirmation of the E-Summit launch slot; production experiment overrides; the exact in-/out-of-network percentage split (it is emergent, not a constant); live model checkpoints.

---

## 3. Company Audit: Where Compact Intelligence Stands Today

### 3.1 Verified facts

| Item | Finding | Source |
|---|---|---|
| Legal entity | COMPACT INTELLIGENCE PRIVATE LIMITED, CIN U62013MR2026PTC478026, incorporated **Jul 2, 2026**, ROC Mumbai; registered address Aurangabad, Maharashtra | Tracxn/QorpIQ MCA data |
| Directors | **Pratik Jayesh Daiya** and **Varun Jayesh Daiya** (appointed Jul 2, 2026) | MCA data |
| Product | **Terminus** — 1.5B-parameter "compact language and reasoning model," <400MB RAM at runtime, 7+ Indic languages, on-device/Indic-first positioning | compactintelligence.in/terminus |
| Thesis | **"After the Wall"** (blog essay by Varun Daiya): Moore's Law ending → GPU brute-force becomes economically capped → **1-bit/ternary LLMs** (BitNet-style, ~1.58 bits/weight, multiplication-free, claimed 55–80% energy reduction) → sovereign on-device AI for "a billion people holding phones." Second essay: "Ink, Bits and Tokens" | compactintelligence.in/blog |
| Tagline | "Maximum Intelligence per Watt" | site + X bios |
| Company X | **@thinkcompact** — joined Oct 20, 2026; **0 posts, 1 follower**, 3 following; not verified | x.com/thinkcompact |
| Founder X | **@varundaiya** — joined Oct 2021; **27 followers, 520 following, 192 posts**; individually verified (Premium); bio "building @thinkcompact"; posts on AI energy/efficiency, a "Bifocal" agent research framework, an "ISRO model" post | x.com/varundaiya |
| LinkedIn | linkedin.com/company/compactintelligence exists (2–10 employees, Founded 2026) | LinkedIn |
| Instagram | could not be verified (login-walled) | — |
| Press | **zero** coverage in Inc42/YourStory/Entrackr/ET; only registry traces | press search |
| E-Summit'26 | **Dec 12–13, 2026 confirmed**, 22nd edition, "Perihelion of Endeavour," IIT Bombay Powai; formats include Startup Expo, Ten Minute Million (₹3.5M pitch), Living Lab, Networking Arena, Content Creation Conclave | ecell.in/esummit |

### 3.2 Credibility gaps found (fix before any post travels)

These matter because the growth strategy below will send journalists, VCs, and engineers to your properties:

1. **Website footer social icons link to bare roots** (`x.com/`, `instagram.com/`, `linkedin.com/`) — not your real handles.
2. **Contact email is a placeholder: `hello@gmail.com`.**
3. **Leftover Framer template pages are live** (`/work/lumin`, `/work/mira`…) and the `/blog` index still carries the template's "Alsham Studios" brand-design copy.
4. **@thinkcompact has zero posts and is not verified**; @varundaiya follows 520 with 27 followers (a follow-ratio that reads as a new account — fine, but expect slow initial follow-backs).
5. The strongest asset — the "After the Wall" thesis — is currently only a blog essay. It has never been adapted into X-native formats.

### 3.3 Strategic read

You are pre-everything: no followers, no press, no public product. But the *ingredients* are unusually well-matched to how the 2026 algorithm rewards content: a real thesis (post-Moore efficiency), a concrete artifact coming (Terminus 1.5B, <400MB RAM), an India-first narrative that Indian tech X demonstrably amplifies (Sarvam, Krutrim, Dhravya Shah), a young-founder underdog story, and a physical stage (E-Summit). The play is not "growth hacking"; it is **making the transformer understand exactly what you are about, then feeding it substance for 38 straight days.**

---

## 4. The Algorithm, From the Source Code

### 4.1 The pipeline (what happens every time someone opens For You)

The feed is assembled per-request by `home-mixer` (Rust) on the `candidate-pipeline` framework. Stages: **sources → hydration → filters → scoring → selection → post-selection filters → blending** with ads/Who-to-Follow/prompts.

**Candidate sources (queried in parallel):**

| Source | What it is | Default budget | Can a 0-follower account enter? |
|---|---|---|---|
| `thunder/` (in-network) | Recent posts from accounts the viewer *follows* | 1200 | **No.** Zero followers = zero in-network impressions. |
| Phoenix retrieval (out-of-network) | Two-tower transformer: user embedding vs. precomputed post index (10.24M–28.67M posts) | 1000 (+200 cold-start) | **Yes — the main path.** Every new post is indexed at creation via semantic IDs regardless of engagement. |
| `simclusters/` | Co-engagement clusters of accounts/posts | 800 | Effectively no — clusters are built from who *favorites* posts. |
| `popular_posts_source` | ~500 globally popular recent posts, view-count ranked | 500 | No (view-count driven). |

Scoring: `PhoenixScorer → RankingScorer → VMRanker`. A `FairShareRankingFilter` allocates the 2,800-candidate scoring budget proportionally across sources. Final feed: ~35 posts + modules (`config.rs:17-22`).

### 4.2 Phoenix: the Grok-derived transformer that replaced hand-engineering

From `phoenix/README.md` and code:

- **Both retrieval and ranking are transformers** (JAX training, Rust serving). The January 2026 README states verbatim: *"We have eliminated every single hand-engineered feature and most heuristics from the system. The Grok-based transformer does all the heavy lifting by understanding your engagement history."*
- **Production ranking model:** embedding 2560, 8 layers, GQA 20/4 heads, history length 1022 actions, 64 candidates per pass, 64-action discrete taxonomy + 8 continuous dwell heads (`phoenix/README.md:397-418`).
- **Candidate isolation:** candidates cannot attend to each other during inference — your post's score doesn't depend on what else is in the batch; scores are cacheable and consistent.
- **Semantic IDs:** every post is represented by residual-quantized codes (6 levels × 256) over its *multimodal content embedding*, plus hashed author IDs. This is the single most important architectural fact for a new account: **the model represents posts by what they say, not by who posted them.** Posts on the same topic share SID prefixes — so topical consistency makes you retrievable alongside content the viewer already engages with.
- **No vocabulary problem:** hash embeddings mean "a new post is representable immediately."
- **Context features the model reads:** viewer country/language/location/age/gender, installed apps, timezone and **local hour-of-day**, surface, post age; history positions carry action embeddings + dwell time. Viewer profile features even include blockers/muters counts and recent search queries (`recsys.proto:78-98`).
- **Retrieval training (Oct 13, 2026 update):** three heads — `home` (favorites as positives), `immersive` (fav, reply, quote, retweet, video-quality-view, follow-author, bookmark, share), and `ld`/long-dwell (positive = "posts people read all the way through," head weight 0.75). The Oct 8 update improved dwell-time estimation in ranking.

**Translation for content strategy:** there is no keyword SEO and no feature gaming left — there is a language model reading your post and deciding who would engage with it. Write clearly, stay on-topic, and write things people finish reading.

### 4.3 The scoring function — exact weights from production defaults

`Final Score = Σ weight_i × P(action_i)` + continuous dwell terms, then post-fusion multipliers. From `home-mixer/params/param.rs` (synced 2026-11-04) and `xai-value-model/scoring.rs`:

| Signal (predicted probability the viewer does this) | Weight | Code |
|---|---|---|
| **Share via copy link** | **20.0** | `param.rs:450-455` |
| **Reply (viewer is a mutual follower of author)** | **5.0 + 15.0 = 20.0** | `param.rs:408-414`, `weights.rs:86-93` |
| Quote | 5.0 | `param.rs:457` |
| Reply (general) | 5.0 | `param.rs:408` |
| Share via DM | 5.0 | `param.rs:444-449` |
| Follow author | 4.0 | `param.rs:470-475` |
| Share (generic) | 2.118 | `param.rs:443` |
| Retweet | 1.0 | `param.rs:421` |
| Favorite (like) | 0.708 | `param.rs:402-407` |
| Click | 0.274 | `param.rs:434` |
| Open link | 0.2 | `param.rs:435` |
| Dwell (discrete) | 0.05 | `param.rs:456` |
| Continuous click-dwell time | 0.385/sec-ish | `param.rs:500-505` |
| Continuous dwell time | 0.0075 | `param.rs:494-499` |
| Photo expand / quoted click | 0.05 | `param.rs:422-427` |
| Post unexplored | 0.015 | `param.rs:476-481` |
| Video open / VQV / profile click | 0.0 | `param.rs` |
| **Not interested** | **−53.07** | `param.rs:507-512` |
| Block author | −31.2 | `param.rs:513-518` |
| Mute author | −58.8 | `param.rs:519-524` |
| Report | −234.0 | `param.rs:525` |
| Not dwelled | −0.02 | `param.rs:526-531` |

**Critical interpretation rule (X's own docs):** these weights multiply *predicted per-viewer probabilities*, not raw counts. "1 report cancels 468 likes" is explicitly wrong — the baseline P(report) is >1000× lower than P(like). The right reading is *directional*: the system works hardest to predict and avoid negative feedback, and among positives it pays most for **private sharing (copy-link/DM), conversation (reply/quote), and follow-through (follow-author, dwell)**.

**Bookmarks:** NOT a scored term in `ValueModelWeights` (`weights.rs:6-48`, `scoring.rs:102-217`). Bookmarks are a candidate input feature (`candidate.rs:109,357`) and one of the 18 "positive engagement" actions that build a viewer's interest history (`viewer_history.rs:13-32`). Useful for the model's understanding, but "bookmark bait" has no direct multiplier.

**What the model can even see:** the raw behavior enum (`recsys.proto:451-692`) includes fav, reply, quote, retweet, follow, block/mute, report, not-interested, click, profile-click, open-link, **click-hashtag**, share/copy-link/DM, bookmark, photo-expand, video playback at 25/50/75/95%/complete + watch-time, **external-link session dwell buckets (<3s…>60s)**, detail-dwell, take-screenshot, translate-click, grok-analyze, reply-downvote, and more — compressed into a 64-dim action head. Continuous heads track dwell-time, click-dwell-time, profile-visit-secs, video-continuation.

### 4.4 The author cold-start boost — your single most important mechanism

`home-mixer/scorers/author_cold_start.rs`, params at `param.rs:607-679`. **Enabled by default**, this is a deliberate small-account distribution lever:

- **Eligibility:** *original posts only* (no replies, no reposts), author **≤ 50,000 followers**, post **≤ 2 hours old**, **< 200 Home impressions**, currently scoring in the top 97%.
- **Mechanism:** per request, **one** eligible post is lifted to feed slot index **15** (`ColdStartSlotMin/Max = 15/16`; Rust's `15..16` always yields 15 — the 16th position, 1-indexed).
- **Selection:** Thompson sampling over `Beta(0.75 + favs, 49.25 + (impressions − favs))` — i.e., among your cold posts, the one with the best *early like-rate* wins the injection; top-2 sampled, then highest model score.

**Implications:** (a) your best content must be **original posts**, never replies; (b) the **first 2 hours** decide the cold-start lottery — post when your target audience is awake and when your existing network can engage early; (c) early likes aren't vanity — they are literally the reward signal of the boost's bandit.

### 4.5 Filters: the gates before scoring

Wired in `phoenix_candidate_pipeline.rs:420-444`; `Filter::enable()` defaults to true unless overridden:

- **`AgeFilter` — drops posts older than 48 hours** (`config.rs:39`). Every post has a 2-day lifespan, period.
- `OONRetweetReplyFilter` — **drops out-of-network reposts and out-of-network replies** (the `EnablePhoenixOonReplies` exception defaults to false). Your replies to big accounts will *not* ride the For You feed — they work through the *conversation/reply section* (a separate ranking system not in this repo) and through profile clicks, so the "reply guy" strategy still works, just not via feed distribution.
- `PreviouslySeenPostsFilter` + `PreviouslyServedPostsFilter` + Thunder source-level `seen_ids` exclusion — **a viewer is essentially never re-served the same post.** Repeat impressions are not a lever; new posts are.
- `ViewerMutedKeywordFilter` — real tokenizer (hashtags, mentions, phrases, case/accents/CJK). If your niche's audience mutes "AI," you vanish — another reason to lead with substance over buzzword-stuffing.
- `AuthorSocialgraphFilter` — drops authors the viewer blocks/mutes, and authors who block the viewer.
- Dedup filters, `IneligibleSubscriptionFilter`, `OONNsfwSimclustersFilter`, retweet dedup; post-selection: `VFFilter`, `AncillaryVFFilter`, `DedupConversationFilter`, `VideoCarouselFilter`.
- Off by default: `NewUserMinEngagementFilter`, holdout filters.

### 4.6 Final-stage economics: diversity, OON discount, DPP

From `vm-ranker/params.rs` and `xai-value-model/scoring.rs`:

- **Out-of-network discount:** OON posts are multiplied by **0.75** (`OonWeightFactor`; 0.5 for topic requests). You start every cold impression at a 25% handicap versus followed accounts — all the more reason the *content* must win on predicted engagement.
- **Author diversity:** enabled, decay 0.5, floor 0.25 — your k-th post in the same feed is multiplied by `(1−floor)·decay^k + floor` (2nd post ≈ 0.625×). **Posting bursts self-compete.** Space your posts hours apart; never expect two posts to ride the same feed.
- **DPP rerank:** a determinantal point process over post embeddings (`DppEnabled`, theta 0.65, applied to top 150) trades a little score for dissimilarity — **a feed won't show the same *topic* too many times either.** If your post is a near-duplicate of what's already viral that hour, you're diversity-throttled. Have a distinct angle.
- **New-viewer suppression:** `NewUserOonWeightFactor = 0.00001` — brand-new *viewers* see almost no out-of-network content. Irrelevant to you as an author, but explains why brand-new follower accounts don't help.

### 4.7 Safety and spam systems (why "professional, not spammy" is enforceable law)

Ranking is separate from visibility. `visibility-filtering/` decides ALLOW/NOTICE/INTERSTITIAL/DROP per post-viewer pair; first DROP rule wins, and **out-of-network recommendations get an extra drop-only rule set** (e.g., high-recall spam labels drop posts *only for non-followers* — fatal for a 0-follower account that lives on OON). Labeling/enforcement stack in the repo: `grox/` (LLM classifiers for spam/adult/violence; prompts withheld), `botmaker-rules`, `scarecrow`, `agatha` (blocks/reports/spam-reports relative to favorites), `bdsm` (behavioral-sequence inauthenticity), `user-cred-v2` (PageRank over the follow+engagement graph), `abuse-enforcement-service`.

X's official policy documents make the behaviors explicit: follow churn, indiscriminate following, **engagement pods/coordinated engagement**, bought engagement, **duplicate or near-duplicate copypasta posts**, post-delete-repost cycles, bulk unsolicited replies/mentions/DMs, excessive unrelated hashtags, and multi-account amplification are all manipulation; penalties include reach restriction (exclusion from search/trends/For You), downranking, and suspension. Automation rules (updated Apr 2026) ban non-API automation and require written approval for AI reply bots. **One mitigating fact:** code comments state coordinated *off-timeline* mass-reporting has no ranking impact — brigading is largely ineffective.

### 4.8 The transparency tool won't help you yet

`under-the-hood/` exposes per-user visibility reports, but eligibility requires **account age ≥ 365 days AND ≥ 10 posts in the prior month** (`underTheHoodReport.User.strato:18-22`). A new account flies blind on labels — stay conservative.

### 4.9 What is NOT in the code (myth-busting)

| Claim | Verdict |
|---|---|
| Verified/Premium gives a ranking multiplier | **False in 2026 code.** No `verified`/`premium` field anywhere in scoring inputs, weights, or vm-ranker (grep-verified). The 2023 stack had hardcoded 4.0×/2.0× multipliers; they are gone. The ~10× Premium reach gap in Buffer's 18.8M-post study is real but correlational/behavioral. |
| Bookmarks are a super-signal | **False** as a ranking weight (input feature only). |
| External links are hard-penalized | **No explicit penalty in code** — `open_link` even has +0.2 weight, and external-link dwell buckets are *history features*. In practice, free-account link posts still crater (Buffer: 0% median engagement) — behavioral, not a code penalty. Put links in the first reply anyway. |
| Replies from big accounts ride For You | **False** — OON replies are dropped as feed candidates. They work in reply sections (separate system). |
| Mass reporting kills reach | Largely **ineffective** per code comments (personalized predictions; off-timeline actions don't count). |
| Posting at a magic hour boosts you | **No scheduler in code.** Local hour-of-day is a *feature* the model conditions on — timing matters only because engagement probability varies with audience availability. |

---

## 5. The Zero-Follower Growth Equation

Putting the code together, a 0-follower account's post reaches people through exactly one mechanical path:

**Post created → indexed by Phoenix via semantic IDs (content-based) → retrieved into OON candidate pools of viewers whose engagement history matches the topic (HOME_COLD/ZERO_FAV datasets, budget ~200/request) → survives 18 filters → scored by the transformer (× 0.75 OON discount) → possibly lifted to slot ~15 by the cold-start bandit if early like-rate is good → shown to a handful of strangers → their engagement (or not-interested) trains the model on who you are.**

Every strategic rule follows from that chain:

**Rule 1 — Topical coherence is distribution.** Semantic IDs mean posts cluster by content. If you post AI efficiency on Monday, memes on Tuesday, politics on Wednesday, the model cannot form a stable "who engages with this author" prior, and your retrieval pool scatters. **Pick 3–4 pillars and never leave them** (Section 6.2).

**Rule 2 — Optimize for the expensive signals.** Copy-link share (20) and DM share (5) are *private* sharing — in India, that's "sent to a WhatsApp group." Write posts people forward: a stunning fact, a demo that must be seen, a take worth arguing about. Replies/quotes (5) reward *conversation-starting* — end with a genuine question or a claim defensible people can push on. Follow-author (4) rewards posts that make strangers think "I need to watch this account" — i.e., serialized content with a tomorrow.

**Rule 3 — Write to be finished.** Dwell is in retrieval training and ranking. Long-form posts (you have Premium — use long posts), tight threads where each post earns the next, and native video with completion all feed dwell/completion signals. Sloppy first lines cost you the `not_dwelled` −0.02 and starve the `ld` retrieval head.

**Rule 4 — The first 2 hours are the lottery window.** Cold-start eligibility expires at 2h; the bandit's reward is early like-rate. Post when your audience is awake, make sure your (small but real) network sees it fast, and reply to every early comment — author activity in the thread correlates with reply predictions.

**Rule 5 — Never trigger a negative.** For an OON-dependent account, one `not interested` (−53) or mute (−58.8) outweighs dozens of likes' worth of probability mass. No engagement bait, no hashtag clouds, no off-topic provocation, no repeated @-mentions of big accounts (reads as spam to both classifiers and humans).

**Rule 6 — Consistency beats brilliance.** 48h lifespan + no re-serving means there is no catalog effect; the feed is a daily lottery where tickets = posts × retrieval match. Buffer's data: median post gets 4 engagements, mean 328 (σ=5,159) — extreme variance. You cannot predict which post travels; you can only buy more, better tickets.

**Rule 7 — Convert engagement into mutuals.** The mutual-follow reply boost (5+15=20) is the single largest author-controllable multiplier. When genuine niche accounts engage, follow back and talk with them. Ten real mutuals in the efficiency-ML community are worth more than 1,000 passive followers for early distribution.

**Rule 8 — One post per feed window.** Author-diversity decay (0.5^k) and DPP topical throttling mean two posts in the same window cannibalize. Max 2–3 original posts/day, spaced ≥4 hours, each on a different pillar.

---

## 6. How Others Actually Did It (Evidence, Not Vibes)

### 6.1 Founder case studies

- **Tony Dinh (@tdinh_me) — the archetype.** ~2 years of daily build-in-public before launching TypingMind days after the ChatGPT API dropped (Mar 2023). ~70k followers at launch; $1k→$10k/day revenue in 10 days, driven entirely by X. His own words: "If that tweet didn't blow up, if I didn't have 70k followers, I don't think the product would have seen the light of day." *Lesson: the launch post works because of the 2 years of receipts behind it. You have 5 weeks — so your receipts must be compressed: numbers, demos, failures, shipped artifacts, every day.*
- **Dhravya Shah (@dhravya) — the Indian precedent.** Mumbai teenager, left the IIT path, built Supermemory in public on X, raised $3M with Google-exec participation. Indian press framed his X presence as central to his Silicon Valley visibility. *Lesson: young Indian founder + technical substance + X-native documentation is a proven route — and E-Summit press will love the parallel.*
- **Marc Lou, Arvid Kahl, Jon Yongfook, Dagobert Renouf** — all converged on: daily cadence, radical transparency with real numbers, launches treated as recurring content (not one-off events), and a personality differentiator (Dagobert used humor/memes for a *logo-design* SaaS).
- **Cluely (Roy Lee) — the cautionary tale.** Provocation-driven virality raised $15M from a16z; in 2026 Lee admitted the $7M ARR he'd claimed was fabricated. *You explicitly want "professional, not spammy" — the algorithm and the community both eventually audit substance. Never ship a number you can't defend.*

### 6.2 What makes AI launches travel on X (Devin, Sora, Sarvam pattern)

From press-documented launches, the repeatable mechanics: **(1) a category claim** ("first AI software engineer," "India's first ___"); **(2) a self-explanatory demo video inside the launch post**; **(3) one hard number** (SWE-bench %, 44ms response, <400MB RAM); **(4) scarcity** (waitlist/invite); **(5) founder account amplifying company account**; **(6) tolerance for a skepticism cycle** (Devin's second wave of engagement came from scrutiny).

Compact Intelligence's ready-made version: *"A 1.5B model that runs in <400MB of RAM, speaks 7 Indian languages, and runs on the phone a billion people already own — launching at IIT Bombay."* That sentence has the claim, the number, and the story.

### 6.3 India-specific dynamics

- Indian tech X amplifies: IIT/IIM pedigree, India-first AI narratives (Sarvam took 87% of Indic-AI funding in 2026; Krutrim announced by @bhash personally), young-founder underdog stories, and founders with an edge.
- **Founder-led > company-led, everywhere but especially in India.** Bhavish Aggarwal runs Krutrim comms from his personal account. **@varundaiya is the voice; @thinkcompact is the mirror and the archive.**
- E-Cell IIT Bombay's official X presence (@ecell_iitb) and E-Summit's investor/speaker network (100X.VC's Sanjay Mehta, Nexus's Sameer Brij Verma are listed) are the reply-and-tag graph for launch week.

### 6.4 The hard numbers on reach (Buffer, 18.8M posts, Aug 2024–Aug 2025)

- **Free accounts: median <100 impressions/post; median engagement rate 0% since March 2025.** Posting from a new free account is near-total invisibility — Premium is effectively table stakes (you have it on the founder account; get it on @thinkcompact too).
- Format engagement (Premium accounts): **text ~0.9% > video ~0.7% > image 0.4–0.5% > links 0.25–0.3%.** Lead with text and native video; never lead with links (link goes in first reply).
- Timing: Buffer (8.7M posts) — Tue/Wed/Thu, 9–11am local; Sprout (~2B engagements) — Tue–Thu 12–6pm local; weekends weakest. For an India-based founder targeting both India and US tech X: **primary slot ~12:30–1:30pm IST (India midday), secondary ~7:30–9:30pm IST (US morning).**
- Replying to comments lifts post engagement ~8% (Buffer).

---

## 7. The 5-Week Plan (Nov 6 → Dec 13)

**Operating cadence (every day, both accounts' jobs split as below):**

- **@varundaiya (the voice):** 2 original posts/day (slots above), 10–15 substantive replies/day on target accounts (see 7.2), 1 thread/week, 1 native video/week. Premium long-posts for the technical essays.
- **@thinkcompact (the mirror):** 1 post/day — re-express (never copy-paste; duplicate cross-account text is a spam trigger) the founder content in company voice, plus artifacts: benchmark screenshots, demo clips, waitlist milestones. Get Premium on this account.
- Reply to *every* reply on your own posts within the first hours (reply weight 5.0; author participation feeds the conversation).
- Follow ~10–15 relevant accounts/day (gradual; follow churn is flagged): efficiency-ML researchers, Indian AI ecosystem, E-Cell/IIT network, investors, tech journalists. Follow back genuine engagers (mutual-follow boost is your biggest multiplier).

### 7.1 Phase plan

**Week 1 (Nov 6–12) — Foundation & the thesis drop.**
- Day 1–2: fix all credibility gaps (Section 9). Set up @thinkcompact properly (bio, banner, pinned post). Turn on notifications for target accounts.
- Day 3: **The thesis thread** from @varundaiya — "After the Wall" distilled to 8–12 posts: Moore's Law is ending → the GPU brute-force era has a ceiling → 1-bit LLMs change the physics → India should build the on-device layer. End with "We're building this. It's called Terminus." (No link in the main posts; waitlist link in final reply.)
- Rest of week: one technical explainer/day (what 1.58 bits/weight means; why multiplication-free inference matters; energy-per-token math). These are dwell-optimized, copy-link-bait posts for the ML community.
- KPI: cadence established, 50–150 followers across both accounts, first strangers replying.

**Week 2 (Nov 13–19) — Proof of substance (build in public begins).**
- Start the **Terminus build log**: real numbers — training tokens, eval scores, quantization decisions, what broke. Failure posts perform as well as wins and build credibility (Arvid Kahl pattern).
- First demo artifact: even 30 seconds of the model running on a cheap phone, posted as native video. Native video is the #2 format and completion feeds the model's video heads.
- Publish one "spiky" technical opinion from the founder account (e.g., "The industry is optimizing the wrong metric. Intelligence-per-watt beats parameters."). Defensible takes drive replies/quotes (5.0 weights).
- KPI: 150–350 cumulative followers; one post >10k impressions; 3–5 real mutuals in the niche.

**Week 3 (Nov 20–26) — The India narrative & the E-Summit announcement.**
- The Indic-first story: demos in Hindi/Marathi/Tamil; "why on-device matters when connectivity and privacy are the constraint" — agriculture/health/governance use cases from your own FAQ. This is your copy-link-to-WhatsApp content: it travels *because* Indians forward it.
- **Announce the E-Summit launch publicly** (Tue Nov 24 or Wed Nov 25): "On Dec 12 at IIT Bombay's E-Summit, we're putting Terminus on stage." Tag @ecell_iitb. This creates the countdown spine for weeks 4–5.
- Founder-story post: two founders from Aurangabad building a foundation model — the underdog arc Indian tech X amplifies.
- KPI: 300–600 cumulative; announcement post is the best performer so far; first inbound from press/investors/E-Cell network.

**Week 4 (Nov 27–Dec 3) — Anticipation engineering.**
- Countdown content: daily "T-minus" posts, each carrying one hard number or one demo clip (the Devin/Sora drip mechanic). Benchmark claims you can defend — nothing Cluely-flavored.
- Waitlist push: every post's first reply carries the waitlist link; report waitlist counts transparently (milestone posts are top performers).
- One hero demo video (60–90s) produced this week, held for launch.
- Quiet outreach: 10–15 DMs/emails to Indian tech journalists and E-Summit speakers with the launch angle — press coverage during launch week is the multiplier the algorithm can't give you directly.
- KPI: 500–900 cumulative; waitlist growing daily; ≥2 press/podcast conversations scheduled for launch week.

**Week 5 (Dec 4–11) — Pre-launch strike window (Tue–Thu are your prime days: Dec 8–10).**
- Daily behind-the-scenes: venue prep, demo rehearsals, "what you'll be able to try at our booth."
- Dec 8 (Tue): the **biggest pre-launch post** — the hero teaser clip + the full claim stack. This is timed for the algorithm's best window because Dec 12 is a Saturday (weak engagement day).
- Dec 10 (Thu): founder's "why we built this" long-form essay as a Premium long-post (dwell bait) — the emotional counterpart to the technical teaser.
- Dec 11 (Fri): logistics post — booth location, demo times, "come break our model."
- Schedule launch-day assets in advance; assign who posts what when.

**Launch weekend (Dec 12–13, Sat–Sun) — the event as a content engine.**
(See Section 8.) Accept that weekend reach is structurally lower; your job on-site is *capture* (footage, reactions, names), not just posting.

**Dec 15 (Tuesday) — the second strike.** The launch recap thread + full demo video drops on the first strong algorithmic day after the event, when you've edited the best footage. Plan for this to be your single biggest post of the campaign.

### 7.2 The reply strategy (your daily discovery engine)

OON replies don't ride For You (code-verified), but reply sections are where your target audience actually reads. Daily, from @varundaiya, leave **substantive** replies (add data, a contrarian angle, a real question — never "great post!") on:

- Indian AI ecosystem: Sarvam AI, Krutrim/@bhash, AI4Bharat, IndiaAI, prominent Indic-NLP researchers
- Efficiency-ML global: llama.cpp/Georgi Gerganov, quantization/1-bit researchers (BitNet authors), MLC/TinyML community, edge-AI hardware accounts
- Startup/investor: Kunal Shah, 100X.VC/Sanjay Mehta, Nexus/Sameer Brij Verma, Peak XV, Z47; E-Summit speakers as announced
- Event graph: @ecell_iitb, IIT Bombay official accounts, E-Summit sponsors
- Build-in-public/indie: the community that already rewards this format

Rules: no templates, no self-promo links in replies, max 1–2 replies per big account per day, zero automated anything.

### 7.3 Content pillar map (the topical-coherence discipline)

| Pillar | Share of posts | Job it does for the algorithm |
|---|---|---|
| 1-bit/efficiency technical substance | ~40% | Semantic-ID anchoring to the ML-efficiency cluster; copy-link shares from engineers |
| Terminus build log (numbers, demos, failures) | ~25% | Dwell + follow-author (serialized story); proof for press |
| Indic-first / India AI narrative | ~20% | OON retrieval into Indian tech X; WhatsApp-forward sharing |
| Founder journey + E-Summit countdown | ~15% | Follows, replies, human interest; press hook |

Never post outside these pillars during the 5 weeks. One off-topic viral-chasing post can scatter the model's author prior *and* reads as unprofessional.

---

## 8. The E-Summit Playbook (Dec 12–15)

**Before (already in the plan):** E-Cell coordination — get the launch listed in official E-Summit channels, confirm demo/booth format (Startup Expo / Living Lab are made for this), ask about Ten Minute Million participation (a pitch stage = a second content stream).

**During (Dec 12–13):**
- Live-post in the 12–6pm IST window only; quality over volume (author-diversity decay punishes bursts).
- Content types: (a) the stage moment video; (b) strangers trying Terminus on a ₹10–15k phone — "we let anyone come break it" (Living Lab framing is inherently viral-friendly); (c) photos with name-dropped attendees (tag speakers/investors — tags put you in their notifications, and their audience's conversation views); (d) one end-of-day recap per day.
- Tag @ecell_iitb and the event hashtag on every post; reply to every attendee who posts about you.
- Collect: every journalist, investor, and creator who stopped by → follow them same day (mutual network for the Dec 15 push).
- Founder account = live voice; company account = polished recaps with different wording (identical cross-posts are a flagged pattern).

**After:**
- Dec 14 (Sun): rest/draft. Dec 15 (Tue, prime window): the launch recap thread + hero demo video + waitlist/results numbers ("1,xxx people tried Terminus at E-Summit; the waitlist is now open"). Milestone transparency posts are the highest-performing content type in every build-in-public case study.
- Dec 16–18: press embargo lifts, founder essay "What we learned putting a 1.5B model in 1,000 hands," and the roadmap tease (the follow-author hook: the story continues).

---

## 9. Credibility Fixes (do in Week 1, days 1–2)

Ordered by visibility to a journalist/VC who clicks through from a traveling post:

1. **Website footer:** point social icons to the real handles (@thinkcompact, the LinkedIn company page, Instagram if it exists — if it doesn't, remove the icon).
2. **Replace `hello@gmail.com`** with a real contact (hello@compactintelligence.in or founders@).
3. **Remove/stub the leftover template pages** (`/work/*`) and rewrite the `/blog` index copy ("Alsham Studios" template text is currently live).
4. **@thinkcompact:** branded banner + avatar, bio with the Terminus one-liner and E-Summit date, pinned launch-tease post, Premium verification.
5. **@varundaiya:** bio already good; add the E-Summit launch date. Consider trimming the 520-following list gradually (not mass-unfollow — churn is flagged; a 520:27 ratio reads spammy to *humans* even though the algorithm doesn't score it directly).
6. **LinkedIn company page:** fill About, link the founders' profiles, cross-post the weekly milestone (E-Summit investors live on LinkedIn as much as X).
7. Prepare a **press kit page** (/press): Terminus one-pager, logos, founder photos, the claim stack with defensible numbers. When a post travels, journalists look for this within the hour.

---

## 10. Hard Don'ts (each verified against policy or code)

1. **No engagement pods / coordinated liking** — explicitly banned; `bdsm`/`agatha` exist to catch behavioral coordination.
2. **No duplicate or near-duplicate posts across the two accounts** — listed spam trigger; re-express instead.
3. **No follow/unfollow churn** — banned; cap at ~10–15 genuine follows/day.
4. **No hashtag stuffing** — muted-keyword filter + manipulation policy; 0–1 relevant hashtags, plus the official event tag during launch.
5. **No bought followers/engagement** — user-cred-v2 is a PageRank over the engagement graph; fake followers actively poison your credibility score.
6. **No automation** of posting/replies/DMs outside the API rules (Apr 2026 rules: non-API automation → permanent suspension; AI reply bots need written approval).
7. **No links in main posts** — first reply (Buffer: link posts crater; and you want the main post optimized for dwell/shares).
8. **No reply-spamming big accounts with self-promo** — bulk unsolicited mentions are a manipulation trigger, and humans will screenshot it. Substance only.
9. **No claims you can't defend.** Cluely is the documented cautionary tale; your entire positioning is engineering credibility.
10. **Don't chase off-topic virality.** Semantic IDs and retrieval history mean off-topic noise actively degrades how the model places you.

---

## 11. Realistic Expectations & KPIs

**The honest baseline (data, not vibes):** new free accounts median <100 impressions/post and 0% engagement; Premium lifts the floor to ~600 impressions median; platform median is 4 engagements/post with extreme variance. No verified founder case reached 10k followers in 5 weeks — Tony Dinh took ~2 years to 70k; Dhravya Shah ~2 years to funding-grade visibility.

**Realistic bands for Dec 13:**

| Scenario | Followers (combined) | What it requires |
|---|---|---|
| Typical execution | 150–400 | Cadence held, no breakout |
| Good execution | 400–1,000 | Cadence + reply engine + 1 post >50k impressions |
| Breakout | 1,000–3,000 | One genuine viral post (thesis thread or a demo) + event amplification |
| 10k+ | Not a plan | Requires a true viral event; treat as upside only |

**Weekly KPIs to track (both accounts):** impressions/post (floor should rise week over week), profile visits → follow conversion (target 3–8%), replies per post (conversation is the #1 weighted signal family), waitlist signups attributed to X, number of real mutuals (target ≥20 by launch), inbound DMs from press/investors.

**The reframe for the launch:** the follower count matters less than (a) the reply-network of 20–50 real accounts who know you, (b) an archive of substance a journalist can scroll, and (c) a proven launch-day distribution template. Those three assets convert E-Summit stage time into durable growth *after* the event — which is when the Tue Dec 15 recap and press cycle do the heavy lifting.

---

## 12. Source Index

**Code (local clone, commit 021afa4, sync 2026-11-04):** `home-mixer/params/param.rs` (weights, cold-start params, source budgets) · `home-mixer/scorers/author_cold_start.rs` · `home-mixer/filters/*` · `xai-value-model/scoring.rs`, `weights.rs` · `vm-ranker/params.rs`, `dpp.rs` · `phoenix/README.md` (model architecture, dims, training heads) · `recsys.proto` (action taxonomy, user features) · `docs/BIDIRECTIONAL_BOOST_CHANGE.md` · `under-the-hood/strato/.../underTheHoodReport.User.strato` · `README.md` (Notable Updates, Key Design Decisions)

**Official:** @XEng open-source announcement (Jan 20, 2026) · Musk release commitments (Jan 10, 2026; Sep 19, 2025) · Nikita Bier on the mutual-follow boost (Jul 2026) · X authenticity/platform-manipulation policy · X automation rules (Apr 2026) · X search policies

**Data studies:** Buffer — X Premium reach (18.8M posts, 71k accounts) · Buffer — best time to post (8.7M posts) · Buffer — X/Threads/Bluesky variance (1.7M posts) · Sprout Social best times 2026 (~2B engagements)

**Cases & press:** Tony Dinh on The Bootstrapped Founder · Arvid Kahl, Dagobert Renouf (Bootstrapped Founder) · marclou.com · Devin AI launch coverage (Bloomberg/Wired/VentureBeat via Wikipedia) · Sora launch (The Verge) · Cluely correction (Yahoo Finance) · Dhravya Shah/Supermemory (Moneycontrol, Business Today, Jagran Josh) · Sarvam funding dominance (Business Standard/Tracxn) · Bhavish Aggarwal/Krutrim (TechCrunch via Wikipedia) · MediaNama on the Aug 2026 algorithm release · HN threads 46688173, 49531195 · doomers.ai growth analysis

**Company/event:** compactintelligence.in (all pages, /blog/after-the-wall, /blog/ink-bits-and-tokens) · Tracxn/QorpIQ MCA records · x.com/thinkcompact, x.com/varundaiya · linkedin.com/company/compactintelligence · ecell.in/esummit (E-Summit'26, Dec 12–13, formats, speakers/investors)

*Caveats: production experiments and withheld components (Grox prompts, some botmaker rules) can diverge from shipped defaults; weights multiply predicted probabilities, not counts; all third-party "growth" claims beyond the cited datasets are directional.*
