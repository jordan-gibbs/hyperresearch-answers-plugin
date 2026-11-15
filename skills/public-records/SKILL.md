---
name: public-records
description: Use when the user asks about a US bank, a company's official registration or a nonprofit, in words like "which banks have the most uninsured deposits", "is this bank FDIC insured", "what's Costco's CIK", "find their latest 10-K", "what's the FEC ID for ActBlue" or "how much does this charity take in". Looks up the official record in FDIC bank records, SEC EDGAR, FEC committee records, nonprofit Form 990 filings and company registers, and returns it exactly as the source shows it, with its link, using Hyperresearch Answers.
---

# Official public records

Hyperresearch Answers reads structured public data sources directly, so identifiers and figures come from the register itself.

## Tools

This skill uses the Hyperresearch Answers connector:

- `data_and_web_answer`: the answer tool. One question, one short cited answer.
- `data_and_web_search`: the search tool. Ranked sources with the exact passages.
- `get_pending_answer`: the pending-answer tool. Collects an answer that came back pending, by its id.

Older connections may show these as `ask`, `search` and `get_answer`. Each call uses the user's Hyperresearch balance.

## Common lookups

| Need | Ask it like this |
|---|---|
| Bank record | "According to FDIC BankFind, what is the FDIC certificate number of First Interstate Bank?" |
| Banks ranked by a measure | "Which US banks have the largest share of uninsured deposits right now?" (the search tool, for a ranked list with sources) |
| SEC company identifier | "What is Costco's Central Index Key (CIK) at the SEC?" |
| Latest filing | "What is the filing date and URL of Nvidia's most recent 10-K on SEC EDGAR?" |
| Campaign committee | "What is the FEC committee ID of ActBlue?" |
| Nonprofit | "What total revenue did {organization} report on its latest Form 990?" |

Lobbying spend, political donations, patents, trademarks, economic statistics and clinical trials have their own skills.

## Steps

1. Identify the register that holds the record and name it in the question.
2. Use the answer tool for a single identifier or figure. Use the search tool when the user needs a list (all filings, all committees with a name, banks ranked by a measure).
3. Return the identifier exactly as the source shows it, with the source URL. Keep leading zeros (CIK 0000320193).
4. If several entities share a name, list the matches with their locations and ask which one the user means instead of guessing.
5. Leave the mode at its default. Fast mode reads only the open web and can't reach the registers.

## Example

User: "According to FDIC BankFind, what is the FDIC certificate number of Silicon Valley Bank (Santa Clara, California)?"

1. One answer tool call with that question.
2. Reply with the certificate number, quoting the FDIC BankFind page and its URL.

## Don't

Don't use this for personal contact details or dossiers on private individuals. Decline those requests.
