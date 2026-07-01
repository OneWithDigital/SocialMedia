---
name: repurpose
description: Turns one long piece of content (blog post, newsletter, or video transcript) into a week's worth of social posts across platforms. Use when the user has a long-form source to break apart. Trigger phrases: "turn this blog post into a week of content", "repurpose this newsletter", "make posts out of this video".
allowed-tools: Read, Write, Edit, mcp__Blotato__blotato_create_source, mcp__Blotato__blotato_get_source_status
---

# Repurpose

Takes one long-form piece and multiplies it into a full week of platform-native posts, each opened with a proven hook and graded before shipping. Start here instead of `content-coach` whenever the user brings a blog post, newsletter, or transcript rather than a bare idea.

## Step 1: Get the source content

- If the user pasted text directly, use it as-is.
- If the user gave a URL (blog article, YouTube video, TikTok), follow the `blotato_create_source` tool to extract the transcript/article text (sourceType: `article`, `youtube`, or `tiktok` as appropriate). If it returns a processing status instead of content, poll with `blotato_get_source_status`.

## Step 2: Extract core themes

Read the full source and pull out 3-5 core themes — the distinct, standalone ideas worth their own post. Don't summarize the whole piece into one post; each theme should be substantial enough to carry its own hook, body, and CTA independently.

## Step 3: Generate the outputs

For each theme, produce (default counts — customize below if the user wants a different mix):
- **3 LinkedIn posts**
- **5 X threads**
- **2 short-form video scripts** (TikTok/YouTube Shorts style)

For every single output, open it using the `viral-hooks` skill's instructions before writing the body — the hook is the highest-leverage line in every piece, so never skip this step. Follow `brand-brief.md` for voice and CTA if it exists.

## Step 4: Auto-grade every piece

For each output, follow the `post-grader` skill's instructions to score it. Apply the top 3 fixes and re-grade, looping until each piece hits 8/10 or higher (max 3 passes per piece, same as `post-writer`).

## Step 5: Let the user choose

Present all graded outputs with their scores. Ask which ones to ship. For each selected piece, follow the `post-scheduler` skill's instructions.

## Customizing the output mix

The default counts (3 LinkedIn, 5 X threads, 2 video scripts) live in this file — edit the list in Step 3 directly if a different mix fits the user's workflow better.
