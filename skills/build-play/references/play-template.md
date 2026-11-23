# Play file template

One play = one file at `plays/<name>.md`. `account-research` reads Part A, `cold-email-drafts` reads Part B. Fill in every section (write "none" if one doesn't apply) and mark anything unconfirmed `TODO`. Section names are read by the other skills; don't rename them. A finished example: [../examples/example-invoice-reconciliation.md](../examples/example-invoice-reconciliation.md).

Terms used below:
- **Qualifying signal:** the quick public check that decides whether an account is worth researching.
- **Incumbent:** whatever the account uses today instead of you (a tool, a consultancy, spreadsheets).
- **Binding constraint:** the thing that actually hurts, as opposed to a side effect of it.
- **Poke the bear:** the one question in an email that names the pain or its cost.

---

```markdown
---
play: <short-kebab-name>
status: draft | ready        # ready = the user has reviewed and approved it
updated: <YYYY-MM-DD>
---

# <Play name> play

<One sentence: what we sell, to whom, instead of what.>

Sources: <links, call notes, docs this play is based on.>

## Part A · Research brief

### Who fits
<The kind of organisation this play suits and why: size, industry, region.>

### Qualifying signal
<One or two searches the researcher can run, with keywords. If two searches find nothing, the account is dropped.>

### Current tool or approach
<What accounts use today for the work we replace, including "none".>

### Profile fields
<Optional. Extra lines for the dossier's Company profile, e.g. "ERP: <system>". Write "none" if not needed.>

### Company evidence
Each item goes in the dossier section shown.
- <what to look for> → <dossier section>
- News and events from the last 24 months: <the kinds that matter> → News and events

### Job ads
- <roles or phrases that signal the pain>

### Contacts to find
In this order.
1. <role and example titles>. Persona: <persona>.

**Contact topics** (for statements): <topics>

**Background to note:** <e.g. did they lead this kind of change before>

**Contact details to collect:** work email only | none      (default: none)

**Treat as sensitive** (tagged in the dossier, never used in emails): <e.g. layoffs, legal trouble>

### Claims to check on the source page
- <the findings the writer will lean on most>

### Dossier sections
Optional extra sections, one ID letter each (never T, N, J or C). Every "→ section" target in Company evidence must be Company profile, News and events, or one of these.
- **After Company profile:** `## <section>`, IDs <letter>1…, columns `ID | Finding | Published | Source`.

## Part B · Messaging

### Pattern and fit
<One line: what the reasoning's "Pattern" line should sum up for this play. One line: which accounts get the strongest angles and which need adjusting.>

### Where we win and lose
We win against any incumbent on:
- **<strength>:** <what it means for the buyer>

| Incumbent | Typical use | Poke | Avoid |
| --- | --- | --- | --- |
| **<tool, consultancy or "no tool">** | <how accounts use it> | <pains it leaves open> | <what it does better than us; never poke> |

**Naming the incumbent in an email:** <how to refer to it without naming it>

### Core pains
| Core pain | Meaning | Angles |
| --- | --- | --- |

**Binding constraint example:** <a signal that looks like the pain but is a side effect (don't poke)> vs <the constraint that actually hurts (poke this)>.

**Best signals:** <evidence that best proves these pains, ideally the company's own words>

### Personas in this play
Library personas: economic buyer (owns the budget), champion (owns the work and carries the case), user (does the hands-on work), technical evaluator (checks fit and security), blocker (procurement, legal). Use them or define your own. One line each, always including "Email them?":
- **<Persona> (<titles>).** Role in the deal: <…>. Email them? <yes / rarely / no>. Measured on: <…>. How to pitch: <…>. Pains in this play: <…>.

### Angle bank
Default angles (used first, when the dossier has a signal for them): <numbers>.
1. **<Angle name>** (<core pain>). Pain: <…>. Signals: <what the researcher can find>. Name: <costs to name in the question>. Value: <what changes for them>. <Strong or weak vs which incumbents.>

### Claims
**Plain outcomes (use freely, once the user has confirmed each):** <outcomes we can say without a number>

**Numbers and customer proof (only these; check others with the user):**
- <approved figure and its source> (<when to use it>)
- <anonymised customer proof, e.g. "a regional bank …"> (<only if the customer has agreed>)
- A `TODO` here stays until the user supplies a sourced figure and is never used in an email.

Third-party market statistics go in Sources as context, not here.

### Words to avoid
- <jargon or loaded words, with plain replacements>

### Examples
Follow the sender profile's greeting, capitalisation and spelling.

**Hook**
- Good: "<…>"
- Vague: "<…>" (<why>)

**Poke the bear**
- "<good>" beats "<weaker>".

**Full email.** Dossier: <…>. Pain: <…>. Current approach: <…>. Cares: <…>. Offer: <…>.

    Subject: <…>

    <greeting>

    <hook>

    <question>?

    <offer>

    <ask>?

    <Sender>

## Changelog
- <YYYY-MM-DD>: <one-line change>
```
