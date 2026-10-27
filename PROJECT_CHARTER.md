# Project Charter: ClearBlu Lending Team

**Project:** ClearBlu Lending Team (see [PROJECT.md](PROJECT.md)) · **Owner:** Larry L. Gilmore, Managing Director, ClearBlu Capital Group Inc. · **Time zone:** Pacific · **Runs on:** Grok Bot, GoHighLevel and the [GHL Super Hub](https://github.com/jbellsolutions/ghl-super-hub)

## 1. Mission

ClearBlu Capital Group is "a direct real estate lender to real estate investors and developers providing short-term fix and flip, new construction and DSCR loans for 1-4 Unit and Multifamily Residential properties" (Larry, 2026-10-13).

The team grows that business through three channels: referral partners, past clients and new borrower leads. Larry runs it from his phone. The agents do the repeatable work. Larry keeps every decision that carries money, liability or a relationship.

Success is more funded investor loans, with each one traced back to the channel that brought it. Larry gets there by approving drafts, taking calls and closing loans, not by operating software.

## 2. Who it serves

- **Larry.** He takes the partner and borrower calls, makes every credit decision and talks to the team through the Chief of Staff.
- **Larry's assistant**, if he has one. They take the call tasks and reply tasks the agents create.
- **Referral partners, in this order** (from the 2026-10-09 call with Larry):
  1. Mortgage lenders and mortgage brokers, including loan officers with investor deals they can't place.
  2. Commercial and investor-loan brokers.
  3. Real estate agents, builders, developers, title companies and other referral sources.
- **Borrowers.** Real estate investors and developers borrowing for non-owner-occupied 1–4 unit and multifamily residential property: fix and flip, renovation, new construction and DSCR.

Not in scope: owner-occupied home loans and ClearBlu Home Loans. The agents never market them, and they send any such question to Larry (Larry, 2026-10-13).

## 3. Operating principles

1. **GoHighLevel does the instant work. Agents do the judgement.** Speed to Lead, instant replies, form routing and drip steps stay as GHL workflows, because they run in seconds and cost nothing per run. Agents read what happened, draft the messages that need a person's touch, spot what's broken and ask Larry.
2. **One voice to Larry.** Only the Chief of Staff messages Larry unasked. Every other agent writes a daily note, and the Chief of Staff turns the notes into one morning brief.
3. **Never silent.** Larry's last agents went quiet without warning. The morning brief arrives every weekday, even when nothing changed. It names any routine that didn't write its note, including the midday reply checks, which each leave a "ran" line even when there were no replies. If the brief itself doesn't arrive by 7:30 am Pacific, Larry sends the Chief of Staff "status".
4. **Files, not wake-ups.** Agents hand work to each other through files in `/workspace/lending-team/`. One agent sends another a handoff message only to deliver an approved action or a hot item. Waking another agent to ask a one-line question is the biggest single waste of usage, so it isn't done.
5. **Nothing external without Larry's yes.** Every send, every new or changed live workflow and every change to a partner's status waits for his approval. See [policies/APPROVALS.md](policies/APPROVALS.md). The one exception: an unsubscribe is honored at once.
6. **The quick app comes first.** Most of Larry's leads finish the 30-second quick app with little back-and-forth, so every borrower message offers it. A call is the fallback, never the demand.
7. **Build additively.** Never delete anything in GHL. New things start in Draft. Old things get renamed with a `ZZ-ARCHIVE |` prefix and stay put.
8. **Sub-account only, own seat.** The agents use their own GHL staff user and a Private Integration token created inside the ClearBlu sub-account. Larry resells GHL at the agency level, so an agency-level key would expose his other clients' accounts. It is never used. Secrets go in only through a secure secret card, Settings → Vault, or a hidden prompt Larry fills in with Take over.
9. **Lean on usage.** Each routine runs once a day, plus one midday reply check per lane. When nothing changed, a routine writes "no change" and stops.
10. **Stop at the quick app.** The agents bring a lead to a complete handoff brief. Pricing, the term sheet, processing and closing belong to Larry's team.

## 4. The team

| Bot | Label | Job in one line | Joins when |
|---|---|---|---|
| [Chief of Staff](agents/01-chief-of-staff.md) | ClearBlu · Larry's point of contact | Pinned. Morning brief, approvals, routing, Friday scorecard, results baseline | Setup |
| [GHL Operator](agents/02-ghl-operator.md) | ClearBlu · GoHighLevel | The only agent that changes GHL structure. Health check, account map, builds | Setup |
| [Affiliate Manager](agents/03-affiliate-manager.md) | ClearBlu · Referral partners | Runs the partner program: onboarding, check-ins, reactivation, replies, referral tracking | Setup |
| [Borrower Desk](agents/05-borrower-desk.md) | ClearBlu · Borrowers | Works what Speed to Lead leaves behind, reactivation replies and past-client care | Gate B |
| [Partner Recruiter](agents/04-partner-recruiter.md) | ClearBlu · Broker outreach | Runs broker cold email from ClearBlu's own sending account | Gate C |
| [Intent Scout](agents/90-reserved-intent-scout.md) | — | Reserved. Not built | A separate decision |

```
                     Larry (phone)
                          │
                   Chief of Staff  ◄── reads /workspace/lending-team/daily/<date>/
      ┌──────────────┬────┴─────────┬──────────────────┐
 GHL Operator   Affiliate Manager   Borrower Desk   Partner Recruiter
 (structure)    (partner records)   (borrower       (cold email account,
                                     records)        new partner prospects)
      └──────────────┴── ClearBlu sub-account in GoHighLevel ──┘
```

## 5. Who owns what

Each thing has exactly one writer. Everyone else reads it, or sends a request to its owner.

| Thing | Sole writer | Everyone else |
|---|---|---|
| GHL structure: workflows, forms, pipelines, stages, custom fields and values, smart lists, calendars, sites | GHL Operator | Request it in `requests/ghl/` |
| Partner contacts, partner notes and tasks, partner-pipeline opportunities, `aff:` and `src:` tags | Affiliate Manager | Read only |
| Borrower leads and past clients: notes, tasks, `bor:` tags, opportunities in "ClearBlu Home & Commercial Lending Leads" up to the quick-app stage | Borrower Desk | Read only |
| New partner prospects from cold email, at the first stage of the partner pipeline, with `src:outbound` | Partner Recruiter | Affiliate Manager takes over from there |
| Cold email campaigns, lists and sending settings | Partner Recruiter, once ClearBlu has its own account | Nobody else touches it |
| `daily/<date>/<agent>.md` | That agent | Chief of Staff reads |
| `daily/<date>/brief.md`, `approved/`, `context/standing-approvals.md`, `context/baseline.md`, `context/team-memory.md` | Chief of Staff | Read only |
| `context/account-map.md` | GHL Operator | Read only |
| `context/program-facts.md` | Chief of Staff, only with Larry's yes | Read only |
| Opportunity stages from the quick-app stage onward | Larry's team | Agents watch and report |

Until the Borrower Desk joins, the Affiliate Manager hands a partner's referred borrower straight to Larry as a hot item.

## 6. What it does, how Larry uses it, how it's measured

| Area | What it does | How Larry uses it | How it's measured |
|---|---|---|---|
| Morning brief | Every weekday by 7:30 am Pacific: what needs his yes, numbers since the last brief, what's broken, today's calls, and any routine that didn't run |  Read it. Reply "approve 1, 3", "skip 2" or "edit 4: …" | Arrives every weekday. Items waiting more than one business day |
| Partner program | Welcomes new partners, checks in on a cadence, wakes up quiet ones, triages replies, tracks every referral to funded | Approve the day's drafts. Take the intro calls and cover terms there | Active partners, referrals a month by partner type and source, days to first referral, quiet partners brought back |
| Borrower follow-through | Follows up leads who didn't finish the quick app, works reactivation replies, keeps past clients close | Approve drafts. Take the calls. Own everything from the quick app on | Quick app completion rate, calls booked, reactivation replies, repeat and referred borrowers |
| Broker outreach | Runs broker cold email from ClearBlu's own sending, works the replies, books intro calls | Approve the copy once per campaign. Take the intro calls | Deliverability, positive reply rate, intro calls booked, brokers signed |
| GoHighLevel | Keeps workflows, forms and lists working, fixes errors, builds what Larry describes | Ask in plain English: "make a smart list of brokers who sent a deal this year" | Open workflow errors, new leads with no first touch, one live form per purpose |
| Friday scorecard | One screen: each channel's funnel from first touch to funded, against the baseline, plus wins, stalls and one focus | Read it. Pick next week's focus | Arrives every Friday |

## 7. Build order: gates, not dates

The team grows one gate at a time. Each gate opens when its conditions are true, not on a date.

**Setup (Gate A): get control.** Chief of Staff, GHL Operator, Affiliate Manager.
- The GHL Operator maps the ClearBlu sub-account read-only: what's live, what's draft, what's broken, and the exact names of every pipeline and stage.
- The Chief of Staff records the results baseline (section 10).
- The Affiliate Manager takes over the partner pipelines and the replies to the Oct 14 partner invite.
- The morning brief starts.

**Gate B: the Borrower Desk.** Opens when both are true:
- Every Gate A routine has run five weekdays in a row with no failed run and no unapproved send.
- Larry says "start the borrower desk".

The Borrower Desk works only on what Speed to Lead and the reactivation workflow leave behind. It never repeats a first touch that a workflow already sent.

**Gate C: the Partner Recruiter.** Opens when all three are true:
- ClearBlu has its own cold email account (Smartlead or Instantly) with its own sending domains and warmed inboxes.
- The build team has handed over the broker campaign, or Larry has approved a new one.
- Larry says "start broker outreach".

Until then, the broker campaign runs on the build team's warmed inboxes, outside this Grok account. Interested brokers arrive in GHL as partner applicants, and the Affiliate Manager works them. See question 9 in [OPEN_QUESTIONS.md](OPEN_QUESTIONS.md).

**Later, each a separate decision:** Intent Scout, a partner newsletter, authority content, a fuller dashboard.

Add an agent only when the one before it has run five clean weekdays and the weekly usage meter has room.

## 8. Daily rhythm (weekdays, Pacific Time)

| Time | Who | What |
|---|---|---|
| 6:07 am | GHL Operator | Health check: workflow errors, stuck contacts, new leads with no first touch |
| 6:23 am | Affiliate Manager | Partner sweep: stage proposals, today's touch queue (40 max), drafts, overnight replies |
| 6:41 am | Partner Recruiter (Gate C) | Campaign stats, overnight replies, sending health |
| 6:53 am | Borrower Desk (Gate B) | Unfinished quick apps, reactivation replies, past-client touches due |
| 7:12 am | Chief of Staff | Reads every note and sends Larry the morning brief, every weekday |
| 12:37 pm | Affiliate Manager | Partner reply check |
| 12:41 pm | Partner Recruiter (Gate C) | Outbound reply check |
| 12:53 pm | Borrower Desk (Gate B) | Borrower reply check |
| Fri 3:17 pm | Chief of Staff | Weekly scorecard |
| 1st of month, 8:37 am | Affiliate Manager | Partner portfolio review |

## 9. Usage budget

Grok Bot usage resets weekly. Watch **Weekly usage** in the account menu. Premium can run Gate A alone. Super and Ultra have room for the full team.

- Gate A: four scheduled runs a weekday. Full team: eight.
- Each run reads, writes one short note and stops. Only the Chief of Staff's routines message Larry.
- If usage runs short before the reset, pause in this order: Borrower Desk routines, Partner Recruiter routines, the monthly review. The morning brief and the Affiliate Manager's daily loop stay on longest. The Chief of Staff names any paused routine in the brief, so a pause never looks like silence.
- Every routine first checks its switch in `context/routines-on.md`.

## 10. Measuring results

Larry judges the team on results, so every number traces back to its source.

- **Baseline.** Before any routine is switched on, the Chief of Staff writes `context/baseline.md`. The GHL Operator reads it out of GHL, read-only: open opportunities by stage in each pipeline, partners by stage, referrals received in the last 90 days, and new leads and quick apps in the last 30 days. Each number is dated. A number GHL can't give is written as "unknown", never estimated.
- **Attribution.** Every partner carries a `src:` tag (outbound, website, referral, event, owner). Every referred borrower carries the referring partner on the record. The scorecard counts each channel separately: partners, past clients, Meta ad leads, broker outreach.
- **Funnel stages are counted separately:** contacted → replied → interested → signed → first referral → quick app → term sheet → funded. Agents count the stages they own. Larry's team's stages are read from GHL, never inferred.
- A stage with no data reads "no data", not zero. A ratio with no denominator is left blank.

## 11. Out of scope

- Underwriting, pricing, term sheets, loan processing and closing.
- Owner-occupied home loans and anything for ClearBlu Home Loans.
- Collecting financial documents, bank statements, credit details or Social Security numbers. Those go through Larry's own secure application, never chat or email with an agent.
- Stating, negotiating or paying referral fees. Agents track a referral to "fee pending" and stop.
- Moving money, or changing billing, payment, phone number or A2P settings.

## 12. Definition of done for setup

- Every Gate A bot exists, with its name, label and description set from its charter, its team memory saved, and its skills enabled.
- The ClearBlu Lending Team project (or sidebar section) holds every team bot.
- GHL is connected through the agents' own seat and a sub-account token, `ghl hub doctor` passes, and `ghl hub whoami` shows the ClearBlu location.
- Larry has added the Ask first rules in Auto-review.
- The account map is written, every pipeline and stage name in it is real, and Larry has read the summary.
- The baseline is written.
- Every Gate A routine exists, passed one test run that wrote nothing outside the team, and was switched on only after Larry said yes.
- The first morning brief has arrived.
