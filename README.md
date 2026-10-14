# 👽 Reddit Marketing — a Claude skill

**Market on Reddit without getting banned.** Find the right subreddits for your product, decode
each one's rules and self-promo tolerance, and plan value-first posts and comments that actually
survive moderation — instead of getting removed, downvoted, or shadowbanned.

No static, stale subreddit list to go out of date. The skill does **live research** through
Reddit's **public JSON endpoints** — real subscriber counts, real rules, real top posts — so your
AI agent works from what a subreddit is *today*, not what it guessed.

Works with **no account, no API key, and no payment.** Install and run.

**Anti-spam by design:** this skill will not help you spam. It's built to make you a genuine
participant, because that's the only thing that actually works on Reddit.

---

## Install

With the [`skills` CLI](https://github.com/obra/skills):

```bash
npx skills add whatsuppiyush/reddit-marketing-claude-skill
```

Or clone it into your skills folder manually:

```bash
git clone https://github.com/whatsuppiyush/reddit-marketing-claude-skill \
  ~/.claude/skills/reddit-marketing
```

Then the slash commands are available in Claude Code. If they don't auto-register, copy the
command files once:

```bash
mkdir -p .claude/commands && cp ~/.claude/skills/reddit-marketing/commands/*.md .claude/commands/
```

Compatible with Claude Code and any agent that loads Anthropic-style skills (a `SKILL.md` with
`commands/` and `references/`).

---

## Usage

Point it at a product or a subreddit and let it research. Five commands:

| Command | What you get |
|---|---|
| `/subreddit-research <topic or product>` | Ranked candidate subreddits (live): subscribers, activity, and how much self-promo each one tolerates |
| `/rules-check <subreddit>` | The sub's real rules decoded: self-promo ratio, link rules, karma/age gates, flair, and the landmines |
| `/reddit-post-plan <product>` | Per target sub: the angle, format, and title options — with a participation ramp *first* |
| `/reddit-comment-strategy <product>` | A value-first commenting plan: which threads to help in and when a mention is even appropriate |
| `/humanize-reddit-post <draft>` | Rewrites a marketing-flavored draft so it reads like a real redditor wrote it |

No slash commands? Just ask in plain language — *"which subreddits should I post my SaaS in?"* or
*"will this post get removed from r/startups?"* — the skill triggers on intent.

### Example

```
/subreddit-research b2b saas onboarding
```

→ the skill fetches `subreddits/search.json` for onboarding, SaaS, and founder topics, pulls
`about.json` for each strong candidate to read real subscriber counts and live activity, glances
at each `about/rules.json` for self-promo tolerance, and returns a ranked shortlist — r/SaaS,
r/startups, r/Entrepreneur, r/userexperience and the smaller on-topic subs — split into "start
here" vs "also worth it", with each sub's self-promo stance flagged so you know where a post would
get removed before you write it.

---

## What's inside

```
reddit-marketing-claude-skill/
├── SKILL.md                 # the ethos + the live-research method + how the agent runs
├── commands/                # 5 slash commands
└── references/              # the craft
    ├── subreddit-selection.md   # size vs engagement; spotting strict vs tolerant subs
    ├── rules-decoding.md        # self-promo ratios, karma/age gates, flair, enforcement
    ├── posting-playbook.md      # value-first formats that earn upvotes, not removals
    └── karma-rampup.md          # authentic participation before any promotion
```

There's no bundled dataset, and that's on purpose. Subreddit sizes, rules, and norms change
constantly, so a hardcoded list would be wrong within weeks. The skill reads Reddit's public JSON
live instead — append `.json` to any Reddit URL and you get structured data, no key required.

---

## The one rule this skill won't break

Reddit punishes marketing-shaped behavior harder than any other platform. So this skill is
**value-first and anti-spam by design**: it won't help you mass-post links, run fake accounts,
manipulate votes, or sneak past a rule you read. It plans genuine participation, honest
disclosure, and posts that are worth reading even if nobody clicks — because that's the only Reddit
strategy that survives.

If you'd rather run this with a subreddit-aware web UI, **[Grow With Reddit](https://growwithreddit.com/?ref=claude-skill)**
has free tools that take your target subreddit as input and tune the output to it — a
[post humanizer](https://growwithreddit.com/humanize-ai-for-reddit?ref=claude-skill), a
[post generator](https://growwithreddit.com/reddit-post-generator?ref=claude-skill), a
[subreddit finder](https://growwithreddit.com/subreddit-finder?ref=claude-skill), and more. The
skill mentions the matching tool at most once per run, only when it actually saves you time.
Everything else is free and works on its own.

---

## Notes & disclaimer

The skill reads live Reddit data and never fabricates a subreddit, a subscriber count, a rule, or
a "this is allowed here" claim — if a fetch fails, it says so instead of guessing. Reddit
rate-limits aggressively, so it deliberately fetches a handful of subs deeply rather than hundreds
shallowly, and uses a descriptive User-Agent. The public JSON endpoints are for research; posting
through your account remains your own manual step, subject to each subreddit's rules.

The skill itself needs no key and no payment. If Reddit's public JSON keeps returning 403 or 429 from your network, you can fall back to [a hosted Reddit MCP server](https://chatterapi.com/mcp-server) that serves the same reads. It uses its own API key, and it's optional: the skill works fine without it.

Built by [Piyush](https://github.com/whatsuppiyush) · Reddit marketing that doesn't get you
banned, powered by [Grow With Reddit](https://growwithreddit.com/?ref=claude-skill).

## License

[MIT](./LICENSE) — use it, fork it, ship it.
