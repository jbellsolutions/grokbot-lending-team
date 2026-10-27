---
name: cold-outbound
description: Use to plan, write, load and monitor ClearBlu's cold email campaigns to referral partners (mortgage lenders and brokers first, then commercial brokers, then real estate agents and others) through ClearBlu's own Smartlead or Instantly account by API.
---

# Cold outbound for partner recruiting

Based on the Smartlead operating playbook in [ai-guy-go-to-market](https://github.com/jbellsolutions/ai-guy-go-to-market) (`sops/smartlead-operations.md`).

## Plan a campaign

One campaign per partner type, in Larry's order: mortgage lenders, mortgage brokers and loan officers first; commercial and investor-loan brokers next; real estate agents and other referral sources last. Use only ClearBlu's own account; never the build team's. Write down:
- **Who**: for example, mortgage loan officers in the states ClearBlu lends in, who get investor deals they can't place.
- **Why they'd care**: they can send ClearBlu the investor deals that don't fit their own programs, instead of losing them.
- **The offer to them**: "We are a direct real estate lender to real estate investors and developers providing short-term fix and flip, new construction and DSCR loans for 1-4 Unit and Multifamily Residential properties." Partner terms are covered on the intro call; no fee amounts in any email.
- **The ask**: a 15-minute intro call.

## Write the sequence

- 3–4 steps on days 0, 3, 7 and 14.
- Plain text, under 120 words for email 1 and under 90 for follow-ups.
- No links or images in email 1. The booking link only after they reply or in the last step.
- Personal first line from public facts (their market, their listings, their firm), never anything private.
- Larry's name and voice. Spell it ClearBlu. Postal address and opt-out in every email. Never mention owner-occupied loans or ClearBlu Home Loans.
- Run `lending-compliance` on every step.

## Load leads

1. Only lists Larry provided or approved.
2. Dedupe against GHL contacts, existing partners and Do Not Disturb.
3. Verify emails. Drop invalid and risky addresses.
4. Load in batches that match the daily cap.

## Sending health

- Separate cold domains with SPF, DKIM and DMARC, never ClearBlu's main domain. New inboxes warm until the tool's warmup reports them ready.
- About 30 per inbox per day.
- Pause the campaign when bounce passes 3% or complaints pass 0.1%. Tell Larry in the next brief.

## Smartlead (recommended)

- API key in a secure secret card named `SMARTLEAD_API_KEY`.
- Campaigns, sequences, leads, stats and replies through the Smartlead API.

## Instantly

- API key in a secure secret card named `INSTANTLY_API_KEY`.
- Campaigns, leads, analytics and replies through the Instantly API.
- Don't use the Instantly web app from the GrokBot computer. Its IP addresses get blocked.

## Replies

Pull new replies through the API in the morning check and again in the midday reply check. Don't set up a reply webhook: Smartlead's and Instantly's documented webhooks don't send the `Authorization` header that a Grok Bot routine needs.

## Daily check

Sent, opens if tracked, replies, positive replies, bounces, complaints, leads left in each campaign, and replies waiting more than four business hours.
