# Client context (private)

The repo is the same for every lending business. What's specific to one business stays out of it: what's already built in their GHL, their goals, their people and their open items. That goes in a private file called `CLIENT-CONTEXT.md`.

- Copy [CLIENT-CONTEXT.template.md](CLIENT-CONTEXT.template.md), fill it in and hand it to the new GrokBot during setup as an attachment. Don't commit it.
- Leave out passwords, keys, contact lists, borrower details and fee terms. The agents never need them.
- `.gitignore` already blocks `CLIENT-CONTEXT.md`.
