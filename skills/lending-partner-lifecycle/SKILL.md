---
name: lending-partner-lifecycle
description: Use for the Affiliate Manager's daily partner loop and any question about a partner's stage, cadence or next touch in a lending referral program.
---

# Lending partner lifecycle

## Stages and tags

applied → onboarding → active → producing → quiet (45 days) → dormant (90) → dead (180) → reactivated

- `aff:applied`: submitted the sign-up form, not yet accepted.
- `aff:onboarding`: accepted by the owner. Welcome series and intro call offered.
- `aff:active`: onboarded, no referral yet.
- `aff:producing`: a real referral in GHL in the last 90 days.
- `aff:quiet` / `aff:dormant` / `aff:dead`: days since the last reply or referral, whichever is newer.
- `aff:reactivated`: came back from quiet, dormant or dead. It stays until their next referral moves them to producing.
- Source, set once: `src:outbound`, `src:website`, `src:referral`, `src:event`, `src:owner`.

## Cadence

| When | Touch |
|---|---|
| Days 0, 2, 5, 10 after acceptance | Welcome series: what we fund, how to send a deal, who to call, intro call invite |
| Every 14 days | Light touch: a short note, a deal we closed (no borrower details), a question |
| Every 30 days | Useful offer: a program update, a market note, a co-marketing piece, the group call invite |
| 60 days silent | Personal check-in: a call task for the owner with three lines of context, or a short personal email in the owner's voice |
| A referral moves | Thank-you or status note to the partner, with no fee amounts |

Tier 2 brokers get the same rhythm. Add a one-on-one call offer at onboarding and a "how's your pipeline?" question every 30 days.

## Daily loop

1. Read the partner pipeline and yesterday's activity.
2. List the stage changes the rules call for. In week 1, propose them. Later, apply them only for tags that trigger no outbound workflow, and log each one.
3. Build today's queue, 40 at most, in this order: producing, recently replied, onboarding, active, quiet, dormant.
4. Draft each touch: under 90 words, one ask, in the owner's voice. Run `lending-compliance` on every draft.
5. Write the queue as numbered items, one line each, to `daily/<date>/affiliate.md`.
6. After approval, send only the approved items, inside quiet hours, and log them.

## A good touch

- Says something useful or asks one easy question.
- Mentions the partner's own world: their market, their recent listing, their deal type.
- Never pushes for a referral twice in a row.
- Never states fees, rates, approvals or income.
