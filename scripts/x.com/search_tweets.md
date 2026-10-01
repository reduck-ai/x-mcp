# X (Twitter) search API: search tweets with every operator, no API key

Automatically search tweets with every operator, no API key on x.com. Search X (Twitter) for tweets with every X search operator, from the Top tab (a ranked sample, the default) or the Latest tab (chronological), picked by the tab arg. Returns per tweet a canonical record: id, url, author {id, handle, name}, text, created_at, lang, likes, retweets, replies, quotes, bookmarks, views, is_retweet, is_quote, plus followers (the author's follower count, a search-only enrichment), and the top-level query and count. Top is a ranked sample, not exhaustive.

- Site: x.com
- Address: `reduck/x.com/search_tweets`
- Updated: 2026-09-29 (v6)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/x.com/search_tweets`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/x.com/search_tweets
```

## Input

- `query` (string, required): Raw X search query. Supports all X search operators, e.g. '"AI automation" min_faves:500 since:2026-06-04'. Combining -filter:replies with min_faves and since can unexpectedly return zero results; using fewer operators together is more reliable. The query is taken literally, so if it targets a person or organization ambiguously — a bare first name, a nickname, or a handle you are not certain is exact, meant for from:/to:/@ targeting — resolve the exact handle first (for example via get_user_info, or by asking) rather than guessing: a wrong guess does not error, it silently searches the wrong thing and returns a plausible-looking but incorrect result set.
- `tab` (string, optional): Which search tab: 'top' (ranked, default) or 'latest' (chronological). Top is a sample, not an exhaustive ranking.
- `count` (integer, optional): Max tweets to return. The script scrolls until count is met or results dry up. Default 20, max 100.

## Output

- `count` (integer, required): Number of tweets returned. 0 is a first-class outcome (no results for the query).
- `query` (string, required)
- `tweets` (array, required)

## FAQ

### What does "X (Twitter) search API: search tweets with every operator, no API key" do?

Search X (Twitter) for tweets with every X search operator, from the Top tab (a ranked sample, the default) or the Latest tab (chronological), picked by the tab arg. Returns per tweet a canonical record: id, url, author {id, handle, name}, text, created_at, lang, likes, retweets, replies, quotes, bookmarks, views, is_retweet, is_quote, plus followers (the author's follower count, a search-only enrichment), and the top-level query and count. Top is a ranked sample, not exhaustive.

### How do I automatically search tweets with every operator, no API key on x.com?

Ask an AI agent connected to Reduck to run reduck/x.com/search_tweets, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/x.com/search_tweets

### Is there a x.com API to search tweets with every operator, no API key?

You do not need one. "X (Twitter) search API: search tweets with every operator, no API key" drives the real x.com pages in a browser, so it works whether or not x.com offers an API for this.

### What information do I need to provide?

Required: query. Optional: tab, count.

### What does it return?

It returns count, query, tweets.

### Do I need to be logged in to x.com?

Yes. It acts as you on x.com: on your own Chrome it reuses your session, and on a Reduck-hosted browser it loads the x.com cookies saved by the Reduck extension.

### Does it change anything on x.com, or only read data?

It only reads. It looks things up on x.com and changes nothing there.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/x.com/search_tweets, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/x.com/search_tweets

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/x.com/search_tweets
