---
name: post-grader
description: Scores a draft post and lists the top 3 fixes. Use when the user asks whether a post is good, or is called automatically by post-writer and repurpose to score drafts. Trigger phrases: "is this post any good", "grade this", "score this draft", "what's wrong with this caption".
allowed-tools: Read
---

# Post Grader

Scores a draft against a rubric weighted toward virality, not just clean writing, then hands back the top 3 fixes. Called automatically by `post-writer` (after drafting) and `repurpose` (after generating each piece). Can also be called directly on a pasted draft.

## Rubric

Score out of 10. **Hook strength is 50% of the score** — the first 3 words decide whether the post gets read, so a weak hook caps the whole score regardless of how good the rest is.

The remaining 50% splits evenly across:
- **Curiosity** — does it create an open loop the reader wants closed?
- **Emotional charge** — does it provoke a reaction (not just inform)?
- **Share-worthiness** — would someone send this to a friend or repost it?
- **Voice match** — does it sound like the brand-brief's voice/vibe, not generic AI copy?
- **Polarity** — does it take a clear side, or hedge into safety?
- **Platform fit** — does the CTA match what that platform's algorithm rewards (see below)?

### Platform-algorithm fit
- LinkedIn rewards comments → CTA should provoke a reply, not just "thoughts?"
- Instagram rewards saves → CTA should give a reason to save (reference material, checklist)
- Facebook rewards shares → CTA should be worth sending to someone specific
- TikTok/YouTube Shorts reward completion → hook must promise a payoff worth watching to the end
- X rewards replies and reposts → hook should be quotable/screenshot-able on its own

## Universal voice rules to check

Flag violations of any of these — they're supposed to be baked into every post:
- Contractions used ("don't" not "do not")
- Active voice, short sentences
- Reader addressed as "you"
- Numbers as digits ("3 tips" not "three tips")
- No em dashes
- One concrete idea per post (not three ideas crammed in)
- Specific details over generic statements

## Output format

```
Score: X/10

Hook: X/10 — [one line on why]
[Other dimension]: X/10 — [one line, only for the weakest 1-2 dimensions, skip the rest]

Top 3 fixes:
1. [specific, actionable fix — not "make it better"]
2. [specific, actionable fix]
3. [specific, actionable fix]
```

## Loop behavior when called by another skill

When `post-writer` or `repurpose` calls this skill, they apply the top 3 fixes and re-submit for grading. Continue this loop until the score reaches 8/10 or higher, up to a maximum of 3 revision passes — if still under 8/10 after 3 passes, hand back the best version with the remaining gaps noted rather than looping indefinitely.
