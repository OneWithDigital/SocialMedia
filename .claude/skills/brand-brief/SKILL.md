---
name: brand-brief
description: One-time setup that captures a business's product, customer, CTA, story, and voice into brand-brief.md. Use when there's no existing brand brief yet, or when the user's business has changed and they want to update it. Trigger phrases: "let's set up my brand", "update my brand brief", "I want to start posting but don't know what to do" (when no brief exists yet).
allowed-tools: Read, Write, Edit
---

# Brand Brief

One-time intake that turns a business into reusable context every other skill reads. Content-coach invokes this automatically the first time a user shows up with no brief. It can also be called directly to refresh an existing brief.

## Before asking anything

Check the current working directory for `brand-brief.md`. If it exists, show its contents and ask whether the user wants to update it or keep it as-is, rather than starting over.

## The 5 questions

Ask these one at a time, in plain language, waiting for an answer before moving to the next:

1. **What do you sell?** (product or service, in the user's own words)
2. **Who buys it?** (the specific customer — not "everyone," get concrete: age range, situation, pain point)
3. **What's the one CTA you want people to take?** (follow, DM, click a link, comment, buy — pick one primary action, not a list)
4. **Tell me a recent story** — a customer moment, a mistake you made, a behind-the-scenes detail, something that actually happened.
5. **What's the vibe?** (playful, no-nonsense, expert, scrappy, luxury — how should this sound out loud?)

### Bonus question (recommended, not required)

Ask if they have a strong opinion or contrarian belief about their industry — something most people in their space get wrong. This single answer is what fuels polarizing, high-engagement hooks later, so if they have one, capture it. If they don't have one ready, skip it — don't force it.

## Save the brief

Write the answers to `brand-brief.md` in the project root, structured like:

```markdown
# Brand Brief

## What we sell
[answer]

## Who buys it
[answer]

## Primary CTA
[answer]

## Recent story
[answer]

## Voice / vibe
[answer]

## Contrarian belief (optional)
[answer or "none captured yet"]
```

Confirm the file was saved and tell the user every other skill (content-coach, post-writer, post-grader, repurpose) will now read this automatically.
