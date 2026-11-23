---
name: account-research
description: >-
  This skill should be used when the user asks to research, enrich or build a
  dossier on one company or a list of companies (name and domain) for an
  outbound play, or to find and research the right contacts at them. Checks each
  account for the play's qualifying signal, then collects sourced evidence on
  the company, its news, job ads, the tool or approach it uses today, and the
  contacts the play targets, using whatever search, page-reading, company-data
  and browser tools are connected. Collects evidence only; it doesn't decide the
  pain, angle or message. Needs a play file in plays/; if none exists, use
  build-play first.
---

# Account research

Collect the evidence about an account and its people for one play, and write it up as a dossier. A later step (or the user) decides the pain, the angle and the message, so don't make those calls here. Record what you find, with sources and dates, completely enough that someone who wasn't there can judge it.

Everything specific to a play (who fits, the qualifying signal, what to look for, who to find) is in Part A of its play file.

## Step 0 · Load the play

1. List `plays/*.md` (ignore `sender-profile.md`), or use a play file the user attached. If the user named a play use it; if unclear, show the list and ask.
2. **If no play fits, stop** and offer to run `build-play`. Don't guess what to look for.
3. Read the whole play file and follow it wherever this file says "the play". If its `status` is `draft`, tell the user and continue only if they say so.
4. Read `plays/sender-profile.md` if it exists, for the do-not-contact rules and compliance notes. If it doesn't exist, keep personal data to a minimum.

## Inputs

One account or a list, each with a company name and domain. Carry any country or CRM ID through to the dossier. Skip any account that matches the sender profile's do-not-contact rules and say why.

## Sources

Use whichever of these are connected. If one isn't available, skip it and note the gap in the dossier. Never fill a field from memory.

| Capability | Used for | Examples |
| --- | --- | --- |
| Web search | news, events, interviews, analyst views | Exa, Brave, Perplexity, built-in search |
| Page reading | checking a claim on its source page, careers pages, annual reports | Firecrawl, built-in fetch, a browser |
| Company data | headcount, tech stack, funding | Apollo, Crunchbase, TheirStack |
| Contact data | titles, start dates, work emails | Apollo, FullEnrich, Hunter |
| Signed-in browser | LinkedIn jobs, company pages and profiles; careers sites | the user's browser tool |
| Social (read only) | public posts and profiles | X, LinkedIn |
| The user's systems (read only) | existing relationship, past deals | CRM, call recorder |

Read API keys from the environment and never print them. Check limits before a big batch.

## What to collect

**Company:** everything in the play's "Company evidence". Always include:
- The tool or approach they use today for the work the play replaces, and how direct the evidence is.
- Headcount: the official figure (annual report, filings) with its date, plus a data provider's figure as an estimate; note conflicts.
- News and events from the last 24 months, of the kinds the play lists.

**Job ads (last 12 months):** the roles the play lists, and any tools named. For each: title, team, location, posted date, link, and a few short quotes in the company's own words.

**People:** the play's "Contacts to find", in order. If more people clearly fit a slot, keep them all. For each: persona, current title, start date, profile link, the background the play asks for, and what they've said publicly in the last 3 years on the play's contact topics (posts, interviews, podcasts, talks).

Work emails only if the play's "Contact details to collect" says so or the user asks; keep an address only if its domain matches the company's, and record the provider. Personal emails and phone numbers only if the user explicitly asks and the compliance row for the account's country allows it.

## How to work

1. **Quick check.** Run the play's qualifying-signal searches. If two find nothing relevant, stop for this account and record that. For a list, do this for every account first and report which you're continuing with.
2. **Research the company** with search, page reading and company data. Retry a failed tool once. If a careers site won't load, a job board is enough; mark ads found only on an aggregator, with the repost date.
3. **Find and research the contacts.** Check the news for recent appointments and departures before trusting a profile; databases lag by months.
4. **Social, read only** (never post, like, follow or message): search the company plus the play's change keywords, recent leadership moves, and each contact's posts on the contact topics. Accept a contact's account only if its bio or posts clearly tie it to them, and rate the match high, medium or low. Don't treat a post as fact without a second source.
5. **Check the play's "Claims to check"** on their source pages. Add `(checked)` to a finding once confirmed; if it fails, list it under "Not found or not collected".
6. **Write the dossier** to `dossiers/<company>-<play>.md` and give the path.
7. **Reply with a contacts outline**, one line each: **[<Name>](<profile URL>)** · <title> · <persona> · since <date>. <what we learned in one or two sentences>. If a profile wasn't found, say so.

## Dossier

Give every piece of evidence an ID and cite the IDs in the summary. Core IDs: T (tools and systems), N (news and events), J (job ads), C (contacts). The play adds its own sections and letters.

```markdown
# <Company> · dossier

<domain> · <country> · <CRM ID> · play: <play-name> · researched <date>

## Summary
What we found, citing evidence IDs: what the qualifying signal shows, recent events, their current tool or approach, the key people, and what we couldn't find. Describe; don't rate or recommend.

## Company profile
- Headcount: <number> (<source>, <date>)
- Current tool or approach: <tool, or none found>, <how direct the evidence is> (<ID>)
- <the play's profile fields>

| ID | Finding | Published | Source |
| --- | --- | --- | --- |
| T1 | "<quote or fact about a tool or system>" | <date> | <link> |

<the play's sections placed after Company profile>

## News and events (last 24 months, newest first)
| ID | Date | Event | Source |
| --- | --- | --- | --- |
| N1 | <date> | <what happened> | <link> |

## Job ads
| ID | Title | Team | Posted | What it says | Tools named | Link |
| --- | --- | --- | --- | --- | --- | --- |
| J1 | | | | | | |

## Contacts
### C1 · <Name> · <Title>
- Persona: <persona from the play>
- In role since: <date> · <profile URL>
- Background: <relevant history>
- Statements:
  - "<quote>" (<date>, <link>)
- Social: <handle, match confidence, active or dormant since <date>, or not found>
- Work email: <email> · <provider> · domain matches: <yes or no>   (only if requested)

## Not found or not collected
- <what, and why>
```

For a list, also return one row per account: researched or not, a one-line description, current tool or approach, notable events, contacts found.

## Rules

- **Tag sensitive findings.** Append `(sensitive)` to any finding that matches the play's "Treat as sensitive" list, so the email writer never uses it.
- Use each source's published date, not the date you found it. Leave out company evidence older than 24 months and personal statements older than 3 years. If a post shows only a relative date you can't place inside the window, drop it or mark the date approximate.
- When sources disagree on a start date or appointment, prefer the company's announcement or filing over a database or social profile. When two official documents give different figures, record both with dates and treat the later as current.
- Quote people only from pages where they're the named speaker.
- If you can't confirm something, say so rather than guess.
- Keep personal data to what the play needs and record where each detail came from.
- Don't update any CRM and don't contact anyone.
