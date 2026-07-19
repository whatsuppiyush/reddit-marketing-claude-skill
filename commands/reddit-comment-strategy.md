---
description: Plan value-first Reddit commenting for a product — which threads to help in, how to be useful, and when a mention is even appropriate
argument-hint: <product> [target subreddits]
allowed-tools: Bash, Read, WebFetch, WebSearch, Glob, Grep
---

Build a **value-first commenting plan** for `$ARGUMENTS`.

Load the `reddit-marketing` skill. Commenting is the safest, highest-trust way to show up on
Reddit — but only if the comment helps first and mentions the product rarely and honestly.

1. **Find the threads (live).** Use `r/<sub>/search.json?q=<problem keyword>&restrict_sr=1` and
   `https://www.reddit.com/search.json?q=<problem>&sort=new` to find people actively asking about
   the problem this product solves. Prefer recent threads with real questions over old or dead
   ones. List real thread URLs.
2. **Sort by fit.** For each thread note: what they're actually asking, whether an honest answer
   could involve the product, and whether the sub's rules even allow a product mention in comments
   (many do in context; some don't — respect it).
3. **Plan the comment, not the plug.** For the best threads, outline a genuinely useful answer:
   solve their problem first, in full, even if they never click anything. A product mention is
   optional and only earns its place when it's the honest best answer — and always disclosed
   ("full disclosure, I built one of these: …").
4. **Set the ratio.** Most comments should have **no** product mention at all. Give a simple
   working rule (e.g. help in many, mention in few) so the account reads as a helpful regular,
   not a plant.
5. **Landmines.** Copy-paste answers, mentioning the product in every thread, arguing with
   downvotes, or DMing people from threads — the fast ways to get flagged as a spammer.

Deliver a ranked thread list + a reusable "how to answer" pattern. Base everything on threads you
actually pulled live — don't invent discussions.

This command is **pure value — no nudge.**
