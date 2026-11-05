# frontdesk

The front desk of the office: one assistant that reads every inbox and calendar it's given and keeps one page current: what needs you, what looks like a commitment, and what's on the calendar. It reads; it does not act, except when you tap Add.

Everything runs on the person's own Claude account and their own Gmail. The maintainer never holds their mail.

First agent of the **office** ecosystem. Later agents (studio, foreman, scout, chief) get their own repos so each keeps its own narrow access.

## What it does

- Hourly, reads what's new across every forwarded account and the calendars.
- Updates the Front Desk page: needs you (with a link to the message), commitments with an Add button, today and tomorrow across all calendars, FYI.
- Pushes a phone notification only when something needs the reader. Quiet hour, no push.
- Taps teach it: Handled, Always flag, Never show. Add creates the calendar event.

## Layout

- `skills/daily-brief/` — the job, and the source of the task prompt
- `skills/onboard/` — the conversation a new reader runs on their own account; the guide points at it
- `skills/setup/` — the maintainer's runbook (step zero, the hard cases)
- `docs/guide.md` — the reader-facing guide, shared as an artifact
- `tasks/daily-brief.md` — how the task is created and updated
- `config/settings.example.json` — the settings block template
- `evals/gate.md` — the two-week gate
- `docs/tuning-log.md` — what changed and why
- `docs/alternatives/` — the email-thread version, in case a reader prefers email

## Distribution

The repo is public and holds no personal data. Both the onboarding prompt and every hourly run read the latest skill straight from `main`, so a push updates every install on its next run. Nobody but the maintainer needs GitHub.

## Iterating

Edit the skill → push to `main` → log it → bump `version`. Settings changes are the only edits made on a person's own task.
