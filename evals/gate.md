# Two-week gate

Phase 1 passes when all of these hold for two straight weeks:

- [ ] The reader opened the page before their mail apps, and the page already had everything that mattered.
- [ ] Nothing that needed action (a deadline, a money decision, a signature, a schedule change, a direct ask) was ever buried under FYI or missed.
- [ ] No duplicates across runs; items cleared when tapped Handled or when a reply appeared in sent mail.
- [ ] The second reader says the page is worth checking once a day.
- [ ] Nothing was sent or changed except the page and Add-tapped calendar events. (Check the hub's sent mail and the calendar.)
- [ ] Usage stayed within the plan without manual intervention.

A failure is a skill change, logged in `docs/tuning-log.md`, with a version bump.

# Test cases

Write sample inboxes and expected triage in `evals/cases/<name>.md`: a list of messages (from, to-account, subject, one-line gist) and the expected buckets. Start with: an action item buried in an automated notification; a vendor pushing a date in a one-line email with a vague subject; a kid's practice moved to a different field; a newsletter that uses urgent-sounding words; the reader's own reply to someone that should clear a Needs item; a "let's do Thursday at 2" that collides with an existing event.
