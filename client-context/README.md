# ClearBlu starting context

Two files hold what the build team already knows about ClearBlu, so Larry isn't asked again:

- [owner.md](owner.md): the business, what's already built in GoHighLevel, and the questions still open (marked **ASK**).
- [program-facts.md](program-facts.md): what the team may say, the exact links, and what it must never say.

Setup copies both to `/workspace/lending-team/context/`. The `getting-started` skill confirms them with Larry and fills in each **ASK**. After that, the workspace copies are the ones the team uses, and Larry approves any change to the program facts.

Never add phone numbers, email addresses, a street address, contact lists, borrower details, fee terms, passwords or keys here. Those go only in the workspace copies, or nowhere at all. `.gitignore` blocks a `CLIENT-CONTEXT.md` file for anything private.
