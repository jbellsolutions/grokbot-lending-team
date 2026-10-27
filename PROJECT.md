# GrokBot Project: ClearBlu Lending Team

This is the project the team lives in. It has three parts, and the Chief of Staff sets them up in Steps 1 to 3 of [START-HERE.md](START-HERE.md):

1. **The project itself**: its name and description, below.
2. **Team memory**: the facts about Larry and ClearBlu that every bot on the team keeps.
3. **The shared folder**: `/workspace/lending-team/`, where the bots hand work to each other.

## 1. The project

If the Grok Bot app offers **Projects**, create one with exactly this name and description, and add every bot on the team to it as it's created. If it doesn't, put every team bot in a sidebar section with the same name: right-click the bot, then **Move to new section** (or **Move to** once the section exists).

```
---
name: ClearBlu Lending Team
description: >-
  ClearBlu Capital Group's lending team for Larry Gilmore. Chief of Staff
  (pinned) leads GHL Operator, Affiliate Manager, Borrower Desk and Partner
  Recruiter. Grows investor and commercial loans through referral partners,
  past clients and new leads in GoHighLevel. Nothing goes out without Larry's
  yes. Shared files in /workspace/lending-team.
---
```

## 2. Team memory

Every bot saves these lines to its memory when it's created, word for word. One fact per line, dated with the day it was learned. When Larry corrects one, the Chief of Staff updates the line here in `/workspace/lending-team/context/team-memory.md` and tells each bot the new line.

```
# About the user
- (2026-10-27) The owner is Larry L. Gilmore, CMB, AMP, Managing Director of ClearBlu Capital Group Inc. Call him Larry.
- (2026-10-27) Larry works in Pacific Time (America/Los_Angeles). Every routine time is Pacific.
- (2026-10-10) The company is spelled "ClearBlu", never "Clear Blue". Fix it anywhere you see it.
- (2026-10-13) What ClearBlu does, in Larry's words: "We are a direct real estate lender to real estate investors and developers providing short-term fix and flip, new construction and DSCR loans for 1-4 Unit and Multifamily Residential properties."
- (2026-10-13) The team works only on investor and commercial loans, which are non-owner-occupied. ClearBlu Home Loans makes owner-occupied home loans in select states, and that is not part of this team's work. Never market it. Route any owner-occupied question to Larry.
- (2026-10-10) The quick app at https://clearblu.applywithustoday.com/ takes about 30 seconds. When a borrower finishes it, ClearBlu can have a term sheet ready before the first call. Offer it in every borrower message, as an option and never a demand.
- (2026-10-10) Most of Larry's leads finish the quick app with little or no back-and-forth, so the quick app is the main borrower call to action. A call is the fallback.
- (2026-10-13) Direct borrower leads belong in Larry's existing pipeline, "ClearBlu Home & Commercial Lending Leads". Referral partners and broker affiliates have their own dedicated pipelines.
- (2026-10-09) Partner priority: mortgage lenders and mortgage brokers first, ahead of real estate agents.
- (2026-10-13) Referral terms are never put in writing. Larry covers them on the intro call. Agents never state or hint at an amount.
- (2026-10-27) Larry has used GoHighLevel for seven years and resells it under his own brand. The team works only in the ClearBlu sub-account, never at the agency level.
- (2026-10-27) Larry's last agents went silent without warning. The morning brief arrives every weekday, even when nothing changed, and it names any routine that didn't run.
- (2026-10-27) No brief by 7:30 am Pacific on a weekday means something's wrong. Larry messages the Chief of Staff "status" and gets what ran, what didn't, and what's waiting on him.
- (2026-10-27) Larry approves every message to a partner, borrower or prospect before it goes out.
```

## 3. The shared folder

```
/workspace/lending-team/
  repo/                 this repo, read only
  context/              owner.md, program-facts.md, team-memory.md, account-map.md, baseline.md, routines-on.md
  daily/<date>/         one note per agent per day: ghl.md, affiliate.md, borrower.md, outbound.md, brief.md
  requests/ghl/         structural change requests for the GHL Operator
  approved/<date>.md    what Larry approved, as he approved it
  log/                  setup.md and one file per month of what each agent did
  ghl-super-hub/        the GoHighLevel tool
```

Each file in `daily/`, `requests/` and `approved/` has one owner who writes it. Every other bot only reads it. The table in [PROJECT_CHARTER.md](PROJECT_CHARTER.md#5-who-owns-what) says who owns what.

## Who's on the team

| Bot | Label | Joins | Charter |
|---|---|---|---|
| Chief of Staff | ClearBlu · Larry's point of contact | Setup | [agents/01-chief-of-staff.md](agents/01-chief-of-staff.md) |
| GHL Operator | ClearBlu · GoHighLevel | Setup | [agents/02-ghl-operator.md](agents/02-ghl-operator.md) |
| Affiliate Manager | ClearBlu · Referral partners | Setup | [agents/03-affiliate-manager.md](agents/03-affiliate-manager.md) |
| Borrower Desk | ClearBlu · Borrowers | When Larry says "start the borrower desk" | [agents/05-borrower-desk.md](agents/05-borrower-desk.md) |
| Partner Recruiter | ClearBlu · Broker outreach | When ClearBlu has its own cold email account | [agents/04-partner-recruiter.md](agents/04-partner-recruiter.md) |
