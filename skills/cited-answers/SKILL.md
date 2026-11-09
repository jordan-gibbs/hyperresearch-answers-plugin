---
name: cited-answers
description: How to use the Hyperresearch Answers tools (ask, search, get_answer) well. Use when the user wants a sourced fact, a number with its source, an official identifier, or primary sources to read, or when they ask to "use Hyperresearch".
---

# Cited answers with Hyperresearch

The Hyperresearch Answers connector has three tools:

- **ask**: one factual question in, one short answer out. The answer is checked word for word against quotes from the pages it cites, and the quotes and URLs come back with it. Statuses include answered, not found, unconfirmed and false premise.
- **search**: ranked raw sources with verbatim passages and no written answer. Use it when you need several sources to compare, want to build a table, or want to read the evidence yourself.
- **get_answer**: collects an answer that ask returned as pending, using its `ans_...` id. It costs nothing extra.

## Picking a tool

| Situation | Tool |
|---|---|
| One fact, number, date or identifier | ask |
| Several sources to compare, or rows for a table | search |
| ask returned an id instead of an answer | get_answer with that id |
| ask came back not found and the user still wants leads | search with a broader phrasing |

## Writing good questions

- Ask one thing per call. Split a broad brief ("tell me about the restaurant POS market") into focused questions: market size, growth rate, top vendors, pricing.
- Name the source when you know it: "According to FDIC BankFind...", "In Apple's latest 10-K...". It helps the answer land on the official record.
- Include the period and place: "US", "2025", "fiscal year ending June 2026".
- For search, use filters when they fit: `include_domains` (for example `["sec.gov"]`), and `start_published_date` / `end_published_date` (YYYY-MM-DD) for recent material.

## Using the results

- Cite the URLs the tool returns next to each fact you use. Don't add sources the tool didn't return.
- If the status is not found or unconfirmed, tell the user no source supports an answer. Don't fill the gap from memory.
- If the status is false premise, say what the sources show instead.
- Every result states what the call cost and the credit left. Mention cost when the user is running many calls.
- Answers checks facts against sources. It doesn't do coding, math, creative writing or casual chat, so don't call it for those.
