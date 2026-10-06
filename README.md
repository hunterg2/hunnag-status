# hunnag-status

Which of hunnaG's Discord bots are running, since when, and in how many servers, plus a month
of hourly uptime. The machine that runs the bots rewrites both files every five minutes and
force-pushes them as the single commit of this repository, so the history never grows. The hub
at https://hunnag.pages.dev reads them to show a live badge and a 30-day strip on each bot.

`status.json`:

```json
{
  "updated": "2026-10-06T05:00:00Z",
  "bots": { "ticketbot": { "online": true, "since": "2026-10-05T19:43:00Z", "servers": 3 } }
}
```

`history.json`: per bot, one character per hour, oldest first, at most 720 (30 days). The last
character is the hour in progress, named by `lastHour`. `1` online in every sample that hour,
`0` offline in every sample, `~` a mix, `?` no samples (the machine was off).

```json
{
  "updated": "2026-10-06T12:05:00Z",
  "lastHour": "2026-10-06T12:00:00Z",
  "hours": 720,
  "bots": { "ticketbot": "1111111111~1" }
}
```
