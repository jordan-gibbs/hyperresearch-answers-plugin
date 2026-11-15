---
name: fact-check
description: Use when the user asks "is this true", "can you check these numbers", "fact-check this", "is this stat right" or "where did they get that figure", or wants the numbers, dates and claims in a draft, report, email, post or slide checked against sources. Checks each claim with Hyperresearch Answers against filings, official statistics, public registers and the live web, and returns a verdict table with the source for each claim.
---

# Fact-check a draft

Goal: a table showing which claims the sources support, which they contradict, and which nobody can confirm.

## Tools

This skill uses the Hyperresearch Answers connector:

- `answer_from_sec_filings_economic_data_patents_and_web`: the answer tool. One question, one short cited answer.
- `search_sec_filings_economic_data_patents_and_web`: the search tool. Ranked sources with the exact passages.
- `get_pending_answer`: the pending-answer tool. Collects an answer that came back pending, by its id.

Older connections may show these as `ask`, `search` and `get_answer`. Each call uses the user's Hyperresearch balance.

## Steps

1. **Extract the checkable claims.** Pull out every statement with a number, date, name, ranking, quote or "first/largest/only" wording. Skip opinions and predictions. If there are more than about 15, ask the user which section matters most.
2. **Turn each claim into one question.** "US e-commerce was 16% of retail sales in 2025" becomes "What share of US retail sales was e-commerce in 2025, according to the Census Bureau?" Keep the original wording next to it.
3. **Ask the answer tool once per claim.** Collect pending answers with the pending-answer tool.
4. **Compare.** Mark each claim:
   - **Supported**: the quoted source says the same thing (allow rounding and stated ranges).
   - **Contradicted**: the source gives a different figure or fact. Give the sourced version.
   - **Outdated**: right for an earlier period, but a newer figure exists.
   - **Unconfirmed**: the answer tool returned not found or unconfirmed.
5. **Report** as a table:

| # | Claim as written | Verdict | What the source says | Source |
|---|---|---|---|---|

Then list a suggested rewrite for every contradicted or outdated claim, each with its URL.

## Rules

- Never mark a claim supported from memory. Only the returned quotes count.
- If the draft already cites a source, check that the cited page says it. A real number with the wrong source is still worth flagging.

## Example

User: "Fact-check this: Apple's SEC Central Index Key is 0000320193, and Silicon Valley Bank's FDIC certificate number is 24735."

1. Two claims, two questions: "What is Apple Inc.'s Central Index Key at the SEC?" and "According to FDIC BankFind, what is the FDIC certificate number of Silicon Valley Bank (Santa Clara, California)?"
2. One answer tool call each.
3. A two-row table: both supported, with the SEC EDGAR and FDIC BankFind URLs.
