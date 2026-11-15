# Hyperresearch Answers plugin for Claude

Cited answers from the record itself: SEC company filings, FRED and Census economic data, USPTO patents and trademarks, ClinicalTrials.gov and FDA records, federal lobbying and FEC campaign-finance filings, FDIC bank records, NOAA weather and climate records, scholarly papers and books, among 120+ structured public data sources, plus the live web. Every answer is checked word for word against quotes from the pages it cites, and the quotes and links come back with it.

## What's inside

**Connector** (`.mcp.json`): the Hyperresearch Answers MCP server at `https://answers.hyperresearch.ai/mcp`, with three tools:

- `data_and_web_answer`: one question, one short answer checked word for word against quotes from the pages it cites. Returns "not found" or "unconfirmed" instead of guessing, and flags false premises.
- `data_and_web_search`: ranked sources with the exact passages and no written answer.
- `get_pending_answer`: collects an answer that is still being worked on, by its id.

Older connections may show these tools as `ask`, `search` and `get_answer`. They work the same.

**Skills**

| Skill | For questions like |
|---|---|
| `company-financials` | "How is Nvidia doing financially?" Reported revenue, profit, segments and cash from 10-K and 10-Q filings |
| `economic-data` | "Is the economy slowing down?" FRED series and Census trade data, each with its date |
| `lobbying-and-campaign-finance` | "How much does Meta spend on lobbying?" LDA lobbying filings and FEC records |
| `patents-and-trademarks` | "Who is patenting solid-state batteries?" USPTO patents and trademarks |
| `clinical-trials-and-drugs` | "Are there trials for this condition?" ClinicalTrials.gov, FDA records and drug labels |
| `public-records` | "Which banks have the most uninsured deposits?" FDIC bank records, SEC identifiers, FEC committees, nonprofit filings |
| `market-snapshot` | "How big is the market for home batteries?" Size, growth, competitors and pricing, with publishers |
| `fact-check` | "Can you check these numbers?" A verdict table with a source for every claim |
| `cited-answers` | "Where does that number come from?" Phrasing questions, picking a tool, citing results |

## Setup

1. Install the plugin from the Claude plugin directory, or in Claude Code:
   ```
   /plugin install hyperresearch-answers --marketplace jordan-gibbs/hyperresearch-answers-plugin
   ```
2. When Claude first calls a tool, a Hyperresearch sign-in window opens. Sign in or create an account at [hyperresearch.ai](https://hyperresearch.ai) and approve access.
3. Each call uses your Hyperresearch balance. The tools never change anything in your account.

## Example prompts

- "How much did Meta spend on federal lobbying in 2024?"
- "What net sales did Apple report in its latest 10-K?"
- "According to FDIC BankFind, what is the FDIC certificate number of Silicon Valley Bank (Santa Clara, California)?"
- "What have US unemployment and core inflation done over the last 12 months?"
- "Fact-check the numbers in this paragraph."

## Links

- Product and setup guide: https://hyperresearch.ai/answers
- Privacy: https://hyperresearch.ai/legal/privacy
- Terms: https://hyperresearch.ai/legal/terms
- Support: support@hyperresearch.ai

## License

MIT. See [LICENSE](LICENSE). The license covers the files in this repository. Use of the Hyperresearch service is governed by its Terms.
