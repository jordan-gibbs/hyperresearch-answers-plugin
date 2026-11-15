---
name: patents-and-trademarks
description: Use when the user asks who is patenting or inventing something, who owns a patent or a brand name, or whether a name is taken, in words like "who's patenting solid state batteries", "which companies hold the most patents on this", "who owns patent 10,000,000", "is this name trademarked" or "is the PLAYSTATION trademark still live". Looks up US patents and trademarks in USPTO records, with assignees, owners, status and links, using Hyperresearch Answers.
---

# Patents and trademarks

## Tools

This skill uses the Hyperresearch Answers connector:

- `data_and_web_answer`: the answer tool. One question, one short cited answer.
- `data_and_web_search`: the search tool. Ranked sources with the exact passages.
- `get_pending_answer`: the pending-answer tool. Collects an answer that came back pending, by its id.

Older connections may show these as `ask`, `search` and `get_answer`. Each call uses the user's Hyperresearch balance.

## Steps

1. Work out which kind of question it is:
   - **Who is active in a field** ("who's patenting solid-state batteries"): use the search tool, so you can read several sources and count assignees yourself.
   - **One patent or one mark** ("who owns patent 10,000,000", "is PLAYSTATION live"): use the answer tool.
2. Name the record and the period in the question:
   - "Which companies are the assignees on recent US patents for solid-state batteries, according to USPTO records?"
   - "Who is the assignee of US patent 10,000,000?"
   - "Is the PLAYSTATION trademark registration live at the USPTO, and who owns it?"
   - "Is HYPERRESEARCH a registered US trademark, and what is its serial number?"
3. For a field, list the assignees with how many patents or applications each source shows, and the URLs. Keep companies that announce research apart from companies that hold patents.
4. For one record, give the number, owner, status and dates exactly as the record shows them, with the link.

## Rules

- Patent applications are not granted patents. Say which each one is.
- If a figure comes from a patent-landscape report rather than USPTO records, name the publisher.
- Don't give legal advice on whether a name can be used or a product infringes. Report what the records show and suggest a patent or trademark attorney for the decision.
- Leave the mode at its default. Fast mode reads only the open web and can't reach USPTO records.

## Example

User: "who's patenting solid state batteries"

1. Search tool: "assignees of US patents and applications on solid-state batteries, USPTO".
2. Reply with a short table of the main assignees, what each source shows for them and the URLs, then one sentence on who leads.
