# Lending Business Team for GrokBot

A ready-made team of GrokBot agents for running a business-purpose real-estate lending company.

The team runs on GoHighLevel and does five jobs:

- runs your referral partner and affiliate program;
- recruits new partners through cold email (Smartlead or Instantly);
- follows up with every borrower lead and past client;
- keeps your GoHighLevel account clean and working;
- gives you one morning brief and one weekly scorecard.

You stay in charge. Nothing goes out to a partner, a borrower or a prospect until you say yes. No agent touches loan processing, rates, approvals or referral-fee terms.

## Setup

1. **Create a new GrokBot.** Use a new bot for this, not one you already use for something else. Name it **Chief of Staff**.
2. **Give it this repo.** Paste this message into the new bot:

   ```
   Set yourself up from this repo: https://github.com/jbellsolutions/grokbot-lending-team
   Read START-HERE.md first and follow it step by step. Ask me before anything goes live.
   ```

3. **You're done.** The bot reads the repo and builds the team. It sets up the skills and the routines, with every routine paused. Then it asks you a short list of setup questions, one at a time, and turns each routine on only after you say yes.

Plan on about 30 minutes of your time on day one. Most of that is answering questions and connecting GoHighLevel.

## What's in here

| File | What it is |
|---|---|
| [START-HERE.md](START-HERE.md) | The build instructions the bot follows. You don't need to read it. |
| [PROJECT_CHARTER.md](PROJECT_CHARTER.md) | The mission, the team, what each part does for you and how it's measured |
| [agents/](agents/) | One charter per agent: role, scope, tools, routines, KPIs, handoffs, guardrails |
| [skills/](skills/) | The methods the agents use, in GrokBot's skill format |
| [routines/](routines/) | Every scheduled job, word for word. All of them ship paused. |
| [policies/](policies/) | What needs your approval, and the compliance rules |
| [OPEN_QUESTIONS.md](OPEN_QUESTIONS.md) | Decisions to make before or during setup |
| [REFERENCES.md](REFERENCES.md) | The repos this team builds on |
| [manifest.json](manifest.json) | A machine-readable list of all of the above |

## What this repo never holds

- passwords, API keys or tokens;
- contact lists, borrower or partner data;
- commission or referral-fee terms;
- account, location, form or calendar IDs.

All of those go in your own GrokBot, through its secure connection prompts, or in a private context file that you keep outside the repo. See [client-context/README.md](client-context/README.md).
