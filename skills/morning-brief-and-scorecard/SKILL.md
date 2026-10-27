---
name: morning-brief-and-scorecard
description: Use for the Chief of Staff's morning brief and Friday scorecard for Larry, and to turn his "approve 1, 3" replies into delivered actions.
---

# Morning brief and scorecard

## Morning brief

The brief goes out every weekday, even when nothing changed. Larry's last agents went silent, so silence is never the answer.

1. Read `/workspace/lending-team/context/routines-on.md` to know which notes to expect today.
2. Read today's notes in `/workspace/lending-team/daily/<date>/`: `ghl.md`, `affiliate.md`, `borrower.md`, `outbound.md`. An expected note that's missing or not dated today goes under **Didn't run**, by routine name.
3. Check the routines that run after the brief. Each switched-on midday reply check leaves a line like `Partner reply check · ran 12:37 · 3 replies` in its lane's note for the last weekday. On Mondays, check that last Friday's `scorecard.md` exists. On the first weekday after the 1st, check `affiliate-monthly.md`. Anything missing goes under **Didn't run**.
4. Save the brief to `daily/<date>/brief.md`, then send it.

Under 180 words, in this order:

```
ClearBlu · <weekday> <date>
Needs your yes
1. [agent]: [what, one line]
2. …
Since the last brief: [n] new leads · [n] quick apps · [n] partner replies · [n] referrals · [n] calls booked
Broken: [one line each, or "nothing"]
Didn't run: [routine names, or "all ran"]
Today: [time] [who], [one line of prep]
```

Group similar approvals, for example "12 broker check-ins (list on request)". Give the full list only if Larry asks.

If nothing needs Larry and nothing broke, send: "ClearBlu · <weekday>. Nothing needs you today. All [n] routines ran." followed by the "Since the last brief" line. Count from the last brief's time, so Monday's brief covers the weekend.

If the same routine misses two weekdays running, put it first in the brief, with the likely cause.

## "status"

When Larry sends "status", compare `context/routines-on.md` with today's notes and the last weekday's midday lines, and reply in a few lines: what ran, what didn't, and anything waiting on him. If the morning brief didn't go out today, say so first and send it now.

## Approvals

- Larry replies "approve 1, 3", "skip 2", "edit 4: …" or "approve all".
- Write each result to `approved/<date>.md`: `<n> · <agent> · <item id> · approved | skipped | edited: <his words> · <time>`.
- Send each agent its own approved items in one handoff message. Mark each item delivered, or undelivered with the reason.
- Anything not approved by the next morning goes into the next brief once, then drops off and is counted in the scorecard.

## Friday scorecard

One screen, saved to `daily/<date>/scorecard.md` and sent to Larry:
- **By channel**, this week and the four-week average, each compared with `context/baseline.md`:
  - partners: contacted, replied, signed, first referral, referrals;
  - Meta ad leads: new, quick app finished, handed to Larry;
  - reactivation: replies, calls booked;
  - past clients: touched, repeat loans, referrals;
  - broker outreach, once the Partner Recruiter has joined.
- **Larry's team's stages**, read from GHL and never inferred: term sheets, funded.
- **Health:** workflow errors, deliverability, approvals that waited, routines that didn't run.
- **Three wins, three stalls, one focus for next week.**

Use numbers from GHL and the cold email tool only. A number that isn't available reads "no data", never zero. A rate with no denominator is left blank. Don't estimate.
