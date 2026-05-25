# Trading Bot

An autonomous paper trading agent powered by Claude Code that runs five scheduled workflows daily (pre-market research, market-open execution, midday scan, end-of-day summary, and Friday weekly review), places real orders on Alpaca, and commits all state to Git as markdown files.

**Local smoke test:** copy `env.template` to `.env`, fill in your Alpaca paper credentials, then run `bash scripts/alpaca.sh account` — valid JSON means the setup is working.

**Cloud routine setup:** see `trading_bot_setup_guide.md` Part 7 and `trading_bot_addendum.md` A1 for creating the five Claude Code routines, cron schedules (ET timezone), and required environment variables.
