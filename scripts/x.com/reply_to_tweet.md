# Reply to a tweet on X (Twitter) from an AI agent

Automatically reply to a tweet on X (Twitter) from an AI agent on x.com. Reply to a tweet given its URL. Returns the reply's id, url, the parent tweet id, and author handle.

- Site: x.com
- Address: `reduck/x.com/reply_to_tweet`
- Updated: 2026-09-29 (v8)
- Author: Reduck AI (reduck)

## Run it

Ask an AI agent connected to Reduck over MCP (`https://mcp.reduck.ai/mcp`) to run `reduck/x.com/reply_to_tweet`, or run it from a terminal:

```bash
npx @reduck-ai/cli@latest run --script reduck/x.com/reply_to_tweet
```

## Input

- `text` (string, required): The reply body text (≤280 chars). Any deliberate @handle in the text (not X's own auto-prepended participant mentions) is validated against a real, non-suspended X account before anything is posted — the run throws naming the bad handle if one doesn't resolve. Every call posts immediately and irreversibly in public, with no preview or confirmation step inside the script, so show the exact text to the user and get their explicit approval for this specific content before running — approval from an earlier or unrelated message does not carry over. X also prepends its own computed reply mentions (the tweet's participants) to the published text, so any @mentions at the very start of this field are stripped before typing to avoid duplicates; put a deliberate @mention of a different account mid-sentence rather than leading with it.
- `tweet_url` (string, required): Full URL of the tweet to reply to, e.g. https://x.com/handle/status/123

## Output

- `url` (string | null, required)
- `text` (string, required)
- `handle` (string | null, required)
- `tweet_id` (string | null, required)
- `in_reply_to` (string | null, required): id of the parent tweet
- `account_used` (string | null, required): handle of the logged-in account that performed the action, read from the account switcher UI (not assumed from input).
- `already_present` (boolean, required): true if a reply with this exact text was already visible on the tweet's page before attempting to publish (duplicate-avoidance check); when true, publishing is skipped and tweet_id/url are null.
- `verified_on_page` (boolean, required): true if the script navigated to the new reply's URL after publishing and confirmed the article is actually present.

## FAQ

### What does "Reply to a tweet on X (Twitter) from an AI agent" do?

Reply to a tweet given its URL. Returns the reply's id, url, the parent tweet id, and author handle.

### How do I automatically reply to a tweet on X (Twitter) from an AI agent on x.com?

Ask an AI agent connected to Reduck to run reduck/x.com/reply_to_tweet, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/x.com/reply_to_tweet

### Is there a x.com API to reply to a tweet on X (Twitter) from an AI agent?

You do not need one. "Reply to a tweet on X (Twitter) from an AI agent" drives the real x.com pages in a browser, so it works whether or not x.com offers an API for this.

### What information do I need to provide?

Required: tweet_url, text.

### What does it return?

It returns url, text, handle, tweet_id, in_reply_to, account_used, already_present, verified_on_page.

### Do I need to be logged in to x.com?

Yes. It acts as you on x.com: on your own Chrome it reuses your session, and on a Reduck-hosted browser it loads the x.com cookies saved by the Reduck extension.

### Does it change anything on x.com, or only read data?

It makes changes on x.com, like sending, posting, booking or buying something.

### How do I run it?

Ask an AI agent connected to Reduck to run reduck/x.com/reply_to_tweet, or run it from a terminal with the Reduck CLI: npx @reduck-ai/cli@latest run --script reduck/x.com/reply_to_tweet

### Who maintains it?

It is part of Reduck's official curated catalogue.

Source: https://reduck.ai/explore/scripts/reduck/x.com/reply_to_tweet
