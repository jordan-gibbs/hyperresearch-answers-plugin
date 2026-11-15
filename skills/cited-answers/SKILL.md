---
name: cited-answers
description: Use when the user wants a fact, a number, a date or an official record with its source, asks "where does that number come from", wants primary sources to read, asks to cite or source something, or says "use Hyperresearch". Hyperresearch Answers reads SEC filings, FRED and Census economic data, patents and trademarks, clinical trials and FDA records, lobbying and campaign-finance filings, bank records and other public registers, among 120+ structured public data sources, plus the live web, and returns short answers checked against quoted sources with their links. This skill covers how to phrase questions, which tool fits, and how to cite the results.
---

# Cited answers with Hyperresearch

## Tools

This skill uses the Hyperresearch Answers connector:

- `answer_from_sec_filings_economic_data_patents_and_web`: the answer tool. One question in, one short answer out, checked word for word against quotes from the pages it cites, with the quotes and URLs.
- `search_sec_filings_economic_data_patents_and_web`: the search tool. Ranked sources with the exact passages and no written answer.
- `get_pending_answer`: the pending-answer tool. Collects an answer that came back pending, by its `ans_...` id.

Older connections may show these as `ask`, `search` and `get_answer`. Each call uses the user's Hyperresearch balance.

## What it reaches

- Company filings: SEC EDGAR 10-K, 10-Q, 8-K and more
- The economy: FRED series (unemployment, inflation, GDP, rates, jobs, housing) and Census Bureau trade data
- Patents and trademarks: USPTO
- Health: ClinicalTrials.gov, openFDA, drug labels, PubMed
- Money and influence: federal lobbying filings, FEC campaign finance, federal awards
- Banks and organizations: FDIC bank records, nonprofit filings, company registers
- Also: NOAA weather and climate records, scholarly papers and books, market data, the live web

## Picking a tool

| Situation | Tool |
|---|---|
| One fact, number, date or identifier | the answer tool |
| Several sources to compare, or rows for a table | the search tool |
| The answer tool returned an id instead of an answer | the pending-answer tool with that id |
| The answer tool came back not found and the user still wants leads | the search tool with a broader phrasing |

## Writing good questions

- Ask one thing per call. Split a broad brief ("tell me about the restaurant POS market") into focused questions: market size, growth rate, top vendors, pricing.
- Name the record when you know it: "According to FDIC BankFind...", "In Apple's latest 10-K...", "According to LDA filings...". It helps the answer land on the official record.
- Include the period and place: "US", "2025", "fiscal year ending June 2026", "last 12 months".
- Turn a loose question into a checkable one. "is the economy slowing down" becomes questions about the latest unemployment rate, GDP growth and job gains, each over a stated period.
- Leave the mode at its default. Fast mode reads only the open web, so it can't reach filings, statistics or registers.
- For search, use filters when they fit: `include_domains` (for example `["sec.gov"]`), and `start_published_date` / `end_published_date` (YYYY-MM-DD) for recent material.

## Using the results

- Cite the URLs the tool returns next to each fact you use. Don't add sources the tool didn't return.
- If the status is not found or unconfirmed, tell the user no source supports an answer. Don't fill the gap from memory.
- If the status is false premise, say what the sources show instead.
- Say which record a figure came from (a 10-K, an LDA filing, a FRED series) and its period.
- The tools look up sourced facts. They don't do coding, math, creative writing or casual chat.

## Example

User: "where does the 4.2% unemployment number come from?"

1. Ask the answer tool: "What is the latest US unemployment rate in FRED (series UNRATE), and for which month?"
2. Reply with the rate, the month, and the FRED series URL the tool returned. If the user's 4.2% matches an earlier month, say which.
