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

## 2026-11-05 · 0.4.2
Addresses collected one at a time: ask for one, set it up, then "Add another" / "That's all." Known addresses (from memory on a re-run) are offered as choices.

## 2026-11-05 · 0.4.3
Browser prompt wording matches the buttons: click "Allow once", not "Always allow for this website".

## 2026-11-05 · 0.4.4
Setup warns that the browser prompt appears two or three times across a provider's mail, sign-in and account sites, and handles landing on a marketing page by signing in and retrying the settings link.

## 2026-11-05 · 0.4.5
Setup warns about the provider's new-browser verification code during sign-in and reads the code from the hub when it lands there.

## 2026-11-05 · 0.4.6
Browser steps: Claude operates the controls itself; any handoff names the exact on-screen controls in order, never a bare "let me know when it's done."

## 2026-11-05 · 0.4.7
Task creation: cron derived from hours so they match, Sonnet model, Gmail and Calendar only, task_id written back into the settings after creation.

## 2026-11-05 · 0.4.8
Connector trimming is best-effort: the task page may not allow removing extras. The skill's own restriction to Gmail and Calendar is the control.

## 2026-11-05 · 0.5.0
First live run. Items now carry sender, exact subject, account, time, gist, and a Gmail link that actually opens (rfc822msgid search, or hex thread id); the page shows sender · subject · account · when above the gist. First run ends with the page's link; onboarding hands over the link and says where the page lives.

## 2026-11-05 · 0.5.1
Links are the connector's viewUrl, never hand-built (the first run's links were fine). Sender shows the display name. "Open" renamed "View email" and de-emphasized; it read as the main action.

## 2026-11-05 · 0.5.2
Always flag and Never show now ask what to learn: from this sender, or about a phrase (the run supplies 2-3 keywords per item). Rules are stored as from:/about: and matched that way in triage.

## 2026-11-05 · 0.5.3
Onboarding warns about the one-time connector consent modal on the page's first button tap.

## 2026-11-05 · 0.5.4
Check now lives in the header next to the status; tapping anything shows a visible "Checking now… started" state with a pulsing dot until new data arrives, with a "still checking" message after five minutes.

## 2026-11-05 · 0.5.5
"Add" is "Add to calendar" (shows "Adding…" after the tap); the gist names the target calendar when several are live; an added item moves into Today/Tomorrow.

## 2026-11-05 · 0.5.6
Commitments get a Skip button (remembered, never re-proposed) and expire once their time has passed.

## 2026-11-05 · 0.5.7
Page split into Inbox and Calendar tabs with counts; remembers the last tab.

## 2026-11-05 · 0.5.8
The page is now a file in the repo (page/front-desk.html) that the run publishes verbatim, with the task id filled in, whenever its version comment changes. All of today's page changes (sender/subject header, View email, clarify chips, checking state, Add to calendar, Skip, tabs) are in it.

## 2026-11-05 · 0.5.9
Headline is the page name and date with a plain-English sentence under it; counts stay on the tabs.

## 2026-11-05 · 0.6.0
Calendar tab: overlap summary line at the top, overlaps counted as pairs, past events dimmed. Learned rules moved to the Inbox tab; the Saved note sits under the status line.

## 2026-11-05 · 0.6.1
Inbox cards restructured for scanning: sender and time on top, subject under it, the ask in bold before the context, a due-date tag. Run supplies `ask` and `due` per item.

## 2026-11-05 · 0.6.2
Header fits a phone: date is its own small element next to the title, status row is a grid (dot, text, button) so Check now stays on the line, today's weekday is dropped from the checked time.
