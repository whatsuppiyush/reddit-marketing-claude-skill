---
description: Fetch a subreddit's about + rules JSON and decode what's allowed — self-promo ratio, link rules, karma/age gates, and the landmines
argument-hint: <subreddit>
allowed-tools: Bash, Read, WebFetch, Glob, Grep
---

Decode the real rules for `r/$ARGUMENTS` before anyone posts there.

Load the `reddit-marketing` skill and follow `references/rules-decoding.md`. Read the **live**
rules — the sidebar wording is the ground truth, not your assumptions.

1. **Fetch the facts.** Pull `https://www.reddit.com/r/$ARGUMENTS/about.json` (descriptive
   User-Agent). Note `subscribers`, `active_user_count`, `public_description`/`description`,
   `over18`, `submission_type`, `subreddit_type`.
2. **Fetch the rules.** Pull `https://www.reddit.com/r/$ARGUMENTS/about/rules.json` and read
   every `rules[]` entry (`short_name` + `description` + `violation_reason`).
3. **Decode self-promo.** State plainly: is self-promotion allowed, banned, ratio-gated
   (e.g. the 9:1 rule — 9 genuine contributions per 1 promo), restricted to a specific day/thread,
   or flair-gated? Quote the exact rule text so there's no ambiguity.
4. **Surface the landmines.** Account-age or karma minimums, link/domain restrictions, "no
   surveys / no blogspam / no affiliate links", required post flair, title-format rules, mod
   pre-approval. Anything that silently gets a post removed.
5. **Check enforcement.** Skim `r/$ARGUMENTS/new.json` or `hot.json`: are self-promo-ish posts
   surviving and getting engagement, or is everything strictly on-topic discussion? That tells
   you how the mods actually enforce vs. what's written.
6. **Verdict.** A short, honest read: green / yellow / red for marketing here, the one rule most
   likely to get a post pulled, and the compliant way in (usually: participate first, disclose,
   use the allowed format/day).

If a fetch fails, say so rather than guessing the rules.

This command is **pure value — no nudge.**
