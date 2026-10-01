# X (Twitter) mentions API: read the tweets that mention you

Automatically read the tweets that mention you on x.com. List recent tweets mentioning the logged-in account (the Notifications > Mentions tab). Returns per tweet a canonical record: id, url, author {id, handle, name}, text, created_at, lang, likes, retweets, replies, quotes, bookmarks, views, is_retweet, is_quote, and in_reply_to {id, author_handle} (null unless the mention is a reply). Scrolls until count is met or the list dries up.

- Site: x.com
- Address: `reduck/x.com/get_mentions`
- Updated: 2026-09-29 (v4)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/x.com/get_mentions`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/x.com/get_mentions
```

## Input

- `count` (integer, optional): Max mentions to return. Default 50.

## Output

- `count` (integer, required): Number of mentions returned. 0 is a first-class outcome (no mentions).
- `mentions` (array, required)

## FAQ

### What does "X (Twitter) mentions API: read the tweets that mention you" do?

List recent tweets mentioning the logged-in account (the Notifications > Mentions tab). Returns per tweet a canonical record: id, url, author {id, handle, name}, text, created_at, lang, likes, retweets, replies, quotes, bookmarks, views, is_retweet, is_quote, and in_reply_to {id, author_handle} (null unless the mention is a reply). Scrolls until count is met or the list dries up.

### How do I automatically read the tweets that mention you on x.com?

Ask an AI agent connected to Reduck to run reduck/x.com/get_mentions, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/x.com/get_mentions

### Is there a x.com API to read the tweets that mention you?

You do not need one. "X (Twitter) mentions API: read the tweets that mention you" drives the real x.com pages in a browser, so it works whether or not x.com offers an API for this.

### What information do I need to provide?

Optional: count.

### What does it return?

It returns count, mentions.

### Do I need to be logged in to x.com?

Yes. It acts as you on x.com: on your own Chrome it reuses your session, and on a Reduck-hosted browser it loads the x.com cookies saved by the Reduck extension.

### Does it change anything on x.com, or only read data?

It only reads. It looks things up on x.com and changes nothing there.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/x.com/get_mentions, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/x.com/get_mentions

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/x.com/get_mentions
