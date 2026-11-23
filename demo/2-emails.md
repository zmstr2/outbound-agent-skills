> **Demo, fictional.** This is what `cold-email-drafts` returns for the contact in `1-dossier.md`. It was written by hand to show the format and to follow the skill's own rules; it is not a recorded run. Note that finding F2 is tagged `(sensitive)` and is not used anywhere below.

## Reasoning
For Sam Okafor, Financial Controller (champion). Current approach: assumed each ERP's built-in matching module plus spreadsheets for the rest (T2, J1); the dossier doesn't say more.

Pattern: two acquisitions in 18 months, three ledgers, one consolidation under way, and matching still done by hand across ledgers.

| Core pain | Signal (evidence ID) | How it shows the pain | Why their current approach doesn't fix it | Why Sam cares | What would help |
| --- | --- | --- | --- | --- | --- |
| Slow close | J1: analyst reconciles "across our three ledgers, mostly in spreadsheets" | Matching waits on a person and a spreadsheet each month | ERP modules match within one ledger, so cross-ledger exceptions end up in spreadsheets | Measured on the close timeline | An example of one process across entities |
| Slow close | F1, N1: two acquisitions adding ledgers in 18 months | Each new entity brings its own matching rules | One-ledger modules need setup per entity, and the migration isn't due until 2027 (T1) | Her own words: "another set of matching rules" (C1) | A short example of putting acquired entities on one process |
| Money lost | F1 plus T2: multiple ledgers, matching partly manual | Duplicate or mismatched payments can slip between ledgers | Nothing checks across ledgers until the migration | Controls are part of her remit | A check on the cause in their own data |

## Options

### 1 · Close waits on matching
- **Signal:** J1, AP analyst ad, 2026-10-20: reconcile across three ledgers "mostly in spreadsheets"
- **Pain:** month-end stalls on unmatched invoices
- **Why their current approach doesn't fix it:** ERP modules match within one ledger, not across three
- **Why they care:** measured on the close timeline
- **What the offer gives them:** a closer look at how others got matching done before close starts
- **Subject:** month-end matching

```text
Hi Sam,

Saw your AP analyst ad mention matching across three ledgers in spreadsheets

Is month-end waiting on unmatched invoices?

I've got a short example of how a finance team put three acquired entities on one process

Worth sending over?

Alex
```

### 2 · Acquired entities, new rules
- **Signal:** C1, Sam's post "Every acquisition means another ledger…", 2026-09-14; F1 and N1, two acquisitions
- **Pain:** each acquired ledger arrives with its own matching rules
- **Why their current approach doesn't fix it:** per-entity setup, and the single platform isn't due until 2027 (T1)
- **Why they care:** it's her own stated problem
- **What the offer gives them:** one rule set across entities without waiting for the migration
- **Subject:** another ledger

```text
Hi Sam,

Read your post on every acquisition adding another set of matching rules

How long before a new entity is matched the same way as the rest?

I've got a short write-up of how one team had acquired entities on one rule set in weeks

Worth sending over?

Alex
```

### 3 · Paying twice
- **Signal:** F1 and T2, multiple ledgers with partly manual matching
- **Pain:** duplicate or mismatched payments slipping between ledgers
- **Why their current approach doesn't fix it:** nothing checks across ledgers
- **Why they care:** controls are in her remit
- **What the offer gives them:** finding out whether it's happening, from their own data
- **Subject:** duplicate payments

```text
Hi Sam,

Saw the Calder & Pike deal added two more ledgers

Could the same invoice get paid once in each?

I can run a quick check on the cause using a sample of your own invoices

Worth a look?

Alex
```

## Before sending
- Assumption: matching is ERP modules plus spreadsheets. If Harbourline already uses a procure-to-pay suite, drop options 1 and 3.
- Option 3 is the boldest; the question implies a risk they may not have. Use it second or not at all.
- Compliance (UK): corporate address, so legitimate-interest outreach is generally allowed. Add the sender's opt-out line. Note in the send log that the contact's role came from public LinkedIn and the company site.

## For contrast: a generic AI cold email for the same account
```text
Hi Sam,

I hope this email finds you well! I came across Harbourline Foods and was impressed by your recent growth. At Ledgerly we help finance teams like yours streamline invoice processing with cutting-edge automation. Would you be open to a 30-minute call next week to explore how we can help?

Best regards,
Alex
```
The generic version names no source, pokes no pain, pitches the product, and asks for a meeting. Every line of the options above traces to an evidence ID.
