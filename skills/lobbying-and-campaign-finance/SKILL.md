---
name: lobbying-and-campaign-finance
description: Use when the user asks who is paying to influence US politics or policy, in words like "how much does Meta spend on lobbying", "how much does Facebook spend on lobbying", "who lobbies for this company", "who's funding this candidate", "how much did this PAC raise" or "which firms lobbied on this bill". Reads federal lobbying disclosure (LDA) filings and FEC campaign-finance records, with amounts by period and links to the filings, using Hyperresearch Answers.
---

# Lobbying and campaign finance

## Tools

This skill uses the Hyperresearch Answers connector:

- `data_and_web_answer`: the answer tool. One question, one short cited answer.
- `data_and_web_search`: the search tool. Ranked sources with the exact passages.
- `get_pending_answer`: the pending-answer tool. Collects an answer that came back pending, by its id.

Older connections may show these as `ask`, `search` and `get_answer`. Each call uses the user's Hyperresearch balance.

## Steps

1. Use the legal name the filings use. "Facebook" files as Meta Platforms, Inc.; "Google" lobbying may be filed under Google LLC rather than Alphabet. If you aren't sure, ask the answer tool which name the filings use.
2. Ask one question per entity and period, naming the record:
   - "What was Meta Platforms, Inc.'s total federal lobbying spending in calendar year 2024, according to Lobbying Disclosure Act filings?"
   - "How much did {company} report in federal lobbying in each of the last three years, according to LDA filings?"
   - "Which lobbying firms reported work for {company} in {year}, according to LDA filings?"
   - "How much has {candidate or committee} raised this cycle, according to the FEC?"
   - "What is the FEC committee ID of {committee}?"
3. Collect any pending answers with the pending-answer tool.
4. Report each amount with its year or quarter, whether it is in-house lobbying or paid to outside firms when the filing says so, and the filing URL. For several years, use a small table.

## Rules

- Lobbying amounts are what the filer reported, per quarter, and totals add up those reports. Say so when you give a total.
- If an answer comes from a site that summarizes filings rather than from the filings, name the site, and offer one more question naming the LDA filings directly.
- Report records, not motives. Don't say what a payment was meant to buy.
- Leave the mode at its default. Fast mode reads only the open web and can't reach the filings.

## Example

User: "How much did Meta spend on federal lobbying in each of the last three years?"

1. Answer tool, once per year: "What was Meta Platforms, Inc.'s total federal lobbying spending in calendar year {year}, according to Lobbying Disclosure Act filings?"
2. Reply with a three-row table (year, amount, number of quarterly reports, lda.gov URL) and one sentence on the trend.
