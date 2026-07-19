---
name: social-board
description: >-
  Generate and plan platform-native social content for BettorEdge — captions, hooks, Reel/Short
  scripts, threads, posts, and a cross-platform content calendar — that is written to each platform's
  actual ranking algorithm. USE THIS SKILL whenever the task is to draft, brainstorm, repurpose, or
  schedule social posts for BettorEdge (or run "/social-board"), for Instagram, X/Twitter, YouTube,
  Threads, or Facebook. It always consults the `platform-algorithms` skill first so every piece is
  built for the right surface and the heaviest ranking signal, not for vanity likes. Reach for it for
  "write me a post / reel / thread about X," "give me this week's content," "turn this into content
  for all platforms," or "why isn't our content reaching people."
compatibility: Works best alongside the `platform-algorithms` skill (same repo), which holds the per-platform ranking playbooks.
---

# social-board — BettorEdge content generation

Turn an idea, result, or angle into **platform-native content that's built for the algorithm.** This
skill is the *workflow*; the `platform-algorithms` skill is the *knowledge base*. Never draft social
content from generic "best practices" — pull the live ranking rules for the exact surface first.

## Non-negotiable first step

**Before writing anything, load the relevant platform reference(s) from the `platform-algorithms`
skill** (`references/{instagram,x,youtube,threads,facebook}.md`). Each draft must be traceable to:
1. the **surface** it's for (a Reel ≠ a Story; a Short ≠ long-form; a text post ≠ a link post), and
2. the **heaviest positive signal** for that surface (see the table below).

## Surface → signal → what to write

| Platform · Surface | Job | Heaviest signal — write for this | Format default |
|---|---|---|---|
| IG Reels / Explore | Reach (strangers) | **Sends** + watch time | Cold-open vertical video, built to be DM'd |
| IG Stories / Feed | Retention (followers) | Replies, relationship | Daily polls/questions; native graphics |
| X For You | Reach (strangers) | **Replies you answer** | Text hook or native video; link in a reply |
| YouTube long-form | Depth + evergreen search | **Retention (first 30s)** then CTR | Packaged thumbnail/title; retention-edited |
| YouTube Shorts | Reach top-of-funnel | Watched-vs-swiped, loops | <2s hook, loop-friendly, Related-video link |
| Threads For You | Reach (strangers) | **Replies / conversation** | Text hook + carousel/image; reply ladder |
| FB Reels | Reach (strangers) | Completion + **private sends** | 15–30s cold-open native video |
| FB Groups | Community reach | Meaningful member comments | Genuine discussion prompt, native |
| Reddit subreddit | Community reach + evergreen Google | **Early upvote velocity** + comments + upvote ratio | Title-first value post; obey subreddit rules; ~9:1 non-promo |

## Workflow

1. **Clarify the input:** the core idea/result/angle, the platform(s), and the goal (reach vs.
   retention vs. conversion). If the user says "all platforms," treat one idea as the seed and
   **re-package per surface** — do not copy-paste the same text everywhere.
2. **Pull the playbook(s)** for each target surface from `platform-algorithms`.
3. **Draft to the signal.** Apply that surface's hook rule, format, and do/avoid list. Every draft
   answers the surface's core question — most often: *"would a specific person send this to a
   specific friend?"* (IG/FB sends), *"does this start a reply I can answer?"* (X/Threads), or
   *"does the first 30s pay off the thumbnail's promise?"* (YouTube).
4. **Add the operational notes** the algorithm rewards: the first-hour engagement plan (be live in
   replies/comments), where the link goes (in a reply/comment, never the body on X/FB), hashtag/topic-tag
   count, and posting-window logic (post when you can staff the first hour).
5. **State the scoreboard.** For each piece, name the metric to judge it by (sends, reply-depth,
   retention %, non-follower reach) — never likes.

## Output format

For a single piece:

```
Platform · Surface — Goal
Hook: <the first line / first 2 seconds / thumbnail+title>
Body/Script: <the content, formatted for the surface>
Send/Reply trigger: <why someone shares or replies>
Link placement: <reply / comment / bio — per platform rules>
First-hour plan: <engagement actions>
Judge by: <the heaviest signal for this surface>
Why it's built this way: <1-line tie back to the platform playbook>
```

For a multi-platform calendar: a table of Day · Platform · Surface · Angle · Hook · Format · Judge-by,
with the same idea re-packaged per surface (reach content to strangers, retention content to followers).

## BettorEdge brand context

> **Confirm/adjust this block — it drives voice and angles.** Based on public info, BettorEdge is a
> **social sports-betting marketplace**: peer-to-peer, **no-vig** (bet against other users, not a
> sportsbook, so sharper odds), a small commission on winnings, a **social feed** to follow friends
> and tail/fade their bets, leaderboards and competitions, legal in 45+ US states.

- **Voice:** sharp, confident, community-first, a little trash-talk; bettor-to-bettor, never
  "corporate brand." Real numbers and real results over hype.
- **Core sendable/reply-worthy angles:** no-vig price vs. the book (screenshot the edge), bad-beat
  humor ("this is so us"), tail/fade a friend, saveable slate/edge checklists, "40% of users profit
  vs. 2% on sportsbooks" style proof points.
- **Compliance guardrails (keep these in every draft):** responsible-gambling tone, no guaranteed-win
  or "get rich" claims, 21+/eligibility and state-legality caveats where relevant, no targeting
  minors. Frame edges as *better pricing/value*, not "beat the system." When a draft risks an implied
  guarantee, soften to expected-value language.

## Integrating with an existing /social-board

If BettorEdge already has a `/social-board` skill, treat this file as the drop-in **algorithm layer**:
keep your existing brand assets/voice and insert steps 2–5 above (pull `platform-algorithms`, draft to
the signal, add operational notes, state the scoreboard). The `platform-algorithms` references are the
reusable knowledge — this workflow is how content generation consumes them.
