# X (Twitter) posts API: export a user's tweets with views and likes

Automatically export a user's tweets with views and likes on x.com. An unofficial X (Twitter) API for a user's posts: export an account's latest tweets with their views, likes, reposts, replies, quotes and bookmarks as data, in one call, without the X API. For the owner-only analytics of each post (impressions, engagements), run get_post_analytics on its id. Get a user's latest posts by handle (x.com/<handle>, the Posts tab), newest first: their own tweets and self-threads, without replies (see get_user_replies) or reposts (see get_user_reposts). Works signed in or signed out. Signed in, it reads the full Posts tab up to count. Signed out, X only shows visitors its few most recent posts, so it returns that short preview and fewer than count is expected; each post's source field says which one you got. Returns per tweet: id, url, text, created_at, lang, likes, retweets, replies, quotes, views, bookmarks, is_retweet, is_quote, source.

- Site: x.com
- Address: `reduck/x.com/get_user_posts`
- Updated: 2026-09-24 (v12)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/x.com/get_user_posts`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/x.com/get_user_posts
```

## Input

- `handle` (string, required): X handle without the @, e.g. BernieSanders
- `count` (integer, optional): Max tweets to collect. Capped by how far X's timeline paginates before throttling.

## FAQ

### What does "X (Twitter) posts API: export a user's tweets with views and likes" do?

An unofficial X (Twitter) API for a user's posts: export an account's latest tweets with their views, likes, reposts, replies, quotes and bookmarks as data, in one call, without the X API. For the owner-only analytics of each post (impressions, engagements), run get_post_analytics on its id. Get a user's latest posts by handle (x.com/<handle>, the Posts tab), newest first: their own tweets and self-threads, without replies (see get_user_replies) or reposts (see get_user_reposts). Works signed in or signed out. Signed in, it reads the full Posts tab up to count. Signed out, X only shows visitors its few most recent posts, so it returns that short preview and fewer than count is expected; each post's source field says which one you got. Returns per tweet: id, url, text, created_at, lang, likes, retweets, replies, quotes, views, bookmarks, is_retweet, is_quote, source.

### How do I automatically export a user's tweets with views and likes on x.com?

Ask an AI agent connected to Reduck to run reduck/x.com/get_user_posts, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/x.com/get_user_posts

### Is there a x.com API to export a user's tweets with views and likes?

You do not need one. "X (Twitter) posts API: export a user's tweets with views and likes" drives the real x.com pages in a browser, so it works whether or not x.com offers an API for this.

### What information do I need to provide?

Required: handle. Optional: count.

### Do I need to be logged in to x.com?

No. It only uses pages of x.com that are reachable without signing in.

### Does it change anything on x.com, or only read data?

It only reads. It looks things up on x.com and changes nothing there.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/x.com/get_user_posts, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/x.com/get_user_posts

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/x.com/get_user_posts
