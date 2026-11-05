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

## 2026-11-05 · 0.3.3
Onboarding now works out the provider behind each address (Gmail, Outlook.com, Yahoo, work Microsoft 365, other) rather than trusting the app name, and gives Outlook.com forwarding steps. Setup runbook adds the Outlook.com path.

## 2026-11-05 · 0.3.4
Added Check now to the page: it fires the hourly task on demand through the viewer's scheduled-tasks connector. The four taps fire it too, with a note, so Add and Handled land within minutes. Onboarding records the task id as `task_id`.

## 2026-11-05 · 0.3.5
The hub is now a new Gmail created for the front desk, not an existing account: real accounts stay untouched, one deletion turns it all off. Open links use authuser so they land in the hub even with several accounts signed in. Items clear via Handled, since the hub never sees the person's sent mail.

## 2026-11-05 · 0.4.0
Setup rewritten after the first live run: buttons everywhere (freeform only for addresses and a name); Claude does forwarding and calendar sharing in the browser when it can; one account at a time with a check; hub filters removed from the user path (the run reads spam); first page shown before tuning; VIPs and ignores proposed from their own top senders as tick lists; hours as presets.

## 2026-11-05 · 0.4.1
Setup handles the browser gracefully: enables it itself when it's just off, offers manual steps only when there's no browser (phone), explains the allow prompt and sign-in and how to bring the pane back, and falls back to steps if a site is blocked or declined.
