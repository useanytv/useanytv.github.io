# AnyTV service status

`status.json` is the one file the AnyTV apps read to know whether our services are healthy. It is served by GitHub Pages at https://useanytv.github.io/status.json.

## When something is wrong

Edit `status.json` on github.com (pencil icon), change the three values and commit. The apps pick it up within a few minutes.

```json
{ "state": "degraded", "since": "2026-11-12T14:30:00Z", "id": "2026-11-12-sync" }
```

- `state`: `ok` (no banner), `degraded` (some services are slow) or `outage` (some services are down).
- `since`: when it started, in UTC.
- `id`: a short name for this incident. Use a new one for every incident, so people who closed an earlier banner see the new one.

## When it is over

Set `state` back to `ok` and commit.

The apps never show text from this file. Each state has its own wording inside the app.
