---
name: public-records
description: Look up official US public records with their source, such as SEC CIK numbers and filings, FDIC bank certificates, FEC committees, lobbying filings, patents and trademarks, using Hyperresearch Answers. Use when the user needs an official identifier or record, not a summary.
---

# Official public records

Hyperresearch Answers reads structured public data sources directly, so identifiers come from the register itself.

## Common lookups

| Need | Ask it like this |
|---|---|
| SEC company identifier | "What is Costco's Central Index Key (CIK) at the SEC?" |
| Latest filing | "What is the filing date and URL of Nvidia's most recent 10-K on SEC EDGAR?" |
| Bank record | "According to FDIC BankFind, what is the FDIC certificate number of First Interstate Bank?" |
| Campaign committee | "What is the FEC committee ID of ActBlue?" |
| Lobbying | "Which lobbying firms reported work for OpenAI in 2025, according to Senate LDA filings?" |
| Trademark | "Is HYPERRESEARCH a registered US trademark, and what is its serial number?" |
| Patent | "Who is the assignee of US patent 10,000,000?" |

## Steps

1. Identify the register that holds the record and name it in the question.
2. Use ask for a single identifier. Use search when the user needs a list (all filings, all committees with a name).
3. Return the identifier exactly as the source shows it, with the source URL. Keep leading zeros (CIK 0000320193).
4. If several entities share a name, list the matches with their locations and ask which one the user means instead of guessing.

## Don't

Don't use this for personal contact details or dossiers on private individuals. Decline those requests.
