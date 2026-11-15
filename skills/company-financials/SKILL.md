---
name: company-financials
description: Use when the user asks how a public company is doing financially, in words like "how is Nvidia doing financially", "how is Nvidia actually doing money wise", "what did Apple report last quarter", "is this company profitable", "how much cash does Costco have" or "what's their data center revenue". Pulls reported revenue, profit, segment results, cash and debt from the company's own SEC filings (10-K, 10-Q, 8-K), with the filing cited, using Hyperresearch Answers.
---

# Company financials from filings

## Tools

This skill uses the Hyperresearch Answers connector:

- `answer_from_sec_filings_economic_data_patents_and_web`: the answer tool. One question, one short cited answer.
- `search_sec_filings_economic_data_patents_and_web`: the search tool. Ranked sources with the exact passages.
- `get_pending_answer`: the pending-answer tool. Collects an answer that came back pending, by its id.

Older connections may show these as `ask`, `search` and `get_answer`. Each call uses the user's Hyperresearch balance.

## Steps

1. Confirm the company and ticker. If the name is ambiguous, ask.
2. Turn a loose question into figures. "How is Nvidia doing financially" usually means: latest quarterly revenue and its growth, net income, the biggest segment, and cash. Pick three to five figures.
3. Find the latest filings with the answer tool: "What are the dates and URLs of {company}'s most recent 10-K and 10-Q on SEC EDGAR?"
4. Ask one question per figure, naming the filing and period:
   - "What total revenue did {company} report for the quarter ended {date} in its 10-Q?"
   - "What net income did {company} report for fiscal year {year} in its 10-K?"
   - "What revenue did {company}'s {segment} segment report for the quarter ended {date}?"
   - "How much cash and cash equivalents did {company} report at {date}?"
5. Collect any pending answers with the pending-answer tool.
6. Present a small table with figure, period, value and filing URL, then two or three plain sentences on what the figures show. Note the fiscal year end if it isn't December.

## Rules

- Use reported figures from the filings, not analyst estimates, unless the user asks for estimates. Label any non-GAAP figure as non-GAAP.
- Keep units as filed (thousands or millions) and say which.
- Leave the mode at its default. Fast mode reads only the open web and can't reach the filings.
- For a private company, say there are no SEC filings, and offer the search tool for other public sources instead.

## Example

User: "What did Nvidia report for data center revenue in its latest 10-Q?"

1. Answer tool: "What is the filing date and URL of Nvidia's most recent 10-Q on SEC EDGAR?"
2. Answer tool: "What Data Center segment revenue did Nvidia report in its 10-Q for the quarter ended {date from step 1}?"
3. Reply with the figure, the quarter, the change from a year earlier if the filing states it, and the 10-Q URL.
