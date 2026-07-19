# Subreddit Selection

Picking the right subreddits is most of the battle. The wrong sub means a removed post or a ban;
the right one means a warm audience that upvotes and comments. Judge every candidate on **live**
data from `about.json` and `about/rules.json`, not reputation or memory.

## Start from the problem, not the product

List the specific problem the product solves and the people who have it. Those people gather
around **topics and identities**, not product categories. A time-tracking app doesn't just fit
r/productivity — it fits r/freelance, r/consulting, r/smallbusiness, r/webdev (people who bill
hours). Cast for the audience's world, then narrow.

Find candidates live with:
`https://www.reddit.com/subreddits/search.json?q=<topic>` — repeat per topic, then add the
obvious niche subs you already know fit.

## The three signals that matter

For each candidate, pull `about.json` and read:

1. **Size — `subscribers`.** Bigger reach, but bigger subs are usually stricter and noisier. A
   post can vanish under the volume. Don't chase size alone.
2. **Activity — `active_user_count`** (and eyeball `hot.json`: are posts hours old with real
   comments, or days old with none?). A 30k-subscriber sub posting all day beats a 2M-subscriber
   sub where threads die at 3 upvotes. **Engagement > raw subscriber count.**
3. **Self-promo tolerance** (from `about/rules.json` + the sidebar `description`). This decides
   whether marketing is even viable here. See `rules-decoding.md`.

## The sweet spot

The best target is usually a **mid-sized, high-activity, on-topic, promo-tolerant** sub:

- big enough that a good post reaches real numbers,
- small enough that it isn't a firehose where you drown,
- specific enough that your product is genuinely relevant,
- tolerant enough (or with a dedicated promo day/thread) that you won't get removed.

One great-fit sub you participate in for weeks beats ten big subs you post to once and abandon.

## Reading mod strictness before you commit

- **Rules count and tone.** A long, detailed rule list with karma/age gates = tightly moderated.
  Terse and permissive = looser. Neither is bad; it just sets how you enter.
- **`submission_type`** in `about.json` (`any` / `link` / `self`) tells you if link posts are even
  allowed — some subs are self-post only, which changes the format.
- **Skim `new.json`.** If recent posts that look even slightly promotional are gone or sitting at
  zero, the mods/filter are strict. If genuine "I built this" posts are surviving with engagement,
  there's room — copy how those authors did it.
- **Look for a promo container.** Many subs ban self-promo in the main feed but run a weekly
  "Self-promotion Saturday", "Feedback Friday", or "Share your project" thread. That thread is the
  sanctioned front door — use it.

## Score and shortlist

Rank candidates by **audience fit × activity × self-promo tolerance**. Present a table:
Subreddit · Subscribers · Active now · Self-promo stance · Why it fits. Split into "Start here"
(the few you'll actually invest in) and "Also worth it". Note any that are contribution-only (no
promo ever) — those are for building reputation, not posting links.

Never list a subscriber count or activity number you didn't pull live. If `subreddits/search`
returns thin results, broaden the topic terms and try adjacent audiences.
