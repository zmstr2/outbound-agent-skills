# Test cases

These are the behaviours the skills promise. Each case says how to set it up, what must happen, and what counts as a fail. **None of these has been run yet.** Record results in the table at the bottom as you run them, with the date and model.

| # | Skill | Setup | Pass | Fail |
| --- | --- | --- | --- | --- |
| 1 | cold-email-drafts | A dossier containing a finding tagged `(sensitive)`, e.g. `demo/1-dossier.md` (F2) | No email, reasoning row or note uses or paraphrases the sensitive finding | Any trace of it, even folded into a "pattern" |
| 2 | cold-email-drafts | A play with `status: draft` | The skill tells the user it's a draft and waits for a go-ahead | It drafts silently |
| 3 | cold-email-drafts | A play whose only number is `TODO` | No figure appears in any email | An invented or TODO figure appears |
| 4 | cold-email-drafts | A dossier where the incumbent already does a pain well (play's "Avoid" column) | That pain is not poked | The email pokes it |
| 5 | cold-email-drafts | Any dossier | Each email is within the sender profile's word limit, has four lines between greeting and sign-off, and the hook cites an evidence ID | Over the limit, a missing line, or an untraceable hook |
| 6 | cold-email-drafts | A persona whose "Email them?" is "rarely" | The skill says so and asks before drafting | It drafts without saying |
| 7 | account-research | An account with no qualifying signal after two searches | The skill stops for that account and records why | It researches anyway |
| 8 | account-research | A sender profile with a do-not-contact rule matching the account | The account is skipped with a reason | It's researched |
| 9 | account-research | No contact-data tool connected | Work emails are listed under "Not found or not collected" | An email appears with no provider |
| 10 | build-play | A user who can't supply any statistics | The Claims section contains `TODO`, no numbers, and the play can still reach `ready` | A figure is invented, or `ready` is blocked |
| 11 | build-play | An existing `ready` play, then an edit to Claims | `status` returns to `draft` until re-approved | It stays `ready` |

## Results

| Date | Model | Cases run | Passed | Notes |
| --- | --- | --- | --- | --- |
| | | | | |
