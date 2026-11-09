# Hyperresearch Answers plugin for Claude

Quote-checked answers and raw sources from the open web plus more than 90 structured public data sources: company filings, campaign-finance and lobbying records, bank and nonprofit registers, patents and trademarks, drug labels and biomedical databases, economic and government statistics, weather and climate records, scholarly indexes and books.

## What's inside

**Connector** (`.mcp.json`): the Hyperresearch Answers MCP server at `https://answers.hyperresearch.ai/mcp`, with three tools:

- `ask`: one factual question, one short answer checked word for word against quotes from the pages it cites. Returns "not found" or "unconfirmed" instead of guessing, and flags false premises.
- `search`: ranked raw sources with verbatim passages and no synthesis.
- `get_answer`: collects a pending answer by id, at no extra charge.

**Skills**

| Skill | Use it to |
|---|---|
| `cited-answers` | Pick the right tool, phrase questions well and cite results |
| `fact-check` | Check the numbers and claims in a draft against sources |
| `public-records` | Look up SEC, FDIC, FEC, lobbying, patent and trademark records |
| `company-financials` | Pull a public company's reported figures from its filings |
| `market-snapshot` | Size a market and list competitors and their pricing, with sources |

## Setup

1. Install the plugin from the Claude plugin directory, or in Claude Code:
   ```
   /plugin install hyperresearch-answers --marketplace jordan-gibbs/hyperresearch-answers-plugin
   ```
2. When Claude first calls a tool, a Hyperresearch sign-in window opens. Sign in or create an account at [hyperresearch.ai](https://hyperresearch.ai) and approve access.
3. Each call is paid from prepaid credit in your Hyperresearch account. Every result states what that call cost and the balance left. The tools never change anything in your account.

## Example prompts

- "According to FDIC BankFind, what is the FDIC certificate number of Silicon Valley Bank (Santa Clara, California)?"
- "Fact-check the numbers in this paragraph."
- "Pull Costco's latest annual revenue and net income from its 10-K."
- "Give me a market snapshot of US restaurant POS software."

## Links

- Product and setup guide: https://hyperresearch.ai/answers
- Privacy: https://hyperresearch.ai/legal/privacy
- Terms: https://hyperresearch.ai/legal/terms
- Support: support@hyperresearch.ai

## License

MIT. See [LICENSE](LICENSE). The license covers the files in this repository. Use of the Hyperresearch service is governed by its Terms.
