# Cloud Routine Prompts

Each file in this directory is a complete, standalone prompt to paste verbatim into a Claude Code cloud routine. Do not paraphrase — the env-var check block and commit-and-push step are load-bearing.

| File | Cron (ET) | Description |
|------|-----------|-------------|
| pre-market.md | `0 6 * * 1-5` | Pre-market research, writes RESEARCH-LOG.md |
| market-open.md | `35 9 * * 1-5` | Executes planned trades, places stops |
| midday.md | `0 12 * * 1-5` | Cuts losers, tightens stops on winners |
| daily-summary.md | `5 16 * * 1-5` | EOD snapshot, always sends summary |
| weekly-review.md | `15 16 * * 5` | Friday stats, letter grade, strategy updates |

See trading_bot_addendum.md A1 for timezone and scheduling details.
See trading_bot_setup_guide.md Part 7 for routine creation walkthrough.
