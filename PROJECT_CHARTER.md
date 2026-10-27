# Project Charter: Lending Business Team

## 1. Mission

Grow a business-purpose real-estate lending company through three channels: referral partners, past clients and new borrower leads. One owner runs it from a phone. The agents do the repeatable work, and the owner keeps every decision that carries money, liability or a relationship.

Success means more funded loans each month. The owner gets there by approving drafts, taking calls and closing loans, not by operating software.

## 2. Who this is for

- **The owner.** They run the business, take partner and borrower calls, make every credit decision and talk to the team from their phone.
- **The owner's assistant** (optional). They take the call tasks and reply tasks that the agents create.
- **Partners.** Realtors, mortgage brokers, builders, developers, title companies and other referral sources.
- **Borrowers.** Real-estate investors, who always borrow through a business entity: fix and flip, new construction, DSCR, multifamily, private and hard money.

## 3. Operating principles

1. **GoHighLevel does the instant work. Agents do the judgement.** Instant replies, speed-to-lead texts, form routing and drip steps stay as GHL workflows, because they run in seconds and cost nothing per run. Agents read what happened, draft the human-sounding messages, spot what's broken and ask the owner.
2. **One voice to the owner.** Only the Chief of Staff talks to the owner unasked. Every other agent writes its daily notes to a shared folder, and the Chief of Staff turns them into one morning message.
3. **Files, not wake-ups.** Agents hand work to each other through files in `/workspace/lending-team/`. They wake another agent only to deliver an approved action. One agent asking another a one-line question is the biggest single waste of usage, so it isn't done.
4. **Nothing external without a yes.** Every send, every new live workflow and every change to a partner's status waits for the owner's approval. See [policies/APPROVALS.md](policies/APPROVALS.md).
5. **Build additively.** Never delete anything in GHL. New things start in Draft. Old things get renamed with a `ZZ-ARCHIVE |` prefix and stay put.
6. **Seats, not logins.** Agents use their own GHL user and a scoped Private Integration token. They never use the owner's login. Secrets are entered only by the owner: in a secure secret card, in Settings → Vault, or at a hidden prompt with Take over.
7. **Lean on usage.** Eight scheduled runs a weekday at full build, four in phase 1. Every routine stays silent when nothing changed. Replies are read in each morning job and once at midday; a GHL webhook can make partner replies instant later.
8. **Stop at loan processing.** The agents bring a lead to a complete handoff brief. From the quick app onward, a person handles it.

## 4. The team

| Agent | Role in one line | Phase |
|---|---|---|
| [Chief of Staff](agents/01-chief-of-staff.md) | Pinned bot. The owner's single point of contact: morning brief, approvals, routing, weekly scorecard | 1 |
| [GHL Operator](agents/02-ghl-operator.md) | GoHighLevel super user. Owns the account's structure, runs health checks, builds what the owner asks for in plain English | 1 |
| [Affiliate Manager](agents/03-affiliate-manager.md) | Runs the partner lifecycle: onboarding, check-ins, reactivation, reply triage, referral tracking | 1 |
| [Partner Recruiter](agents/04-partner-recruiter.md) | Cold outbound to realtors, brokers and builders through Smartlead or Instantly; hands interested people to the Affiliate Manager | 2 |
| [Borrower Desk](agents/05-borrower-desk.md) | Speed-to-lead follow-through, database reactivation and past-client care; hands a complete brief to a person | 2 |
| [Intent Scout](agents/90-reserved-intent-scout.md) | Reserved. Social intent signals for borrower and partner leads | Later |

The owner pins the Chief of Staff and talks to it first. It routes each request to the right agent.

```
                   Owner (phone)
                        │
                 Chief of Staff  ◄── reads /workspace/lending-team/daily/*
      ┌───────────┬─────┴──────┬───────────────┐
 GHL Operator  Affiliate    Partner        Borrower
 (structure)   Manager      Recruiter      Desk
      └───────────┴── GoHighLevel (records, by lane) ──┘
```

## 5. Who owns what in GoHighLevel

Structure has one owner. Records have lane owners.

| Owner | Can create or change | Lane prefix and tags |
|---|---|---|
| GHL Operator | Workflows, forms, pipelines, custom fields, custom values, smart lists, calendars, sites | Any. It is the only agent that changes **structure**. |
| Affiliate Manager | Partner contacts, partner notes, tasks and opportunities in the partner pipelines | `AFF |`, `aff:` and `src:` tags |
| Partner Recruiter | New partner prospects from outbound, and "interested" handoffs | `OUT |`, `out:` tags |
| Borrower Desk | Lead and past-client notes, tasks and opportunity stages up to the human handoff | `STL |`, `REACT |`, `bor:` tags |
| Chief of Staff | Nothing in GHL. It reads only. | — |

Any agent that needs a structural change writes a request to `/workspace/lending-team/requests/ghl/`. The GHL Operator picks those up on its next run.

## 6. What it does for you, how you use it, how it's measured

| Area | What it does | How you use it | How it's measured |
|---|---|---|---|
| Morning brief | One message by 7:30 am: yesterday's numbers, what needs your yes, what's broken, today's calls | Read it, reply "approve 1, 3" or "skip 2" | Delivered every workday; items waiting more than one day |
| Partner program | Welcomes new partners, checks in on a schedule, wakes up quiet ones, triages replies, tracks every referral to Funded | Approve the day's drafts, take the calls it books | Active partners (a referral in the last 90 days), referrals per month, time to first referral, quiet partners reactivated |
| Partner recruiting | Runs cold email to realtors, brokers and builders, works the replies, books intro calls | Approve copy once per campaign, take intro calls | Deliverability, positive reply rate, intro calls booked, partners signed per week |
| Borrower follow-up | Chases leads who didn't finish the quick app, works reactivation replies, keeps in touch with past clients | Approve drafts, take the calls, own everything from the quick app on | Quick-app completion rate, calls booked, reactivation replies, repeat and referred borrowers |
| GoHighLevel | Keeps workflows, forms and lists working; fixes errors; builds what you describe | Ask in plain English: "make a smart list of partners who sent a deal this year" | Open workflow errors, first-touch time on new leads, one live form per purpose |
| Weekly scorecard | One page every Friday afternoon: the funnel from partner to funded loan, wins, stalls, next week's focus | Read it, pick one focus for next week | Delivered every Friday |

## 7. Phases

**Phase 1: get control (week 1).** Chief of Staff, GHL Operator, Affiliate Manager.
- The GHL Operator audits the account and writes a plain-English map of what's live, what's draft and what's broken.
- It settles which form is the live one for each purpose and wires the website's partner page to it.
- The Affiliate Manager takes over the existing partner list and pipeline and sends its first approved check-ins.
- The morning brief starts.

**Phase 2: grow (week 2 onward).** Partner Recruiter, Borrower Desk.
- Outbound picks up where the existing broker campaign stopped, through Smartlead or Instantly.
- Reactivation is switched back on at a pace the owner sets.
- The Borrower Desk starts past-client care.

**Phase 3: optional.** Intent Scout, a partner newsletter, authority content and a fuller KPI dashboard. Each is a separate decision. See [OPEN_QUESTIONS.md](OPEN_QUESTIONS.md).

Add an agent only once the one before it runs a full week without surprises and the weekly usage meter has room.

## 8. Daily rhythm (weekdays, in the owner's time zone)

| Time | Who | What |
|---|---|---|
| 6:07 | GHL Operator | Health check: errors, stuck contacts, new leads without a first touch |
| 6:23 | Affiliate Manager | Partner sweep: retag proposals, today's touch queue (40 max), personal drafts, overnight replies |
| 6:41 | Partner Recruiter (phase 2) | Outbound stats, overnight replies, list health |
| 6:53 | Borrower Desk (phase 2) | Unfinished quick apps, reactivation replies, past-client touches due |
| 7:12 | Chief of Staff | Reads all four notes and sends the owner one morning brief |
| 12:37 pm | Affiliate Manager | Partner reply check |
| 12:41 pm | Partner Recruiter (phase 2) | Outbound reply check |
| 12:53 pm | Borrower Desk (phase 2) | Borrower reply check |
| Fri 3:17 pm | Chief of Staff | Weekly scorecard |
| 1st of month 8:37 | Affiliate Manager | Partner portfolio review |

## 9. Usage budget

GrokBot usage resets weekly. On Premium, plan for phase 1 alone at first; Super and Ultra have larger weekly allowances. Watch **Weekly usage** in the account menu.

- Four scheduled runs a weekday in phase 1, eight at full build: one morning job per agent, the morning brief, and one midday reply check per lane. Each one reads, writes a short note and stops.
- The Chief of Staff's routines are the only ones that message the owner.
- No routine runs more than once a day, apart from each lane's midday reply check.
- If usage runs short before the weekly reset, pause in this order: Borrower Desk routines, Partner Recruiter routines, monthly review. The morning brief and the Affiliate Manager's daily loop stay on longest.
- Every routine first checks its switch in `context/routines-on.md`, then: "Lean run. If nothing changed, write 'no change' and stop."

## 10. Out of scope

- Underwriting, pricing, term sheets, loan processing and closing.
- Collecting financial documents, bank statements or Social Security numbers. Those go through the owner's secure portal, never chat or email with an agent.
- Stating, negotiating or paying referral fees. Agents track a referral to "Fee pending" and stop there.
- Trading, moving money, or changing payment or banking settings.

## 11. Definition of done for setup

- Every agent exists with its profile, skills and memory seeded.
- GHL is connected through the GHL Operator's own seat and token, and `ghl hub doctor` passes.
- The owner added the Ask first rules in Auto-review.
- The account map is written and the owner has read it.
- Every routine exists, ran once as a test that wrote nothing external, and is switched on only after the owner said yes.
- The first morning brief has arrived.
