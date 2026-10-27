---
name: cold-outbound
description: Use to plan, write, load and monitor cold email campaigns to lending referral partners (realtors, brokers, builders, title companies) through Smartlead or Instantly by API.
---

# Cold outbound for partner recruiting

Based on the Smartlead operating playbook in [ai-guy-go-to-market](https://github.com/jbellsolutions/ai-guy-go-to-market) (`sops/smartlead-operations.md`).

## Plan a campaign

One campaign per partner type. Write down:
- **Who**: for example, residential realtors in the states the owner lends in.
- **Why they'd care**: their investor clients need fast, flexible funding, and a lender who closes keeps their deals alive.
- **The offer to them**: a dependable lender to send investor deals to, and a partner program. No fee amounts.
- **The ask**: a 15-minute intro call.

## Write the sequence

- 3–4 steps on days 0, 3, 7 and 14.
- Plain text, under 120 words for email 1 and under 90 for follow-ups.
- No links or images in email 1. The booking link only after they reply or in the last step.
- Personal first line from public facts (their market, their listings, their firm), never anything private.
- The owner's name and voice. Postal address and opt-out in every email.
- Run `lending-compliance` on every step.

## Load leads

1. Only lists the owner provided or approved.
2. Dedupe against GHL contacts, existing partners and Do Not Disturb.
3. Verify emails. Drop invalid and risky addresses.
4. Load in batches that match the daily cap.

## Sending health

- Separate cold domains with SPF, DKIM and DMARC. Warm for two weeks or more.
- About 30 per inbox per day.
- Pause the campaign when bounce passes 3% or complaints pass 0.1%. Tell the owner in the next brief.

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
