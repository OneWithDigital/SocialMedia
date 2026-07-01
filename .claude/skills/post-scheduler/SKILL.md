---
name: post-scheduler
description: Ships a finished post via Blotato, or saves it to a file for manual posting if Blotato isn't connected. Use when the user has finished copy and wants to publish or schedule it. Trigger phrases: "schedule this to LinkedIn", "post this now", "schedule for tomorrow morning", "publish this".
allowed-tools: Read, Write, mcp__Blotato__blotato_list_accounts, mcp__Blotato__blotato_create_post, mcp__Blotato__blotato_get_post_status, mcp__Blotato__blotato_list_schedules, mcp__Blotato__blotato_create_presigned_upload_url, mcp__Blotato__blotato_list_pinterest_boards
---

# Post Scheduler

Ships a finished post. Prefers Blotato when it's connected; falls back to a copy-paste file when it isn't. This is the only skill in the pack that needs Blotato — every other skill works without it.

## Step 1: Confirm you have a finished post

Never schedule a draft that hasn't been through `post-grader` (directly or via `post-writer`/`repurpose`) unless the user explicitly says to post it as-is.

## Step 2: Determine the platform and target account

Ask the platform if not already clear from context (Instagram, LinkedIn, X, Facebook, TikTok, YouTube, Threads, Bluesky, Pinterest).

## Step 3: Try Blotato

If the Blotato MCP tools are available:

1. Call `blotato_list_accounts` (optionally filtered by platform) to get the correct `accountId`, and any required sub-account info (Facebook Page ID, LinkedIn Company Page, YouTube playlist, Pinterest board via `blotato_list_pinterest_boards`, etc.).
2. If the post includes media, upload it first via `blotato_create_presigned_upload_url` (or reuse a URL already generated elsewhere in the conversation, e.g. from a visual template).
3. Call `blotato_create_post` with the account, content, media, and platform-specific required fields (e.g. TikTok privacy settings, YouTube title/privacy status).
4. If the user asked for a specific time ("tomorrow morning"), pass that as the scheduled time; otherwise post immediately or ask which they want.
5. Confirm back to the user with the result, and use `blotato_get_post_status` if they ask to check on it later.

## Step 4: Fallback if Blotato isn't connected or the call fails

Don't block the user. Instead:

1. Write the finished post to a file, e.g. `ready-to-post/[platform]-[YYYY-MM-DD].md`, including the platform, any scheduled time the user wanted, and the full copy ready to paste.
2. Tell the user the file is ready to copy-paste, and that connecting the Blotato MCP server would let this skill post/schedule it directly next time.

## Notes

- Never guess an `accountId` — always look it up via `blotato_list_accounts` first, since it can change and platforms have different required fields.
- If `blotato_list_schedules` shows a conflicting or duplicate scheduled post for the same slot, flag it to the user before creating another one.
