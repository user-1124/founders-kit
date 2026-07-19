# X (Twitter) Algorithm Playbook

> How X ranks and distributes posts, for a brand/creator maximizing reach.
> X is the one major platform whose ranker is **open-source**: the 2023 `twitter/the-algorithm`
> repo published **exact heavy-ranker weights**, and the 2026 `xai-org/x-algorithm` repo ("Phoenix,"
> a Grok-based transformer) publishes the **pipeline and signal list but not the current weights**.
> So: treat the 2023 numbers below as *directionally current, not literal*, and treat widely-repeated
> observations as **[heuristic]**.
> **Last verified:** 2026-07.

## The one idea

X is **conversation-first, not consumption-first.** Every other platform optimizes watch-time or
completion first; X optimizes **replies you answer**. The heaviest positive signal by far is a reply
that *you reply back to* — a real two-way conversation. Write posts that start arguments you can
join, and then be there to join them.

## Surfaces — what each does

| Surface | Serves | Optimizes for |
|---|---|---|
| **For You** | **~50% strangers by design** (out-of-network is a first-class candidate source) | Predicted engagement, esp. replies/conversation. Where reach is won. |
| **Following** | Existing followers only | Reverse-chronological, no ML. Reliable, zero discovery. |
| **Search** | Strangers with intent | Relevance + engagement + recency. Rewards keyword-rich text. |
| **Communities** | Members **+ public For You since 2026** | In-community relevance; posting in a big community can exceed follower reach. **[heuristic]** |
| **Notifications** | Existing relationships | Where your reply strategy compounds. |

Because ~half of For You is strangers by design, viral breakout from near-zero followers is more
structurally possible on X than on follower-locked platforms.

## Ranking signals — the exact 2023 weights (directionally current)

Final score = Σ (weight × predicted probability of each action). From the published heavy-ranker:

| Signal | Weight | Meaning |
|---|---:|---|
| **Reply you then engage with** | **+75.0** | Someone replies **and you reply back.** The top signal, by a mile. |
| **Profile click → then likes/replies** | +12.0 | Drove to profile *and* engaged |
| **Reply** (any) | +13.5 | Any reply to your post |
| **"Good click" (opens + participates)** | +11.0 | Reader taps in and engages |
| **"Good click v2" (opens + dwell ≥2 min)** | +10.0 | Time spent |
| **Repost** | +1.0 | Baseline reshare |
| **Like** | +0.5 | The **weakest** positive signal |
| **Negative feedback** (show-less/mute/block) | **−74.0** | Massive suppressor |
| **Report** | **−369.0** | Near-fatal |

**Ordering:** conversation you sustain ≫ replies ≫ profile-clicks-with-engagement ≫ dwell/good-clicks
≫ reposts ≫ likes. A few back-and-forth replies outscore a hundred likes.

### What changed by 2026 (Phoenix) [mostly heuristic]
- **Replies still weighted heaviest** — reaffirmed officially.
- **Video and dwell time up-weighted** vs the near-zero 2023 video weight; Phoenix natively reads
  video and rewards watch-time.
- **Bookmarks are now a first-class positive** ("save for later" quality proxy).
- **Out-of-network external links penalized** — non-Premium accounts posting body links see
  near-zero median reach. **[heuristic — strong consensus]**
- **Author-diversity attenuation** (official 2026): limits how many of your posts hit one feed in a
  row — space your posting out.

## Format: what wins

- **Text hook posts** — X is the one platform where a strong text-only post routinely beats video.
  Punchy standalone insight/hot-take → drives replies at zero production cost.
- **Native video** (uploaded to X, not a YouTube link): vertical, ≤60s, hook in 1–2s, bold on-screen
  text readable without sound. Among the most amplified formats now.
- **Images/screenshots** lift a hook post's click-through; screenshots of text read as native media.
- **Single long-form posts** are increasingly favored over multi-post threads in 2026 (one
  dwell-generating unit the reader stays on). Thread only when content genuinely needs 4–8 steps.
- **Links: keep them OUT of the body.** Put the link **in a reply** ("link below") or bio. Body links
  cut initial reach hard, especially for non-Premium. **[heuristic — near-universal practice]**

## The first 30 minutes

The ranker is **velocity-sensitive**: the *rate* of early engagement, not the total, decides whether
For You fans out to strangers. ~20 replies in the first 30 min beats 50 spread over a day.
- **Be present 60–90 min after posting** and **reply to every reply** — you're manufacturing the +75
  "author-engages-reply" signal over and over and stacking dwell.
- **Don't post into dead hours you can't staff.** Best time = when *you* can converse, not a generic
  "peak hour."

## Downranked / penalized

- Body **external links** (biggest self-inflicted wound, esp. non-Premium).
- Anything that earns **mute/block/show-less (−74)** or **report (−369)** — bait that provokes these
  is self-defeating.
- **Engagement-bait** ("like if…", "RT to win", follow-for-follow) — pattern-matched, suppressed.
- **>2 hashtags** — X isn't hashtag-driven; more looks spammy.
- **Rapid-fire same-author posting** (author-diversity throttle).
- Old/duplicate content (filtered pre-scoring).

## Premium / verified

- Officially: subscription status gates candidate eligibility; Premium unlocks long-form, edit,
  analytics. **Premium replies rank higher in threads** (Premium+ gets top placement).
- Magnitude of the reach boost is disputed across studies, but the direction is consistent enough
  that for a brand doing organic growth in 2026, **Premium is effectively table stakes.** **[heuristic]**

## Judge success by

**Replies and reply-depth** — the #1 target: heaviest weight *and* best leading indicator of
amplification. Then **bookmarks** (quality proxy) and **out-of-network impressions** (confirms
stranger reach). **Likes are the weakest signal — don't optimize for them.**

## Do this / avoid this

**Do**
- Write to start conversations; reply to every reply in the first hour.
- Post native video/images and strong text hooks.
- Put links in a reply, never the body.
- Be live 30–90 min post-publish (velocity window).
- Prefer self-contained long-form over sprawling threads.
- Track replies, bookmarks, out-of-network impressions.

**Avoid**
- Links in the main post. Engagement-bait. >2 hashtags.
- Reposting others' content as your main output. Rapid-fire posting.
- Optimizing for likes.

## For BettorEdge specifically (edit to taste)

- X is the **sports-betting town square** — this is your reply-game platform. Post a sharp take on
  a line ("This total is 2 pts too high, here's why") *as text*, then **live in the replies** during
  the game window; every answered reply is the +75 signal.
- **Reply into big betting accounts** during games — a great reply is an out-of-network discovery
  unit and can out-reach your own posts. This is a primary growth channel, not etiquette.
- Put the **BettorEdge marketplace link in a reply**, never the post body.
- Screenshots of *your* no-vig price vs the book's number = native, sendable, argument-starting.

## Sources

- X algorithm (2023 repo): https://github.com/twitter/the-algorithm
- Exact 2023 heavy-ranker weights: https://github.com/twitter/the-algorithm-ml/blob/main/projects/home/recap/README.md
- X 2023 engineering blog: https://blog.twitter.com/engineering/en_us/topics/open-source/2023/twitter-recommendation-algorithm
- Phoenix / Grok ranker (2026 repo): https://github.com/xai-org/x-algorithm
- X Premium (official): https://help.x.com/en/using-x/x-premium
- Social Media Today — revealed ranking factors: https://www.socialmediatoday.com/news/x-formerly-twitter-open-source-algorithm-ranking-factors/759702/
- Sprout Social — X algorithm 2026: https://sproutsocial.com/insights/twitter-algorithm/
- Buffer — Does X Premium boost reach? (skeptical): https://buffer.com/resources/x-premium-review/
- igorbrigadir/awesome-twitter-algo: https://github.com/igorbrigadir/awesome-twitter-algo
