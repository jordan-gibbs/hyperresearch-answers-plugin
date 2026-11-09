---
name: company-financials
description: Pull a public company's latest revenue, profit, cash and other reported figures from its official SEC filings, with the filing cited, using Hyperresearch Answers. Use when the user asks about a listed company's financials, results or reported numbers.
---

# Company financials from filings

## Steps

1. Confirm the company and ticker. If the name is ambiguous, ask.
2. Find the latest filings: "What are the dates and URLs of {company}'s most recent 10-K and 10-Q on SEC EDGAR?"
3. Ask one question per figure, naming the filing and period:
   - "What total revenue did {company} report for fiscal year {year} in its 10-K?"
   - "What net income did {company} report for the quarter ended {date}?"
   - "How much cash and cash equivalents did {company} report at {date}?"
4. Present a small table with figure, period, value and filing URL. Note the fiscal year end if it isn't December.

## Rules

- Use reported figures from the filings, not analyst estimates, unless the user asks for estimates. Label any non-GAAP figure as non-GAAP.
- Keep units as filed (thousands or millions) and say which.
- For a private company, say there are no SEC filings, and offer search for other public sources instead.
