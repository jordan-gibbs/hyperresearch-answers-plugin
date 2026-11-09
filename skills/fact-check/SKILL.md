---
name: fact-check
description: Check the numbers, dates and factual claims in a draft, report, email or slide against sources, using Hyperresearch Answers. Use when the user asks to fact-check, verify, source or "check the numbers" in a piece of text.
---

# Fact-check a draft

Goal: a table showing which claims the sources support, which they contradict, and which nobody can confirm.

## Steps

1. **Extract the checkable claims.** Pull out every statement with a number, date, name, ranking, quote or "first/largest/only" wording. Skip opinions and predictions. If there are more than about 15, ask the user which section matters most, since each check is a paid call.
2. **Turn each claim into one question.** "US e-commerce was 16% of retail sales in 2025" becomes "What share of US retail sales was e-commerce in 2025, according to the Census Bureau?" Keep the original wording next to it.
3. **Call ask once per claim.** Collect pending answers with get_answer.
4. **Compare.** Mark each claim:
   - **Supported**: the quoted source says the same thing (allow rounding and stated ranges).
   - **Contradicted**: the source gives a different figure or fact. Give the sourced version.
   - **Outdated**: right for an earlier period, but a newer figure exists.
   - **Unconfirmed**: ask returned not found or unconfirmed.
5. **Report** as a table:

| # | Claim as written | Verdict | What the source says | Source |
|---|---|---|---|---|

Then list a suggested rewrite for every contradicted or outdated claim, each with its URL.

## Rules

- Never mark a claim supported from memory. Only the returned quotes count.
- If the draft already cites a source, check that the cited page says it. A real number with the wrong source is still worth flagging.
