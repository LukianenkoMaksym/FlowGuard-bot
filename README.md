# FlowGuard — Sports Odds Monitoring Bot

Automated multi-source odds movement monitor with Telegram alerts.
Built solo as a portfolio project for parsing & automation work.

## What it does

- Tracks odds movements across **every bookmaker** supplying odds for a match
  (bookmakers are discovered dynamically per match — no hardcoded list)
- Detects **drops, rises, and spike-and-revert** patterns on 1X2 and Over/Under markets
- Monitors money-flow signals (SMART EXCAPPER / SMART MONEY)
- Sends formatted Telegram alerts, including an odds-movement timeline
  ("how the odds moved", 5+ time/odds slices with direction arrows)
- **Self-tuning alert threshold**: adjusts from the win rate of the last
  60 settled signals (bounded, max 1 change per day)
- Persists all state in PostgreSQL — survives restarts without losing context
  (match bindings, signal history, goal context, watchlists)

## Stack

- TypeScript / Node.js
- PostgreSQL (persistent state)
- Telegram Bot API (alerts + control commands)
- Vitest — 600+ automated tests
- Hosted on Replit

## Highlights

- 600+ tests, strict TypeScript, clean diffs
- Multi-bookmaker detection keyed strictly by market + line
- Cooldown and deduplication logic (per match + signal type)
- Diagnostics and control via Telegram commands
- Atomic state persistence — no data loss on container restarts

## License

All rights reserved. See [LICENSE](LICENSE).
