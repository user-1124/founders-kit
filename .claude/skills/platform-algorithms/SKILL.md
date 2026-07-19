---
name: platform-algorithms
description: >-
  Authoritative, per-platform playbooks for how social algorithms actually rank and distribute
  content — Instagram, X/Twitter, YouTube, Threads, Facebook, and Reddit — each broken down by surface
  (Feed, Reels, Stories, Explore, For You, Search, Shorts, Suggested, Groups, etc.), ranking signal
  priority, what wins, and what gets downranked. USE THIS SKILL whenever the task involves creating,
  planning, scheduling, or critiquing social content or a posting strategy for ANY of these
  platforms — writing captions/hooks/threads/scripts, choosing a format (Reel vs Story vs Short vs
  long-form vs text post), deciding hashtags/timing/cadence, growing reach or followers, or asking
  "how does the platform algorithm work / why isn't this reaching people." Also use it as the
  knowledge base behind /social-board and any content-generation workflow. Reach for it even when the
  user doesn't name "the algorithm" — if they're making a post to be distributed, the ranking rules
  apply.
---

# Platform Algorithms

Codified, source-grounded knowledge of how each major social platform ranks and distributes content,
so that content is written *to the ranker*, not to vanity metrics. This is the knowledge base that
`/social-board` and any content-generation task should consult **before** drafting.

## How to use this skill

1. Identify the **platform(s)** and the **surface** the content is for (a Reel is not a Story; a
   Short is not a long-form video). Goal → surface first, format second.
2. Open the matching reference file below and pull its ranking signals, hook rules, and
   do/avoid list into the draft.
3. Write to the **heaviest positive signal** for that surface, and judge the result by that signal —
   not by likes.

## Platform reference files

Read only the file(s) relevant to the task.

| Platform | Reference | Reach engine (strangers) | Retention engine (existing audience) |
|---|---|---|---|
| Instagram | `references/instagram.md` | Reels, Explore | Stories, Feed |
| X / Twitter | `references/x.md` | For You, Search | Following, replies to your audience |
| YouTube | `references/youtube.md` | Suggested, Search, Shorts, Home | Subscriptions, notifications |
| Threads | `references/threads.md` | For You | Following |
| Facebook | `references/facebook.md` | Reels, Groups, unconnected recs | Feed (friends/followers) |
| Reddit | `references/reddit.md` | Hot/Rising → r/all, Popular, Google | Subreddit New feed |

## Two ways in: by platform or by feature

Ranking lives at the **platform** level (a Reel on Instagram and a Reel on Facebook are scored by
different engines), so the reference files are organized per platform — but each file is broken down
**by surface/feature** inside. If you're thinking feature-first ("I'm making a Reel / a Story / a
short-form video / a text post today"), jump straight to the right section:

| Feature you're making | Where it's ranked as a reach vs. retention surface | Read |
|---|---|---|
| **Short-form vertical video** (Reels / Shorts) | Reach engine on every platform — strangers, watch-time/completion | `instagram.md` (Reels), `youtube.md` (Shorts), `facebook.md` (Reels) |
| **Stories** | Retention — existing followers, daily presence | `instagram.md` (Stories), `facebook.md` (Stories) |
| **Feed image / carousel post** | Retention-leaning; carousels punch above weight | `instagram.md` (Feed), `threads.md` (format), `facebook.md` (format) |
| **Text / short posts** | Reach via conversation | `x.md`, `threads.md` |
| **Long-form video** | Depth + evergreen search | `youtube.md` (long-form) |
| **Threaded / community discussion** | Community reach | `x.md` (threads), `facebook.md` (Groups), `reddit.md` |

Same principle everywhere: **the format is not the unit of ranking — the surface is.** Pick the
platform's surface, then write to *its* heaviest signal.

## Cross-platform first principles

These hold on every platform. The per-platform files give the specifics.

1. **There is no single "the algorithm." There are several — one per surface.** Each surface has a
   job: some serve people who *already follow you* (recency + relationship), others serve *strangers*
   (entertainment + discovery). Post retention content to your audience and discovery content to
   strangers — most accounts do the reverse.

2. **Match the content to the surface's job.** Reach surfaces (Reels, For You, Suggested, Explore)
   reward broad entertainment/utility; relationship surfaces (Stories, Following, Subscriptions)
   reward consistency and conversation. The same idea should be *packaged differently* per surface.

3. **The heaviest positive signal is usually a "vouch," not a "like."** A share to a DM (Instagram
   *send*), a repost (X/Threads), a share (Facebook) says "I put my name on this to someone I know."
   It's rarer and weighted heavier than a like or even a save. Ask of every draft: **"would a
   specific person send this to a specific friend?"**

4. **The first moment is an audition.** The opening second of a video, the thumbnail+title of a
   Short/long-form, the first line of a post — that's where the swipe/scroll decision happens.
   Cold-open into the payoff; trim every warm-up frame. Platforms give small accounts constant
   auditions; most fail in the first second, not for lack of "reach."

5. **Originality is favored; visible reposts are downranked.** Native, original content (no other-app
   watermarks, no recycled clips) is boosted, especially for smaller accounts.

6. **Early engagement compounds.** The first ~hour of replies/comments/watch-through tells the ranker
   whether to widen distribution. Be live in the comments early.

7. **Consistency builds the relationship signals** that feed your audience-facing surfaces. Active
   accounts generate more signal — not because you're punished for gaps, but because activity *is*
   signal.

8. **Judge by the deep signal, not the vanity one.** Watch time / completion, sends/shares, and
   follows-after-view predict future reach. Likes don't. Instrument to the metric the ranker rewards.

## Keeping this current

Platform mechanics change. Each reference file ends with a **Sources** section and a **Last verified**
date. When a file is stale or a platform ships a ranking change, re-research from the listed official
sources (platform engineering/creator blogs first, credible reporting second) and update the file
plus its date. Mark community heuristics as **[heuristic]** so they're never confused with confirmed
statements.
