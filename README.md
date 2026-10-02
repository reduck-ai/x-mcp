# X MCP

X's API is pay-per-use and needs a developer app, even to read a post. This X (Twitter) MCP server (Model Context Protocol) lets Claude, ChatGPT or Cursor search tweets, read any account's posts, your mentions and DMs, and post or reply as you, with no API key and no credits.

![One integration, every website](https://docs.reduck.ai/overview/one-integration-every-website.png)

[Reduck MCP](https://docs.reduck.ai) gives your agent reusable browser scripts for the sites that have no API. They run in your own Chrome, through the Reduck extension, where you are already signed in: no credentials exposed, and no bot detection.

**Get started:** [docs.reduck.ai](https://docs.reduck.ai)

## Overview

X is where founders, researchers and brands say things first. An AI agent can read your email, your docs and your CRM, but when you ask it what someone posted on X, it searches the web and finds only what somebody else already wrote about it.

## Why it's hard

X gives an agent two ways in, and both cost. The X API is pay-per-use: every post read and every post created is billed against credits you buy upfront, and you need a developer app to get a key at all. X's own MCP server (xmcp) sits on that same API, so it needs the same app, OAuth setup and credits. The other Twitter MCP servers either ask for those keys too, or scrape through accounts that are not yours, so they cannot read your mentions or DMs, and cannot post as you.

## How Reduck does it

Reduck is an MCP server whose X scripts run in your own Chrome, where you are already signed in to X. Your agent sees what you see: any account's posts, search results with every X search operator, your mentions, your notifications and your DMs. It posts, replies and threads only when you ask. There is no developer app, no API key, no credit balance and no separate account.

## Tools

| Script | What it does | Takes |
|---|---|---|
| `search_tweets` | Tweets matching a query, Top or Latest tab, with all X search operators | a query, how many |
| `get_user_posts` | An account's latest posts, newest first, with views, likes and reposts | a handle, how many |
| `get_user_info` | An account's profile: bio, website, exact follower and following counts | a handle |
| `get_tweet` | One tweet and the conversation around it | its url |
| `get_mentions` | Your latest mentions | how many |
| `get_personal_feed` | Your For You timeline | how many |
| `get_messages` | The messages of one DM conversation | a handle |
| `post_tweet` | A tweet, with one image or video | the text, the media |
| `post_thread` | A thread of several posts | the posts |
| `reply_to_tweet` | A reply to one tweet | its url, the text |
| `schedule_tweet` | A tweet scheduled for later | the text, the time |

Every script answers structured data: ids, links, authors, dates, the text as X shows it and its counts. The summary and the reasoning stay in your agent. The full list of X scripts is in the [catalogue](https://reduck.ai/explore?host=x.com).

## Connect it

1. Install the Reduck extension in Chrome and stay signed in to X there.
2. Add Reduck to your client: [Claude Code](https://docs.reduck.ai/claude-code), [Claude Desktop](https://docs.reduck.ai/claude-desktop), [ChatGPT](https://docs.reduck.ai/chatgpt) or [any other MCP client](https://docs.reduck.ai/other-clients).
3. Ask: "What did @rockstargames and @xbox post this week? Summarize it."

## X API MCP or Reduck

| | X's MCP (xmcp) and API-based MCPs | Reduck |
|---|---|---|
| Setup | Developer app, OAuth credentials, a local bridge | Stay signed in to X in Chrome |
| Cost | X API credits, per post read and per post created | No X API credits |
| Acts as | Your developer app | You, in your browser |
| Your DMs and mentions | Through the API, if your app's scopes allow it | Yes, as you see them |
| Posting | Through the API, billed per post | Yes, as you |

## Who it's for

- Founders and marketers who post on X from an AI agent
- Anyone who wants an agent to follow specific accounts without opening the app
- Developers who want X in their agent without a developer account or a credit balance

## FAQ

### Is there an official X MCP server?

Yes. X hosts one at api.x.com/mcp (xmcp). It calls the X API, so it needs your own developer app, OAuth credentials, and X API credits: the X API is pay-per-use, per post read and per post created. Its documentation lists search, users, bookmarks, news, trends and Articles. Reduck is a different kind of MCP server: its X scripts use your own signed-in X tab, so there is no developer app and no credit balance.

### Do I need an X developer account or an API key?

No. There is no app to create, no key to paste and no credits to buy. You stay signed in to X in your own Chrome, and the Reduck extension runs each script there.

### Can it read the tweets of specific accounts, not just search results about them?

Yes. get_user_posts reads an account's Posts tab, newest first, with each post's text, date, views, likes, reposts, replies, quotes and bookmarks. Your agent reads what the account actually posted, not what a news site later wrote about it.

### Can it post and reply for me?

Yes, and only when asked. post_tweet posts a tweet, with one image or video if you want; reply_to_tweet, quote_tweet and post_thread do what their names say. The agent shows you the exact text first, and each script returns the new tweet's link. post_tweet also has a dry run that stops just before the Post click.

### How is it different from the Twitter MCP servers on GitHub and Apify?

Most Twitter MCP servers either call the X API with your keys, or run a scraper account you do not control. Apify's Twitter actors read public data; they do not post as you. Reduck acts as your own account, in your own browser, so it can read your mentions and DMs and post as you.

### Will X ban my account for this?

X's rules restrict automation, and no tool can promise that X will never act on an account. Reduck does not run a bot on its own: each script runs only when you or your agent asks, one at a time, in your own browser, from your own connection. Keep the volume and the pace of a person, and read X's automation rules before you post at scale.

### Does it work with ChatGPT, Claude and Cursor?

Yes. Reduck connects to ChatGPT, Claude, Claude Code, Codex, Cursor and any other MCP client. You ask in plain words, and the agent picks the X scripts it needs.

Source: https://reduck.ai/use-cases/x-mcp
