# Scheduled task: front desk check

One cloud scheduled task on the person's own Claude account. The whole job is in the task's prompt.

**Schedule:** hourly during working hours, e.g. `CRON_TZ=America/Los_Angeles 0 7-19 * * 1-6`. Hourly is the platform floor.

**Model:** Sonnet-class.

**Connectors:** Gmail and Google Calendar only. Remove every other connector.

**Notifications:** push on. The run's final line is the notification text; the skill writes `Checked, nothing new.` on quiet runs so nothing fires.

**Repositories:** none, if the platform allows a task without one. Otherwise attach this repo read-only.

**Prompt:** `Read https://raw.githubusercontent.com/bestes206/frontdesk/main/skills/daily-brief/SKILL.md and follow it exactly as this run's instructions.` then `## Settings` and the filled-in JSON from `config/settings.example.json`. The repo is public and holds no personal data; every run reads the latest skill, so a push to `main` updates every install on its next run without anyone touching the task.

**Updating:** edit the skill here and push to `main`. Only a settings change needs the task edited on the person's account. Log it in `docs/tuning-log.md`, bump the version.

**Manual run:** fire once after setup and after every change; open the page and check it against the inbox.
