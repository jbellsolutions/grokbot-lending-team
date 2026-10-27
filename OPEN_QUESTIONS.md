# Open questions

The Chief of Staff asks Larry the day-to-day questions itself, from the **ASK** lines in `client-context/owner.md`. The questions below are decisions to make around the build.

Already answered by Larry, and built in:
- Direct borrower leads go into "ClearBlu Home & Commercial Lending Leads". Referral and broker affiliates keep their own pipelines (2026-10-13).
- Owner-occupied loans and ClearBlu Home Loans are out of this work (2026-10-13).
- Referral terms stay out of writing and are covered on the intro call (2026-10-13).
- Mortgage lenders and brokers come before real estate agents (2026-10-09).
- The company is spelled ClearBlu (2026-10-10).

## Before setup

1. **Separate Grok account?** Grok Bot gives each user account one shared computer, so every bot in that account can see the same files, browser sessions and logins. If Larry already uses Grok Bot for anything else, the cleanest setup is a separate Grok account for ClearBlu. The other option is to share the account and rely on the isolation guard in every routine.
2. **Plan size.** Grok Bot needs Premium or higher. On Premium, run Gate A only and watch **Weekly usage** before opening Gate B. Super and Ultra have room for the full team.
3. **GoHighLevel access.** Larry resells GHL at the agency level. The staff seat and the Private Integration token must be created inside the ClearBlu sub-account, not at the agency. Does his agency setup allow Private Integrations at the sub-account level?
4. **Referral fees and state rules.** Which partner types and states can legally be paid a referral fee for business-purpose loans? Larry confirms with counsel. The agents never discuss terms either way.

## Gate A (setup)

5. **Which partner form is live?** The GHL Operator's audit answers this. Larry confirms which one the website's partner page should use.
6. **Speed to Lead stage.** Which stage in "ClearBlu Home & Commercial Lending Leads" should a new Speed to Lead reply land in? This is still open with the build team ("Inbound Reply Router").
7. **Reactivation status.** Larry approved the reactivation copy on 2026-10-13 with his new sentence and paragraph spacing. Is it live, and at what daily pace? The audit checks. Larry confirms the pace.
8. **Signature.** Larry's email signature links ClearBlu Home Loans. Should the team's messages use a signature without that line?

## Gate C (broker outreach)

9. **ClearBlu's own sending.** The broker campaign runs on the build team's warmed inboxes. Three things are open:
   - Who sets up ClearBlu's own cold domains, inboxes and Smartlead or Instantly account?
   - When the build team hands the campaign over, it sends the list, the sequence and the last step sent.
   - Until then, interested brokers must reach GHL as partner applicants with `src:outbound`, so the Affiliate Manager can work them. Who creates them there?
10. **Smartlead or Instantly?** Smartlead is recommended. Either way, the account is ClearBlu's own.
11. **Standing approvals.** Should an interested broker get the booking-link reply automatically, or wait for Larry's yes each time?

## Gate B (borrower desk)

12. **Hot alerts.** Should a partner with a deal, or a borrower ready to talk, reach Larry right away, or only in the morning brief?
13. **Past clients.** Are funded loans in GHL with a funding date and loan type? Past-client care depends on them. If they aren't, the GHL Operator proposes how to add them.

## Any time

14. **Group intro call.** Monthly? Which day and time?
15. **Instant partner replies.** Partner replies are read each morning and at midday. Should the GHL Operator add a webhook so they reach the team at once? See the optional step at the end of START-HERE.
16. **Small business loans.** Larry's signature links a small business loan page. Is it part of what the team may mention, or does the team keep to real estate?

## Later, each a separate decision

17. **Intent Scout.** Social intent signals for borrower and partner leads (the reserved agent).
18. **Partner newsletter, authority content and a fuller dashboard.**
19. **Loan-processing helper.** Out of scope here on purpose. Any agent past the quick-app stage needs its own design, with a person in the loop at every step.
