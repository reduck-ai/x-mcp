# Get X (Twitter) user posts

Automatically get X (Twitter) user posts on x.com. Get an X (Twitter) user's latest posts by handle (the Posts tab of x.com/<handle>), with their views, likes, reposts, replies, quotes and bookmarks. Returns { posts, complete }; until 16 Oct 2026 the answer was the bare posts array, so a caller written before then reads result.posts now. Posts come in the order X shows them: the pinned post, if any, first, then newest first, with each self-thread kept in thread order. complete is true only when X marked the end of the tab and every post fits in count. Replies (see get_user_replies) and reposts (see get_user_reposts) are not included. Works signed in or signed out. Signed out, X only shows visitors a short preview of recent posts, so fewer than count is expected, complete is false, and in_reply_to and quoted_tweet are not available; each post's source field says which one you got.

- Site: x.com
- Address: `reduck/x.com/get_user_posts`
- Updated: 2026-10-29 (v28)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/x.com/get_user_posts`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/x.com/get_user_posts
```

## Input

- `count` (integer, optional): How many to return. Without it, the script returns the first page X shows (often 20 to 40). With it, the script loads more until it has count, reaches the end, or X stops loading.
- `handle` (string, optional): X handle, with or without the @, e.g. NASA.
- `handles` (array, optional): Not supported since 19 Oct 2026: the run fails with a message saying so. Send one handle per call and fan out with run_script's scripts.

## Output

- `posts` (any, optional)
- `complete` (boolean, optional): True only when X marked the end of the Posts tab and every post fits in count; false when count stopped the read, X stopped loading, or for the signed-out preview.

## FAQ

### What does "Get X (Twitter) user posts" do?

Get an X (Twitter) user's latest posts by handle (the Posts tab of x.com/<handle>), with their views, likes, reposts, replies, quotes and bookmarks. Returns { posts, complete }; until 16 Oct 2026 the answer was the bare posts array, so a caller written before then reads result.posts now. Posts come in the order X shows them: the pinned post, if any, first, then newest first, with each self-thread kept in thread order. complete is true only when X marked the end of the tab and every post fits in count. Replies (see get_user_replies) and reposts (see get_user_reposts) are not included. Works signed in or signed out. Signed out, X only shows visitors a short preview of recent posts, so fewer than count is expected, complete is false, and in_reply_to and quoted_tweet are not available; each post's source field says which one you got.

### How do I automatically get X (Twitter) user posts on x.com?

Ask an AI agent connected to Reduck to run reduck/x.com/get_user_posts, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/x.com/get_user_posts

### Is there a x.com API to get X (Twitter) user posts?

You do not need one. "Get X (Twitter) user posts" drives the real x.com pages in a browser, so it works whether or not x.com offers an API for this.

### What information do I need to provide?

Optional: count, handle, handles.

### What does it return?

It returns posts, complete.

### Do I need to be logged in to x.com?

No. It only uses pages of x.com that are reachable without signing in.

### Does it change anything on x.com, or only read data?

It only reads. It looks things up on x.com and changes nothing there.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/x.com/get_user_posts, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/x.com/get_user_posts

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/x.com/get_user_posts
