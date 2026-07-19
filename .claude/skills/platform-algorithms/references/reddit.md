# Reddit Algorithm Playbook

> How Reddit ranks and distributes content — and how a brand participates **without getting banned**,
> because Reddit is uniquely hostile to promotion.
> Anchored on Reddit's content policy, the historically open-sourced ranking code, and the Google
> licensing deal; community/analyst observations are marked **[heuristic]**. Subreddit-specific rules
> are marked **[verify]** — copy them from each sub's live sidebar/wiki before acting.
> **Last verified:** 2026-07.

## The one idea

Reddit is **community-governed, not centrally-fed.** There's no follower boost and no past-performance
boost — **every post starts near zero, and the title + the first hour are the whole engine.** And a
**subreddit's rules and mods are a veto that overrides every algorithmic signal**: a high-velocity post
that breaks a sub rule is removed and reaches no one. You are not gaming one algorithm; you're
negotiating with thousands of independent communities that are **explicitly anti-marketing**.

## Surfaces

| Surface | Reaches | Optimizes for |
|---|---|---|
| **Home feed** (logged-in) | Your **subscribed** subs + recs | Personalized ML **Best** sort |
| **Popular / r/all** | **Strangers site-wide** | Velocity/score — where a post "escapes" its home sub |
| **Subreddit feed** | That sub's subscribers + visitors | The viewer's chosen sort (default **Hot**); governed 100% by the sub |
| **Search (Reddit + Google)** | **Strangers, evergreen for months/years** | Keyword relevance + score + recency |

**The escape ladder that reaches strangers:** `New → Rising → Hot → r/popular / r/all`. A post that
never leaves its home subreddit only ever touches that community.

**Sort orders:** **Hot** = score + time-decay (default sub sort). **Best** = personalized ML (default
home feed). **New** = reverse-chronological (where early voters/mods first see you). **Top** = net
score over a window. **Rising** = **upvote velocity relative to post age** (the on-ramp to Hot).
**Controversial** = high volume with a ~50/50 split.

## Ranking signals (rough priority)

1. **Early upvote velocity (first ~1–2 hours)** — the single biggest lever; Rising and the r/all escape are driven by *rate*, not total. **[heuristic]**
2. **Score (upvotes − downvotes), log-scaled** — the first ~10 net upvotes matter as much as the next 100. **[code]**
3. **Upvote ratio** — a low ratio (<~70–80%) suppresses spread and flags spam. **[heuristic]**
4. **Comment count & velocity** — engagement multiplier; comment-heavy posts keep resurfacing.
5. **Time decay / recency** — Hot is heavily time-anchored (below). **[code]**
6. **Subreddit rules / mod removal** — *a veto over all of the above.*

### The classic "Hot" formula (the mental model, not the live code)

```
score = log10(max(|U − D|, 1)) + sign(U − D) × (t − 1134028003) / 45000
```

`log10` = diminishing returns per vote; `/45000` means **every ~12.5 hours of age is worth roughly
10× the votes** — a 12-hour-old post needs ~10× the score of a 1-hour-old post to sit at the same
height. Because votes are logarithmic and the time term climbs linearly, **early votes are worth
vastly more than late ones**, and turnover is guaranteed. **[code]** — Reddit's live production code is
not published and now includes ML re-ranking + anti-manipulation dampening, so treat this as
directional.

## The subreddit is the gatekeeper

Before you can be ranked at all, you must clear each sub's gates individually (all enforced by
**AutoModerator**, often with **silent/shadow removals**):
- **Karma requirements** (comment and/or link karma minimums)
- **Account-age gates** (new accounts auto-filtered)
- **Link-domain bans** (specific domains auto-removed — common for promo/affiliate/betting sites)
- **Required post flair**; keyword filters; manual approval queues

There is **no site-wide "verified brand" pass.**

## The self-promotion problem

- The **"9:1 / 10% rule" is community folklore**, not current TOS — but mods still enforce it as a
  norm. Reddit's **official** language defines the problem as **spam**: *repeated, unwanted, or
  unsolicited* posting, or content posted **primarily to drive traffic / promote a product** rather
  than to participate. **Vote manipulation is a separate, hard, site-wide bannable rule.**
- **What gets you removed/shadowbanned:** an account that's mostly your own links; the same link
  sprayed across subs; multiple accounts pushing one product; undisclosed affiliation; affiliate/
  referral links; asking for upvotes.
- **How to actually participate:** be *"a person who is part of this community and happens to make X,"
  not "a brand using this community."* Value-first — answer questions, contribute, and surface your
  product only where it genuinely answers a need **and the sub allows it.**

## Format & craft

- **The title is ~everything** — no follower/past-performance boost, so the title alone earns the
  first clicks and votes. Specific > vague; **numbers help**; keep it skimmable; **match the sub's
  voice**; questions farm comments.
- **Text/self posts** are best for participation/discussion/AMAs and clear promo filters more easily.
  **Link posts** live or die on domain reputation (your-own-domain links trip promo filters).
  **Native Reddit video/images** favored over external hosts in visual subs. **[heuristic]**
- **Hashtags are useless on Reddit** and read as off-platform spam.

## First 1–2 hours = the whole game

A burst of upvotes + comments in the first **15–60 minutes** pushes you into **Rising**; power-users
browse Rising, snowballing into **Hot** and, if velocity holds, into **r/popular / r/all** (strangers).
The same 50 upvotes in hour 1 vs hour 8 produce completely different outcomes. **Post at peak time, be
present to answer every early comment** (comments beget comments beget reach), and **never buy or beg
votes** to fake the burst.

## Downranked / removed / penalized

- Downvotes / low upvote ratio; **mod & AutoModerator removal** (often silent, overrides everything).
- **Reposts** (duplicate filters + backlash); the same link across subs reads as spam.
- **Overt promotion / affiliate & referral links** (domain filters + mods).
- **Vote manipulation** — bots, multiple accounts, **coordinated voting** (asking staff/friends/Discord
  to go upvote), "upvote to enter." Hard, site-wide, **bannable.**
- New-account / low-karma auto-filters; account-level shadowbans.

## Judge success by

**Upvote ratio (aim >85–90%), comment count/velocity, first-hour vote velocity, and whether it reached
Rising/Hot.** Raw upvotes alone are vanity — ratio + comments + velocity tell you if the community
actually approved.

## Do this / avoid this

**Do**
- Lurk + read each sub's rules; clear karma/age gates first; build comment karma as a genuine participant for weeks.
- Craft specific, numbered, community-voiced titles; ask questions to farm comments.
- Post at peak local-sub times; be present the first hour and reply to everyone.
- Run **mod-approved AMAs** with proof of identity; disclose affiliation.
- Use **official Reddit Ads** for scaled/regulated promotion. Judge by ratio + comments + velocity.

**Avoid**
- Asking for upvotes / coordinated voting / alt accounts (site-wide ban).
- Affiliate/referral links in betting subs; spraying one link across subs; making your account mostly your own links.
- Marketing-speak titles and AMA answers; hashtags; direct product drops in strict subs without mod buy-in.

## For BettorEdge specifically — high risk, handle with care (edit to taste)

Reddit is where BettorEdge can get **banned fastest** if done wrong, and where a single upvoted thread
pays off in Google **for years** if done right.

- **r/sportsbook is one of the strictest subs on Reddit for this** — documented prohibitions: **no
  advertising/self-promo, no selling/touting picks, no referral or affiliate links, no promoting your
  own service/Discord.** Most discussion is funneled into daily pinned threads. **[verify — read the
  live sidebar]** r/sportsbetting is similar, slightly less rigid. Gambling is a regulated vertical
  under extra Reddit scrutiny and aggressive domain filtering.
- **Compliant playbook:**
  1. **Value-first participation** — become a trusted voice on odds, +EV, exchange-vs-sportsbook
     mechanics so you *earn* organic "what platform is that?" questions instead of pushing links.
  2. **AMA route** — a mod-approved "I built a peer-to-peer betting marketplace — AMA" is the cleanest
     organic path in strict subs, because product talk is *invited*.
  3. **Own your ground** — build and run **r/BettorEdge** where you set the rules.
  4. **Paid, not sneaky** — use **official Reddit Ads** (gambling/geo targeting) for scaled reach.
  5. Always **disclose affiliation**; never use alts or seed/ask for votes.
- **Evergreen SEO upside:** since the 2024 Google–Reddit licensing deal, well-received Reddit threads
  surface prominently in Google and AI answers — genuine, upvoted contributions are a durable search
  asset, which makes spam/manipulation even more counterproductive.

## Sources

- Reddit's Approach to Content Recommendations (Help): https://support.reddithelp.com/hc/en-us/articles/23511859482388-Reddit-s-Approach-to-Content-Recommendations
- Disrupting Communities / vote manipulation (Help): https://support.reddithelp.com/hc/en-us/articles/360043066412-Disrupting-Communities
- Reddit S-1 / 424B4 (Google deal disclosures, SEC): https://www.sec.gov/Archives/edgar/data/1713445/000162828024012380/reddit-final424b4.htm
- Reddit's algorithm-defined "Best" — Social Media Today: https://www.socialmediatoday.com/news/reddit-looks-to-improve-content-discovery-with-algorithm-defined-best-lis/603446/
- Deriving the Reddit formula — Evan Miller: https://www.evanmiller.org/deriving-the-reddit-formula.html
- How Reddit ranking algorithms work — Salihefendic: https://medium.com/hacking-and-gonzo/how-reddit-ranking-algorithms-work-ef111e33d0d9
- Google strikes $60M deal with Reddit — Fortune: https://fortune.com/2024/02/23/reddit-60m-deal-google-search-giant-train-ai-models-on-posts/
- Reddit self-promotion rules (2026): https://redship.io/blog/reddit-self-promotion-rules
- How to run a successful Reddit AMA — Influencer Marketing Hub: https://influencermarketinghub.com/reddit-ama-campaign/
