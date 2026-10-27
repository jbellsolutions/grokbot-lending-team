---
name: ghl-account-audit
description: Use to map a GoHighLevel account read-only (workflows, forms, pipelines, calendars, smart lists, fields, values) into a plain-English account map, find what's broken or duplicated, and recommend fixes. Run at setup and whenever the owner asks "what's live?".
---

# GHL account audit (read only)

This audit changes nothing. Use `ghl hub` reads, and a browser subagent only for screens the API doesn't show (smart lists, form-to-page wiring).

1. Confirm the location: `ghl hub whoami`. Stop if the name isn't the owner's business.
2. List each object type: workflows (name, status, trigger, last run), forms and surveys (name, status, submissions in the last 30 days, where embedded), pipelines and stages with open counts, calendars, smart lists, custom fields, custom values, tags in use.
3. Group them by job, using name prefixes where they exist (`AFF |`, `STL |`, `REACT |`, `OUT |`, `OPS |`) and their trigger otherwise: partner program, speed to lead, reactivation, outbound, internal, unknown.
4. For each job, answer:
   - What's live and what's in draft?
   - Do two or more forms or workflows do the same job? Which one is wired to the website, and which one got recent submissions?
   - Any workflow errors, contacts stuck in a step, or live workflows that haven't run in 30 days?
   - Any step waiting on something outside GHL, like A2P or a missing email domain?
5. Write `/workspace/lending-team/context/account-map.md`:
   - one table per job: name, status, what it does in one line, last activity;
   - a "Competing" section: same-job duplicates and which one to keep;
   - a "Broken" section;
   - "Top three fixes", each with what it fixes and the risk.
6. Include no contact names, emails or phone numbers. Counts only.
7. Hand the five-line summary to the Chief of Staff in the daily note.
