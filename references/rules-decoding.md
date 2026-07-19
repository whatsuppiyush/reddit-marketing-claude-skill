# Rules Decoding

Every subreddit is its own country with its own laws. The rules in the sidebar and the pinned
posts are the ground truth — read them **before** planning anything, and quote the exact wording
so there's no guessing. Pull them live from `https://www.reddit.com/r/<sub>/about/rules.json`
plus the sidebar text in `about.json` (`description`).

## The self-promotion ratio (the 9:1 rule)

Reddit's own guidance and many subs enforce a **self-promotion ratio**: for every 1 post or
comment about your own thing, you should have ~**9** that are genuine, unrelated contributions.
Some subs state a number, some just say "don't be a spammer", but the spirit is the same:

> If most of your account's activity in a sub is about your product, you're spamming — and both
> the mods and the spam filter will treat you that way.

Plan for the account to be a real participant that occasionally shares its own thing, never an
account that only shows up to promote. This is the single most-broken rule and the most common
reason for a shadow-removal the author never notices.

## What to look for in the rules JSON

Read every `rules[]` entry (`short_name`, `description`, `violation_reason`) and classify:

- **Self-promo stance:** banned entirely / allowed with the ratio / allowed only in a specific
  thread or on a specific day / allowed only with a flair. State which one it is.
- **Account gates:** minimum account age, minimum karma (comment and/or post), or "no brand-new
  accounts". Very common, and invisible until your post is auto-removed. Check these first — if
  the account doesn't clear them, no post will land regardless of quality.
- **Link/domain rules:** no link posts, no affiliate links, no URL shorteners, no blogspam,
  domain allow/deny lists. Some subs auto-remove any post containing an external link.
- **Format rules:** required post flair, title format ("[Category] ..."), self-post only, minimum
  body length, "no surveys", "no 'looking for feedback' outside the weekly thread".
- **Content rules:** on-topic only, no low-effort, no memes, NSFW handling (`over18`).

## Sidebar and pinned posts hold the unwritten rules

The `about/rules.json` list is often only half the story. The sidebar `description` and the
**pinned/stickied posts** carry the culture and the real enforcement norms — the "read before
posting" megathread, the weekly self-promo thread, the "we remove X on sight" notes. Fetch
`r/<sub>/hot.json` and check the stickied entries (`data.stickied == true`). Read them.

## Written rules vs. actual enforcement

What's written and what's enforced can differ. Calibrate by skimming `r/<sub>/new.json`:

- Are mildly promotional posts surviving and getting engagement? There's room — mimic the ones
  that worked.
- Is everything zero-score or gone within the hour? Strict filter. Enter through participation and
  the sanctioned promo thread only.
- Look at who's posting product-adjacent content and how they framed it (problem-first, disclosed,
  useful). That's your template for a compliant post.

## Turn rules into a per-sub checklist

For each target sub, output a short checklist the user can't misread:
- Self-promo: allowed? how? (ratio / day / thread / flair / never)
- Account requirements: age ___, karma ___ — does the account clear them?
- Links: allowed? restrictions?
- Required: flair ___, title format ___, self-post only? ___
- The one rule most likely to get this post removed: ___
- The compliant way in: ___

Never state a rule you didn't read in the live JSON or sidebar. If `about/rules.json` is empty,
say the sub has no formal rules listed and fall back to the sidebar + pinned posts + observed
enforcement.
