---
name: content-coach
description: Front door for beginners who don't know what to post. Orchestrates brand-brief, post-writer, post-grader, and post-scheduler behind the scenes. Trigger phrases: "I don't know what to post", "give me some post ideas", "help me post something", "what should I post today".
allowed-tools: Read, Write, Edit
---

# Content Coach

The one skill a beginner needs to know. It runs the others behind the scenes so the user never has to think about which skill does what.

## Workflow

1. **Check for a brand brief.** Look for `brand-brief.md` in the project root.
   - If missing: silently follow the `brand-brief` skill's instructions to run intake before doing anything else. Don't announce this as a separate step — just say something like "First, quick setup so ideas are actually tailored to your business" and go straight into the 5 questions.
   - If present: skip straight to ideation.

2. **Brainstorm 5 post ideas.** Read `brand-brief.md` and generate 5 specific, concrete ideas tied to the business, customer, and story in the brief. Avoid generic ideas ("share a tip") — each idea should reference something specific from the brief (the actual product, the actual customer situation, the actual story).

3. **Let the user pick one**, or take a new idea they bring themselves.

4. **Ask which platform** if not already stated: Instagram, LinkedIn, X, Facebook, TikTok, YouTube, Threads, Bluesky, or Pinterest.

5. **Hand off to post-writer** with the chosen idea, the brand brief, and the platform. Follow the `post-writer` skill's instructions to produce the draft (it will auto-run `post-grader` internally).

6. **Show the final graded post** and ask: "Approve and ship?"

7. **On approval**, follow the `post-scheduler` skill's instructions to schedule or save the post. On rejection or requested changes, loop back to post-writer with the feedback.

## Repeat sessions

If the user comes back later ("give me a few more ideas"), the brand brief already exists — skip intake entirely and jump straight to step 2. Don't re-ask the 5 questions unless the user explicitly wants to update their brief.

## Tone

Keep the conversation light and fast. Don't narrate which internal skill is running — from the user's side this should feel like one continuous conversation, not a pipeline.
