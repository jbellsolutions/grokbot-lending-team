# ClearBlu Lending Team for Grok Bot

The Grok Bot team for **ClearBlu Capital Group**, a direct real estate lender to investors and developers. Built for Larry Gilmore.

The team works in ClearBlu's GoHighLevel sub-account and does five jobs:

- runs the referral partner program, mortgage lenders and brokers first;
- works every borrower lead that Speed to Lead and reactivation leave behind, with the quick app first;
- runs broker cold email from ClearBlu's own sending, once it's set up;
- keeps the GoHighLevel sub-account clean and working;
- sends Larry one morning brief every weekday and one scorecard every Friday.

Larry stays in charge. Nothing goes out to a partner, a borrower or a prospect until he says yes. No agent touches pricing, term sheets, loan processing, referral terms or owner-occupied loans.

## Before you start

- A Grok plan that includes Grok Bot (Premium or higher).
- The Grok Bot desktop app for the first session. After that, the phone app is enough.
- Admin access to the ClearBlu sub-account in GoHighLevel.
- If this Grok account already runs bots for anything else, think about a separate Grok account for this team. All bots on one account share one computer, its files and its logins.

## Setup

1. **Create a new bot.** In Grok Bot, choose **New chat (+) → Create new Bot**. Use a new bot, not one you already use for something else.
2. **Give it this repo.** Paste this message into the new bot:

   ```
   Set yourself up from this repo: https://github.com/jbellsolutions/grokbot-lending-team
   Read START-HERE.md first and follow it step by step. Ask me before anything goes live.
   ```

3. **Answer its questions.** The bot becomes your Chief of Staff and builds the rest of the team:
   - it sets up the ClearBlu Lending Team project and saves the skills;
   - it creates each bot with its name, label and description;
   - it connects GoHighLevel and maps your account;
   - it creates every routine switched off.

   It already knows ClearBlu's programs, links and pipelines. It confirms them with you once and asks only what's still open. It turns each routine on only after you say yes.

## What only you can do

The bot stops and walks you through each of these when it gets there:

- Pin the Chief of Staff. Paste a bot's description into its details if the bot can't set it itself.
- Create the **ClearBlu Lending Team** project, or a sidebar section with that name, if the bot can't.
- Check that **Settings → Bot → Timezone** is Pacific. Every routine runs on it.
- Add the approval rules in **Settings → General → Auto-review**. The bot gives you the exact lines.
- In the **ClearBlu sub-account** (not the agency), add a staff user for the agents and create a Private Integration token.
- Paste that token once into a hidden prompt on the bot's computer, using **Take over**. It never goes in the chat.
- Save the agent user's GHL login in **Settings → Vault**, and type any two-factor code.
- Say yes to each routine before it goes on.

No brief by 7:30 am Pacific on a weekday means something's wrong. Message the Chief of Staff "status" and it tells you what ran, what didn't, and what's waiting on you.

After setup, when you approve items in the morning brief, the bot doing the send may ask you to confirm once more in its own chat. That prompt expires after about 10 minutes.

## What's in here

| File | What it is |
|---|---|
| [START-HERE.md](START-HERE.md) | The build instructions the bot follows. You don't need to read it. |
| [PROJECT.md](PROJECT.md) | The Grok Bot project: its name and description, the team memory every bot keeps, and the shared folder |
| [PROJECT_CHARTER.md](PROJECT_CHARTER.md) | The mission, the team, who owns what, the build gates and how results are measured |
| [agents/](agents/) | One charter per bot: its name, label and description, inputs, outputs, limits, schedule, and what "done" means |
| [client-context/](client-context/) | What the team already knows about ClearBlu, and what it may and may never say |
| [skills/](skills/) | The methods the agents use, in Grok Bot's skill format |
| [routines/](routines/) | Every scheduled job, word for word, with its exact Pacific Time schedule. Each one starts switched off. |
| [policies/](policies/) | What needs Larry's approval, and the compliance rules |
| [OPEN_QUESTIONS.md](OPEN_QUESTIONS.md) | Decisions still open |
| [REFERENCES.md](REFERENCES.md) | The repos and docs this team builds on |
| [manifest.json](manifest.json) | A machine-readable list of all of the above |

## What this repo never holds

- passwords, API keys or tokens;
- phone numbers, email addresses or a street address;
- contact lists, borrower or partner data;
- referral-fee or commission terms;
- account, location or calendar IDs.

Secrets go in through a secure secret card, Settings → Vault or Take over. Contact details go only in the workspace copies of the context files on the bot's computer.
