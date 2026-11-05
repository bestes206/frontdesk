---
name: setup
description: Installs the front desk on a person's own Claude account. Walks through picking the hub Gmail, forwarding the other mailboxes into it, hub filters, calendar sharing, the Microsoft 365 step-zero test, the three settings questions, and creating the hourly scheduled task with phone notifications. Use when someone says "set up frontdesk", "install the front desk", or "run the setup".
---

# Setup runbook

Everything lives on the person's own accounts. The maintainer never holds their mail. In order; stop and report when a step fails. Budget about two hours with the person.

## Step 0. Prove it on the maintainer's own account first

Run the front desk on the maintainer's accounts for a few days: forwarding in, hourly task, page updates, push notification, an `Add` tap creating an event. Fix the skill until it's boring.

## Step 1. Create the hub

The person creates a new Gmail just for the front desk (their own account, their own password; the maintainer never holds it). Everything forwards into it and it's the only account Claude reads, so their real accounts stay untouched and turning it all off is one deletion. New accounts spam-filter forwarded mail for a few days; the hourly run reads spam too, so nothing is lost. Then add it to the Gmail app on their phone so the page's Open links land in it.

## Step 2. Connect Claude

On their Claude account (Pro or higher; scheduled tasks need a paid plan), connect the Gmail and Google Calendar connectors to the hub. Confirm Claude can search the hub and list today's calendar. Install the Claude app on their phone with notifications on.

## Step 3. Forward the other mailboxes in

Each Gmail: Settings → Forwarding → add the hub → confirmation code arrives in the hub → confirm → "Forward a copy and keep Gmail's copy."

Outlook.com (personal Microsoft account): Settings → Mail → Forwarding → enter the hub, keep a copy. Free. The Microsoft 365 connector does not support personal accounts, so forwarding is the only path.

Yahoo: forwarding needs Yahoo Mail Plus (about $5/month). Their call; if no, leave it out.

The app someone reads mail in (Outlook, Apple Mail, the Gmail app) is irrelevant; the account's provider sets the path.

Any work Microsoft 365 mailbox: try an inbox rule or mailbox forwarding to the hub and send a test. A bounce about external forwarding means the tenant blocks it. Then try the Claude Microsoft 365 connector; if it asks for an administrator, it needs their IT. If both fail, email IT once with the exact ask and launch without that mailbox.

## Step 4. Hub filters (maintainer tests only)

A fresh hub needs no filters: the hourly run searches spam too. Only when the hub is an inbox someone actually reads (a maintainer testing on their own account) add one filter per forwarded account: `to:(the-forwarded-address)` → Skip the Inbox, label `Frontdesk/Forwarded`.

## Step 5. Calendars

Share each of their real calendars with the hub account: see all event details for most, make changes to events for the one marked `main`, since that's where `Add` puts events. Outlook and family calendars that can't be shared: subscribe the hub's Google Calendar to their published ICS link and mark them `feed`.

## Step 6. Three questions

With their inbox open:
1. "Who always needs a same-day answer?" → `vip`.
2. "What shows up every day that you never need to see?" → `ignore`.
3. "What hours and days should it check?" → `hours`.

Show them the page buttons: Open, Handled, Add, Always flag, Never show.

## Step 7. Create the task

Build the prompt from `tasks/daily-brief.md`. Create one cloud scheduled task on their account: hourly during their hours, a Sonnet-class model, Gmail and Calendar as its only connectors, phone notifications on. Fire it once by hand, open the page together, and check it against their inbox.

## Step 8. First two weeks

Tell them: open the page before you open your mail apps, and tap Handled, Always flag, or Never show when it gets something wrong. Weekly 15-minute review: read the page's footer together, move learned VIPs and ignores into settings, fix the prompt, log it in `docs/tuning-log.md`. Check usage after 48 hours; move up a plan only if runs hit limits. Gate: `evals/gate.md`.
