---
name: cold-email-drafts
description: >-
  This skill should be used when the user asks to write outreach, draft cold
  emails or suggest messaging angles for a contact, from an account dossier or
  research notes. Produces 3 to 5 short cold email options for one contact, each
  on a different angle, after reasoning from signal to pain to offer. Loads the
  play's pains, angles and approved claims from plays/<name>.md and the sender's
  style from plays/sender-profile.md. Never sends anything. If no play exists
  yet, use build-play first.
---

# Cold email drafts

Input: a dossier (from `account-research` or any research notes) and one contact. Output, in the chat reply: reasoning, then 3 to 5 email options on different angles. **Never send anything.**

Everything specific to a play (incumbents, pains, angles, claims, words to avoid) is in Part B of its play file. The sender's voice is in `plays/sender-profile.md`. Types of contact are in [references/personas.md](references/personas.md), refined by the play's "Personas in this play".

## Step 0 · Load

1. **Pick the play.** The user names it, or the dossier header says `play: <name>`. List `plays/*.md` (ignore `sender-profile.md`), or use an attached play file, and ask if unclear. **If no play fits, stop** and offer `build-play`: never make up pains, angles or claims. If its `status` is `draft`, tell the user and continue only if they say so.
2. **Read the whole play file.**
3. **Read `plays/sender-profile.md`.** If missing, offer to create it via `build-play`, or use the defaults in Style and say so. Find the compliance row for the account's country (from the dossier; if unknown, the strictest of the profile's regions). If it says to ask before drafting, ask.
4. **Pick the contact's persona** from the dossier, or from their title and what they own. Prefer the play's personas; fall back to the library. If the persona's "Email them?" is rarely or no, say so, suggest using their pain as evidence in an email to a better-placed contact, and ask whether to draft anyway.

## Step 1 · Reason

Read the whole dossier, not just the contact's section. Then, from the contact's view:

1. **Signals that prove a core pain.** Start from the play's core pains and the incumbent's weaknesses, not the newest headlines. Best signals are the company's own words on how the work is done (job ads, the contact's words); a pattern of changes over 12 to 24 months often beats one announcement; CEO quotes and strategy statements are weak. State only what the source says.
2. **What it betrays.** What it forces them to do and what that costs. Find the binding constraint, not a side effect (see the play's Core pains).
3. **Does it survive their current approach?** Check "Where we win and lose": if the incumbent already solves the pain, drop it. If the dossier doesn't say how they use it, state your assumption.
4. **Why this person cares**, in terms of what their persona is measured on. Drop pains they don't own.
5. **What would help:** something we could send or do, and what changes for them.

Pick the 3 to 5 strongest chains on different angles, ranked by how clearly the signal proves the pain, how hard it lands for this person, and how clearly we beat their current approach. Prefer the play's default angles when the dossier has a signal for them; otherwise use other angles from the bank. Fewer is fine; never pad.

## Step 2 · Write

Four lines between greeting and sign-off, separated by blank lines. The play's Examples show good and weak versions.

1. **Hook:** name the specific source (which job ad, post, announcement) and the one detail that proves the pain. About 10 words (15 at most). One simple sentence, one idea, no extra clauses. Only what the source says, paraphrased. No "loved your post" or "hope you're well".
2. **Poke the bear:** one question, one clause, that names the pain or its cost early. Put the cost first, name the cost not just the effort, avoid questions with an obvious answer ("is there a risk…?"), and never poke a pain their current approach already solves.
3. **Offer:** something they'd say "yes" to just to get it: a result, proof it's been done, or a check on their own situation. Say what they gain, not our method. About 12 words (20 at most), one idea, and it must follow from the question. Add an approved number only if it makes the value clearer.
4. **Ask:** the sender profile's default ask, with an offer that can actually be sent. Don't ask for a meeting in a first email unless the profile says so.

**Claims:** a number isn't required. Use only the play's plain outcomes and approved numbers; check any other figure with the user. A `TODO` claim never goes in an email.

**Style** (from the sender profile; these are the defaults if a setting is missing):
- Greeting "Hi <Name>," and sign-off with the sender's first name. Sentence case. American spelling. Plain, short words a 10-year-old could follow. Loose, like a quick personal note. 60 words or fewer from first body line to last. No full stop at the end of the hook or offer; questions end in "?"; no dashes or exclamation marks.
- No jargon or the play's "words to avoid", even if it's the contact's own phrase (paraphrase it).
- Never name the sender's company, a customer, a competitor or the incumbent unless the profile and play allow it. Don't pitch the product.
- Use only dossier facts and approved claims. **Never use a finding tagged `(sensitive)`**, even folded into a count or pattern.
- Pitch at the persona's level, and don't split one strong pain across two weak emails.

## Output

```markdown
## Reasoning
For <Name>, <title> (<persona>). Current approach: <incumbent and use, or assumption>.

Pattern: <1 to 2 lines, on what the play's "Pattern and fit" asks for>

| Core pain | Signal (evidence ID) | How it shows the pain | Why their current approach doesn't fix it | Why <Name> cares | What would help |
| --- | --- | --- | --- | --- | --- |
```

Then each option, strongest first. The draft email goes in its own fenced `text` block, plain text only; the subject line goes in the notes above it.

````markdown
### <n> · <angle name>
- **Signal:** <finding, evidence ID, date, link>
- **Pain:** <pain poked>
- **Why their current approach doesn't fix it:** <one line>
- **Why they care:** <what they're measured on>
- **What the offer gives them:** <how it relieves the pain>
- **Subject:** <2 to 4 words, in the sender's case style>

```text
<greeting>

<hook>

<question>?

<offer>

<ask>?

<Sender>
```
````

End with short notes before sending: assumptions about their current approach, tone risks, and the compliance lines for the account's country. Always include the profile's opt-out line, add the postal address for US, Canada and Australia, and for UK and EU a one-line note on where the contact's data came from. These sit outside the word limit.

## Before you hand over

- The chain holds: signal proves a core pain → their current approach doesn't fix it → the persona owns it → the question names it → the offer relieves it → the ask pairs with the offer.
- Every hook traces to a dossier evidence ID, none is tagged `(sensitive)`, and each email is within the word limit.

If the user reports which emails got replies or fell flat, offer to update the play's angle bank and examples via `build-play`.
