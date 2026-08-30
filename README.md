# ligamxterminal — archived

This repository has been superseded by **[betmodel](https://github.com/jiajun-builds/betmodel)**,
which runs Liga MX alongside the Chinese Super League from one engine where a
league is configuration rather than a fork.

Nothing here is live. The workflows are disabled and the Cloudflare Worker that
dispatched them has been deleted.

## Where everything went

| here | in betmodel |
|---|---|
| `src/ligamx/` | `src/betmodel/`, league-agnostic |
| model and signal parameters | `leagues/ligamx.yml` |
| `data/MEX_*.csv` | `data/ligamx/` |
| `data/MEX_odds_capture_history.csv` | `data/ligamx/odds_capture_history.csv` |
| `data/dashboard/json/` | `public/legacy/ligamx/` |
| the GitHub Pages board | [myevbettracker](https://github.com/jiajun-builds/myevbettracker) |

The odds-capture history and the unpriced-observation log — the two irreplaceable
things here, since no provider sells opening lines retroactively and the proof
that a price was an *opening* price cannot be reconstructed after the fact — were
reconciled into betmodel before this repository was switched off, and the
reconciliation reports a zero delta in both directions.

Liga MX gained something in the move it never had here: a scheduled full refresh
that runs in CI. Its fixtures and xG come from a provider that refuses datacenter
IPs, so it used to require a manual run on a laptop; betmodel reaches it through
a residential proxy.

The full history of this repository is preserved inside betmodel: both trees were
merged with `--allow-unrelated-histories`, so its commits are reachable there.
