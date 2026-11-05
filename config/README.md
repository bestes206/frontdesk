# settings

`settings.example.json` is the template for the settings block at the end of the task prompt. Fill it in per person. Real settings never get committed here.

| Key | Meaning |
| --- | --- |
| `hub` | The Gmail the person owns and Claude is connected to. Everything else forwards here. |
| `readers` | Names used to tag items when more than one person reads the page. |
| `accounts` | Every mailbox feeding the hub, with the short label shown on the page. |
| `calendars` | Calendars to read: `live` (shared Google) or `feed` (ICS, refreshes slowly). Exactly one is `main`: where `Add` puts events. |
| `hours` | Working hours, days, timezone. |
| `vip` | Senders or domains that always need a same-day answer. |
| `ignore` | Senders, domains, or subjects dropped before triage. |

VIPs and ignores learned from page taps show in the page footer until the weekly review moves them here.
