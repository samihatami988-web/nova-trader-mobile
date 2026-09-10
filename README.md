# NOVA TRADER V5.2 — POSITION PROTECTION HOTFIX

Critical fixes discovered during FAST paper testing:

1. Open Position Watcher
- Open spot positions are fetched independently of the discovery/candidate ranking.
- A token falling out of the scanner can no longer silently remove it from normal stop/trailing monitoring.
- Stale open-position prices generate a watchdog warning.

2. Daily Guard visibility
- Dashboard shows today's realized P&L and daily loss limit.
- Clearly shows ACTIVE vs BLOCKED.

3. Clean Paper Reset
- Dashboard adds RESET PAPER TEST with double confirmation.
- Resets paper equity, positions, trades, adaptive trade-feature history and execution-event history.
- Strategy/risk settings remain.
- Market snapshot research history remains.

4. UI wording
- `SIGNAL PASS` renamed to `SCORE PASS`.
- Passing the base score does not imply all final safety gates passed.

Important:
A configured stop is a trigger, not a guaranteed fill price. Gaps, stale quotes and simulated slippage can still make a realized exit worse than the stop trigger. V5.2 specifically fixes one major source of excessive stop deviation: losing price monitoring when a spot token leaves the scanner list.
