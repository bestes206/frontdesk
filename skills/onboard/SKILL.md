---
name: onboard
description: The guided onboarding conversation a new reader runs on their own Claude account after installing the app and connecting Gmail and Calendar. Collects their accounts, what counts as urgent (with real examples pulled from their inbox and confirmed), the main calendar, and hours; writes the settings block; and hands back the scheduled-task prompt. Use when someone pastes the front desk onboarding prompt or says "set up my front desk".
---

# Onboarding conversation

You are setting up the front desk for the person you're talking to. Plain words, one question at a time, and show them real examples from their own inbox before asking them to decide anything. Nothing here sends email or changes a calendar. It ends with a settings block and the task prompt.

## 1. Check the connections

Search their Gmail for the newest message and list today's calendar. If either fails, stop and tell them which connector to connect (Settings → Connectors → Gmail, Google Calendar) and to come back.

Tell them which Gmail you're connected to. That's the hub.

## 2. Their other mailboxes

Ask: "Which other email accounts do you check? List every address, work and personal." For each one, ask what to call it on the page (a short label like `Work` or `Personal`).

Then search the hub for the label `Frontdesk/Forwarded`. For each address they named, check whether forwarded mail from it is already arriving. For any that isn't, show them the forwarding steps for that provider (Gmail: Settings → Forwarding; Yahoo: needs Mail Plus; a work Microsoft 365 account: try an inbox rule, and if it bounces, their IT has to allow it) and tell them it's fine to finish forwarding later; the page will just say that account isn't connected yet.

## 3. What urgent means to them

Ask in this order. After each answer, search the hub and show 3 to 5 real matching messages (sender, subject, date), and ask "Are these the kind?" Keep what they confirm; drop what they reject.
1. "Who are the people whose email always needs a same-day answer?" Names or addresses. These become VIPs.
2. "What words in a subject line mean 'drop everything'?" Pull recent subjects containing those words and confirm.
3. "Think of the last two or three things you were glad you caught in time. What were they?" Find them. These are the `must_catch` examples.
4. "What shows up every day that you never need to see?" Pull examples and confirm. These become ignores.

Write down specifics (addresses, domains, exact words), not categories.

## 4. Calendars

List every calendar visible to the hub. Ask:
1. "Which one is your main calendar, the one new appointments should go on?" Mark it `main`.
2. "Which of these should the page show?" Include work and family.
3. "Are there calendars that aren't here?" (Outlook, a kids' team app, a school.) Explain the published-link option and that those refresh slowly, so they're shown for the day but never flagged as changed.

## 5. Hours and readers

Ask what hours and days it should check, and who else will read the page.

## 6. Write it back

Show them the finished settings block as plain language first ("I'll watch these 4 accounts, flag anything from these 6 people, hide these 3 senders, add appointments to your Work calendar, and check hourly 7am to 7pm Monday to Saturday"). Then produce the JSON settings block and the full task prompt: one line, `Read https://raw.githubusercontent.com/bestes206/frontdesk/main/skills/daily-brief/SKILL.md and follow it exactly as this run's instructions.`, then `## Settings` and the JSON. If you can create a scheduled task from here, create it: hourly during their hours, Gmail and Google Calendar as the only connectors, phone notifications on, and run it once. If you can't, tell them exactly where to paste the prompt to create it (claude.ai/code/routines, New task), and what to set: hourly, their hours, Gmail and Calendar only, notifications on.

Finish by telling them what the first page will look like and that tapping Handled, Always flag, or Never show is how they teach it.
