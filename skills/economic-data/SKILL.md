---
name: economic-data
description: Use when the user asks about the economy or an official economic number, in words like "is the economy slowing down", "what have unemployment and inflation done this year", "what's core inflation now", "what did the Fed just do", "are mortgage rates going up", "how many jobs were added last month" or "how much does the US import from China". Reads the official series from FRED (unemployment, inflation, GDP, interest rates, jobs, housing and thousands more) and Census Bureau trade data, and cites each series with its latest date, using Hyperresearch Answers.
---

# Economic data and official statistics

## Tools

This skill uses the Hyperresearch Answers connector:

- `data_and_web_answer`: the answer tool. One question, one short cited answer.
- `data_and_web_search`: the search tool. Ranked sources with the exact passages.
- `get_pending_answer`: the pending-answer tool. Collects an answer that came back pending, by its id.

Older connections may show these as `ask`, `search` and `get_answer`. Each call uses the user's Hyperresearch balance.

## Steps

1. Turn a loose question into a few named measures. "Is the economy slowing down" usually means: GDP growth, the unemployment rate, monthly job gains and inflation. Three or four measures are enough.
2. Ask the answer tool one question per measure, naming the series, the place and the period:
   - "What has the US unemployment rate (FRED series UNRATE) been each month over the last 12 months?"
   - "What has US core CPI inflation, year over year, been over the last 12 months, according to FRED?"
   - "What was US real GDP growth in the latest quarter, according to FRED?"
   - "What is the current federal funds target range, and when did the Fed last change it?"
   - "What was the value of US imports from China in {year}, according to Census Bureau trade data?"
3. Collect any pending answers with the pending-answer tool.
4. Present each measure with its latest value, its date, the change over the period and the series URL. Then answer the user's question in two or three plain sentences, saying what the numbers show and what they don't.

## Rules

- Give the date of every figure. Economic series are revised and updated often.
- Say whether a figure is monthly, quarterly or annual, and whether it is seasonally adjusted, when the source says.
- Don't forecast. If the user asks what will happen, report the latest data and say it describes the past.
- Leave the mode at its default. Fast mode reads only the open web and can't reach the official series.

## Example

User: "What have US unemployment and core inflation done over the last 12 months?"

1. Answer tool: "What has the US unemployment rate (FRED series UNRATE) been each month over the last 12 months?"
2. Answer tool: "What has US core CPI inflation, year over year, been over the last 12 months, according to FRED?"
3. Reply with a two-row table (start value, latest value, latest month, series URL) and one sentence on each trend.
