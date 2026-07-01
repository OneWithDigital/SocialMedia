---
name: post-writer
description: Writes a graded, polished social post for a given idea and platform. Use when the user has an idea and a platform in mind. Trigger phrases: "write me a post about X for Instagram", "write a LinkedIn post about X", "draft a caption for X".
allowed-tools: Read, Write, Edit
---

# Post Writer

Turns an idea plus a platform into a finished, graded post. Called directly by the user, by `content-coach` after ideation, or by `repurpose` for each piece it generates.

## Inputs needed

- The idea/topic (required)
- The platform (required — ask if not given: Instagram, LinkedIn, X, Facebook, TikTok, YouTube, Threads, Bluesky, or Pinterest)
- `brand-brief.md` if it exists in the project root (read it for voice, customer, and CTA — don't ask the user to repeat it)

## Process

1. **Open with a hook.** Follow the `viral-hooks` skill's instructions to generate the opening line. Pick the framework that best matches the idea and the brand's contrarian belief if one exists.
2. **Write the body.** One concrete idea, specific details, short sentences. Reference the brief's actual customer and story where relevant instead of generic language.
3. **Close with a CTA** matching the platform's algorithm (see below), pulling from the brief's stated primary CTA when it fits, but shaped to drive the platform-native action.
4. **Format for the platform:**
   - **LinkedIn**: short paragraphs (1-2 sentences), line breaks between them, CTA that invites a comment/opinion.
   - **X**: punchy, single post or thread-starter under the character limit, hook doubles as the tweet if it's a single post.
   - **Instagram**: caption with hook as first line (before the "more" cutoff), CTA drives saves or shares, optional hashtags at the end.
   - **Facebook**: conversational, shareable, CTA gives a reason to tag/send to someone.
   - **TikTok / YouTube (Shorts)**: script format — hook line, then beats, payoff before the CTA, optimized to be watched to the end.
   - **Threads**: casual, single strong thought, light CTA.
   - **Pinterest**: description framed around the specific search/outcome someone is pinning for.

## Universal voice rules (always apply)

- Contractions always ("don't" not "do not")
- Active voice, short sentences
- Address the reader as "you"
- Numbers as digits ("3 tips" not "three tips")
- No em dashes
- One concrete idea per post
- Specific details over generic statements

## Auto-grading loop

After drafting, automatically follow the `post-grader` skill's instructions to score the draft. Apply the top 3 fixes it returns, then re-grade. Repeat until the score is 8/10 or higher, up to 3 passes total. Show the user the final post along with its score — don't show intermediate drafts unless asked.
