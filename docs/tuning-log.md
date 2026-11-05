# Tuning log

Dated entries, newest first. What was reported, what changed, which version.

## 2026-11-05 · 0.1.0
Initial scaffold from a Nov 5 planning session and a three-review pressure test (expert, end user, implementer). Not yet run.

## 2026-11-05 · 0.2.0
Cut back to the simplest version that solves the stated problem. Removed: config repos, GitHub on the person's side, git-committing learned rules, feedback emails, calendar-add command, onboarding interview (now three questions), `always_needs`. Kept: hourly checks that reply only when something new needs someone, numbered items with `#n` replies, commitments-and-conflicts line (read-only). Whole job now lives in the task prompt.

## 2026-11-05 · 0.3.0
Switched delivery from an email thread to a private page on the person's own Claude account, updated hourly, with phone push notifications when something needs them. Reason: everything must stay on accounts the person owns; a scheduled run can publish a page and push a notification with no sending and no approval. Added: Open links to the hub copy of each message, Add button that creates the calendar event on the next run, Handled / Always flag / Never show taps. Email-thread version kept in docs/alternatives.

## 2026-11-05 · 0.3.1
Added the reader-facing guide (docs/guide.md) and the onboarding conversation (skills/onboard) it points at: connections check, other mailboxes, urgent-with-real-examples interview, calendars with a main one, hours, settings written back. To be iterated on the maintainer's own accounts before anyone else sees it.

## 2026-11-05 · 0.3.2
Published the Module 0 page (Front Desk Setup artifact). Prompts now read the skills from the public repo's raw main URLs, so a push updates every install; the person never needs GitHub.
