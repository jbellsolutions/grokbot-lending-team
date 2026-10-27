# Lending Business Team for GrokBot

A ready-made team of GrokBot agents for running a business-purpose real-estate lending company.

The team runs on GoHighLevel and does five jobs:

- runs your referral partner and affiliate program;
- recruits new partners through cold email (Smartlead or Instantly);
- follows up with every borrower lead and past client;
- keeps your GoHighLevel account clean and working;
- gives you one morning brief and one weekly scorecard.

You stay in charge. Nothing goes out to a partner, a borrower or a prospect until you say yes. No agent touches loan processing, rates, approvals or referral-fee terms.

## Before you start

- A Grok plan that includes Grok Bot (Premium or higher).
- The Grok Bot desktop app for the first session. After that, the phone app is enough.
- Admin access to your GoHighLevel sub-account.
- If you already use Grok Bot for something else, think about a separate Grok account for this team. All bots on one account share one computer, its files and its logins.

## Setup

1. **Create a new bot.** In Grok Bot, choose **New chat (+) → Create new Bot**. Use a new bot for this, not one you already use for something else.
2. **Give it this repo.** Paste this message into the new bot:

   ```
   Set yourself up from this repo: https://github.com/jbellsolutions/grokbot-lending-team
   Read START-HERE.md first and follow it step by step. Ask me before anything goes live.
   ```

3. **Answer its questions.** The bot builds the team: it saves the skills, creates the other bots, connects GoHighLevel, maps your account and sets up every routine switched off. It turns each routine on only after you say yes.

## What only you can do

The bot stops and walks you through each of these when it gets there:

- Rename the first bot **Chief of Staff** and pin it.
- Check your time zone in **Settings → Bot → Timezone**. Every routine runs on it.
- Add the approval rules in **Settings → General → Auto-review**. The bot gives you the exact lines.
- In GoHighLevel, add a staff user for the agents and create a Private Integration token.
- Paste that token once into a hidden prompt on the bot's computer, using **Take over**. It never goes in the chat.
- Save the agent user's GHL login in **Settings → Vault**, and type any two-factor code.
- Say yes to each routine before it goes on.

If the bot can't create the other bots itself, it gives you a message to paste into each new bot you create.

After setup, when you approve items in the morning brief, the bot doing the send may ask you to confirm once more in its own chat. That prompt expires after about 10 minutes.

## What's in here

| File | What it is |
|---|---|
| [START-HERE.md](START-HERE.md) | The build instructions the bot follows. You don't need to read it. |
| [PROJECT_CHARTER.md](PROJECT_CHARTER.md) | The mission, the team, what each part does for you and how it's measured |
| [agents/](agents/) | One charter per agent: role, scope, tools, routines, KPIs, handoffs, guardrails |
| [skills/](skills/) | The methods the agents use, in GrokBot's skill format |
| [routines/](routines/) | Every scheduled job, word for word. Each one starts switched off. |
| [policies/](policies/) | What needs your approval, and the compliance rules |
| [OPEN_QUESTIONS.md](OPEN_QUESTIONS.md) | Decisions to make before or during setup |
| [REFERENCES.md](REFERENCES.md) | The repos this team builds on |
| [manifest.json](manifest.json) | A machine-readable list of all of the above |

## What this repo never holds

- passwords, API keys or tokens;
- contact lists, borrower or partner data;
- commission or referral-fee terms;
- account, location, form or calendar IDs.

All of those go in your own GrokBot (a secure secret card, Settings → Vault or Take over), or in a private context file that you keep outside the repo. See [client-context/README.md](client-context/README.md).
