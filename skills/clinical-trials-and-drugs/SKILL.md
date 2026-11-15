---
name: clinical-trials-and-drugs
description: Use when the user asks about clinical trials, a drug's approval, label, warnings or recalls, or the research behind a treatment, in words like "are there trials for this condition", "what trials are testing this drug", "when does this trial finish", "is this drug FDA approved", "what does the label say about side effects" or "has this been recalled". Looks up ClinicalTrials.gov registrations, openFDA records, drug labels and PubMed, with trial ids and links, using Hyperresearch Answers.
---

# Clinical trials and drug records

## Tools

This skill uses the Hyperresearch Answers connector:

- `data_and_web_answer`: the answer tool. One question, one short cited answer.
- `data_and_web_search`: the search tool. Ranked sources with the exact passages.
- `get_pending_answer`: the pending-answer tool. Collects an answer that came back pending, by its id.

Older connections may show these as `ask`, `search` and `get_answer`. Each call uses the user's Hyperresearch balance.

## Steps

1. Pin down the condition, drug or trial. Use the generic drug name when you know it, and the NCT number for a trial.
2. Pick the tool:
   - **A list of trials** ("are there trials for…"): the search tool, so you can read the registrations side by side.
   - **One fact** (a trial's completion date, an approval date, a label warning): the answer tool.
3. Name the record in the question:
   - "Which ClinicalTrials.gov trials are recruiting for {condition} in the US, and what phase is each?"
   - "What is the primary completion date of trial NCT04368728 on ClinicalTrials.gov?"
   - "When did the FDA approve {drug}, and for what use?"
   - "What boxed warning, if any, is on the FDA label for {drug}?"
   - "Has {drug} been recalled, according to openFDA?"
4. For trials, show a table: NCT id, title, phase, status, sponsor, location if asked, and link. For one fact, give it with the record and its URL.

## Rules

- Report what the records say. Don't recommend a treatment, a dose or a trial for the user, and suggest they talk to their doctor about their own care.
- Give each trial's status as registered (recruiting, completed, terminated), with the date the record was last updated when the source shows it.
- Leave the mode at its default. Fast mode reads only the open web and can't reach the registries.

## Example

User: "What is the primary completion date of trial NCT04368728?"

1. One answer tool call with that question.
2. Reply with the date, whether it is actual or estimated, and the ClinicalTrials.gov URL.
