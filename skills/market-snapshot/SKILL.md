---
name: market-snapshot
description: Use when the user asks how big a market is, how fast it is growing, who the players are or what they charge, in words like "how big is the market for home batteries", "is home battery storage a big market", "who are the main competitors in restaurant POS", "who competes with this company" or "what do they charge". Builds a short sourced snapshot of market size, growth, main competitors and their published pricing, with the publisher of every estimate, using Hyperresearch Answers.
---

# Market snapshot

## Tools

This skill uses the Hyperresearch Answers connector:

- `data_and_web_answer`: the answer tool. One question, one short cited answer.
- `data_and_web_search`: the search tool. Ranked sources with the exact passages.
- `get_pending_answer`: the pending-answer tool. Collects an answer that came back pending, by its id.

Older connections may show these as `ask`, `search` and `get_answer`. Each call uses the user's Hyperresearch balance.

## Steps

1. Pin down the market: product, customer type and geography (for example "restaurant POS software, US, small restaurants"). Ask if it's unclear.
2. Ask the answer tool one focused question at a time:
   - "What is the size of the {market} in {year}, and who estimates it?"
   - "What is the forecast growth rate of the {market}?"
   - "Who are the largest vendors in the {market} by market share?"
   - For each of the top 3–5 vendors: "What is {vendor}'s published pricing for {product}?"
3. Use the search tool when you want several estimates side by side. Market-size figures vary a lot between research firms.
4. For a listed vendor, its own 10-K often states its revenue and how it describes the market. Ask for that when it helps.
5. Write the snapshot:
   - **Size and growth**: every estimate with its publisher, year and URL. If estimates disagree, show the range instead of picking one.
   - **Competitors**: a table of vendor, positioning and published price, each price with its URL and the date it was read.
   - **Gaps**: what no source answered.

## Rules

- Say who published each market-size number. A figure without a publisher doesn't go in the snapshot.
- Prices change, so note the date pricing was read.

## Example

User: "Give me a market snapshot of US restaurant POS software."

1. Answer tool: market size and who estimates it; forecast growth; largest vendors by share.
2. Search tool: "US restaurant POS software market size estimates" to put several estimates side by side.
3. Answer tool, once per top vendor: its published pricing.
4. The snapshot: size range with publishers, a competitor table with prices and dates, and the gaps.
