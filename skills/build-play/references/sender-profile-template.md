# Sender profile

Create `plays/sender-profile.md` from the block below. Ask the user each question and use the default if they skip. In the compliance section, keep only the rows for the regions the user selects, plus "Always".

```markdown
# Sender profile

- **Sender first name (sign-off):** <name>
- **Company and one-line description:** <what we do, in plain words>
- **Company name in emails:** never | only when asked | always     (default: never)
- **Customer names in emails:** never | anonymised only | named if approved     (default: anonymised only)
- **Spelling:** British | American     (default: American)
- **Capitalisation:** sentence case | all lowercase except names     (default: sentence case)
- **Length:** max words from the first body line to the last, excluding greeting, sign-off and any compliance lines     (default: 60)
- **Greeting:** "hey <Name>" | "Hi <Name>," | "<Name>,"     (default: "Hi <Name>,")
- **Default ask:** "worth sending over?" | "open to a quick look?" | custom, e.g. a meeting ask     (default: "worth sending over?", never a meeting)
- **Outreach regions:** UK | EU (which countries) | US | Canada | Australia | other
- **Legal company name and postal address:** <needed for US, Canada and Australia>
- **Opt-out line:** <e.g. "Not relevant? Tell me and I won't email again.">
- **Do-not-contact rules:** <lists, existing customers, partners, regions>
- **Words and phrases the sender never uses:** <list>
- **Sample email the sender likes (optional):** <paste one>

## Compliance notes (the agent follows these; it never sends)

General guidance, not legal advice; check with your own counsel. The row that applies is the one for the account's country, not the sender's.

- **UK (PECR + UK GDPR):** emailing a company or LLP address is generally allowed without prior consent if the sender is identifiable and there's a working opt-out. Sole traders and some partnerships count as individuals and need consent.
- **EU (ePrivacy + GDPR):** rules differ by country. Some (for example Germany and Austria) require prior consent even for business emails. Ask the user to confirm the rule before drafting.
- **GDPR (UK and EU):** when personal data comes from a third party, the person must usually be told where it came from, at the latest in the first message (Art. 14). Keep only what you need and note the source of each detail.
- **US (CAN-SPAM):** accurate sender identity, no deceptive subject lines, a valid postal address and a working opt-out.
- **Canada (CASL):** needs consent, but it can be implied when the address is conspicuously published, there's no "no solicitation" notice and the message relates to the person's role. Needs sender ID, postal address and unsubscribe. Ask before drafting.
- **Australia (Spam Act):** needs express or inferred consent (a published work address relevant to the role can count), clear sender identification and a working unsubscribe.
- **Other regions:** no default. Ask the user.
- **Always:** honour the do-not-contact rules. Don't collect personal (non-work) emails or phone numbers unless the user has a lawful basis and asks.
```
