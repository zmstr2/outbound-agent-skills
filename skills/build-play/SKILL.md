---
name: build-play
description: >-
  This skill should be used when the user wants to build, set up or update an
  outbound sales play: for example "build a play for <offer>", "set up cold
  email for <segment>", "define our ICP and messaging against <competitor>",
  "add a new angle or campaign", "update the play with what got replied to", or
  "set up my sender profile and email style". Interviews the user, researches
  their files, connected apps and the web, and writes plays/<name>.md (plus
  plays/sender-profile.md) for the account-research and cold-email-drafts
  skills to use.
---

# Build play

A **play** is one repeatable outbound motion: one offer, aimed at one kind of account, triggered by one kind of signal. A user will end up with several (different products, segments, events, competitors), each in its own file so the other two skills load exactly one.

Your job is to produce that file by asking good questions and doing the research the user shouldn't have to do. Collect and verify; don't invent.

## Where files live

In the user's workspace, not inside the skill folders (which get overwritten on update):

```
plays/
  sender-profile.md        # who signs, tone, spelling, regions, compliance notes
  <play-name>.md           # one per play
dossiers/                  # written by account-research
```

If there's no `plays/` folder, create one (ask first if the directory looks like an unrelated project). If you can't write lasting files (for example a chat sandbox that resets), give the play and sender profile as downloadable files and tell the user to attach them when running the other two skills.

## Step 0 · Sender profile

If `plays/sender-profile.md` doesn't exist, create it from [sender-profile-template.md](references/sender-profile-template.md) by asking its questions. Use the defaults for anything the user skips.

## Step 1 · Scope

Ask what the play is. List `plays/*.md` (ignore `sender-profile.md`) and match by filename or `play:` frontmatter. If one exists, ask whether to revise it or start a new one. Pick a short kebab-case name, e.g. `finance-teams-after-acquisition`.

## Step 2 · Research and interview

Follow [interview-guide.md](references/interview-guide.md): look at the user's own material first, ask only what's left, then research the market.

- Ask once before searching the user's email, chat or call recordings.
- Don't copy prospect or customer names, email addresses or verbatim call quotes into the play unless anonymised, because play files get shared.
- Use whatever tools are connected; skip what's missing and say so.

## Step 3 · Write

Fill in [play-template.md](references/play-template.md) completely, using the guide's "Where each section comes from" table. See [the finished example](examples/example-invoice-reconciliation.md). Rules:

- Never fabricate statistics, customers, quotes or competitor weaknesses. Unknown means `TODO`.
- Every number needs a source. Anything taken from reviews or competitor pages is "unconfirmed" until the user agrees. Summarise competitor material in your own words.
- Keep the angle bank to 3 to 8 angles. An angle with no signal the researcher can find is a wish, not an angle.
- Never name a real customer unless the user confirms they've agreed.
- Set `status: draft`.

## Step 4 · Review and approve

Check that every "→ section" in Company evidence exists, then show a one-screen summary: who fits, the qualifying signal, the incumbent and how we beat it, top three pains, default angles, **plain outcomes and "we win" strengths for the user to confirm**, approved numbers, and open `TODO`s. Apply their edits.

Set `status: ready` only after the user approves, and only if there's no `TODO` in Qualifying signal, Contacts to find, Core pains or Angle bank. `TODO`s elsewhere are allowed and are never used in emails.

Finish by telling the user what to do next: "run account-research on `<company>` for the `<play>` play", then "draft cold emails for `<contact>`".

## Updating a play

When the user reports what got replies, what fell flat, or a new competitor or claim, update the play, bump `updated`, and add a line to its `## Changelog`.

- Edits to Claims, Where we win and lose, or Qualifying signal set `status: draft` until the user re-approves.
- Edits to the Angle bank, Examples or wording keep `ready`.

Don't contact anyone and don't change any connected app's data.
