# Outbound Agent Skills

Three Claude skills that turn "I have an offer" into cold emails grounded in real evidence, instead of generic spam.

**The difference, for the same contact:**

> *Generic AI email:* "I hope this email finds you well! … At Ledgerly we help finance teams like yours streamline invoice processing with cutting-edge automation. Would you be open to a 30-minute call?"
>
> *This pipeline:* "Saw your AP analyst ad mention matching across three ledgers in spreadsheets. Is month-end waiting on unmatched invoices? I've got a short example of how a finance team put three acquired entities on one process. Worth sending over?"

Every line of the second email traces to a sourced finding. See the [full demo](demo/) (fictional company): the [dossier](demo/1-dossier.md) and the [reasoning and options](demo/2-emails.md).

| Skill | What it does |
| --- | --- |
| **build-play** | Interviews you, researches your files, connected apps and the web, and writes a *play*: one reference file for one use case, angle or campaign. Also sets up your sender profile. |
| **account-research** | For a company (or list), checks the play's qualifying signal, then builds a sourced dossier: tools they use, news, job ads, contacts, public statements. Collects evidence only. |
| **cold-email-drafts** | Reads a dossier and one contact, reasons from signal to pain to offer, and drafts 3 to 5 short options on different angles. Never sends. |

```
build-play → plays/<name>.md → account-research → dossiers/<company>-<play>.md → cold-email-drafts → email options
```

## What's a play?

One offer, aimed at one kind of account, triggered by one kind of signal. You'll have several over time (products, segments, events, competitors). Each is one markdown file the other two skills load:

- **Part A, research:** who fits, the qualifying signal, what they use today, what to look for, which contacts to find.
- **Part B, messaging:** where you win and lose, core pains, personas, angle bank, approved claims, words to avoid, examples.

See [the example play](skills/build-play/examples/example-invoice-reconciliation.md) (fictional).

## Design decisions

- **Research collects; drafting judges.** The research skill records evidence with sources and dates and refuses to decide the angle. That keeps the dossier reusable and the reasoning reviewable.
- **Plays are files, not prompts.** Positioning, pains and approved claims live in a versioned file you can review, diff and improve from reply data, instead of being rewritten into each prompt.
- **Tools are capabilities, not brands.** Skills say "web search" and "company data" and list example tools, so they work with whatever you have connected.
- **No invented facts.** Unknown claims are `TODO` and never reach an email. Plays have a draft/ready approval gate, and findings tagged `(sensitive)` are never used.
- **A human always sends.** Nothing is sent and no CRM is written to.
- **Never poke what the incumbent does well.** Emails only raise pains the current tool or process leaves open.

## Install

**Claude Code:** copy the three folders in `skills/` into `~/.claude/skills/` (all projects) or `<project>/.claude/skills/`.

```bash
git clone <repo-url>
cp -R outbound-agent-skills/skills/* ~/.claude/skills/
```

**Claude.ai and desktop:** zip each skill folder (`build-play`, `account-research`, `cold-email-drafts`) and upload it under Settings → Capabilities → Skills.

Work from a folder where your `plays/` and `dossiers/` will live. They're git-ignored because they hold your positioning and contact data. If your environment doesn't keep files between sessions, `build-play` gives you the play and sender profile as downloads to attach when you run the other two skills. The skills work when installed separately and share information only through the `plays/` and `dossiers/` files.

## Quick start

1. "Build a play for `<what you sell>`." You'll be interviewed, then review and approve `plays/<name>.md`.
2. "Research `acme.com` for the `<name>` play." You get `dossiers/acme-<name>.md`.
3. "Draft cold emails for `<contact>` from that dossier." You get the reasoning plus 3 to 5 options. Edit and send them yourself.

## Tools

The skills use whatever you have connected and note what's missing. Useful: web search, page reading, company data, contact data, a signed-in browser (LinkedIn, careers pages), social search, and read-only access to your CRM or call recorder. Results are thinner without web search and page reading.

## Status and testing

The skills and the demo are new. The demo files are hand-written to show the format, not recorded model runs. [evals/cases.md](evals/cases.md) lists 11 test cases for the behaviours the skills promise (sensitive findings never used, TODO claims never emailed, draft plays flagged, and more); none has been run yet, and results will be recorded there. The compliance notes are general guidance, not legal advice.

## Contributing

Plays you've validated, with customer and prospect details removed, are welcome as examples: open a PR adding a file to `skills/build-play/examples/`.

## License

MIT. See [LICENSE](LICENSE).
