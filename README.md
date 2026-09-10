# NOVA TRADER V5.6.1 — WATCHER CADENCE FIX

Small operational hotfix for V5.6.

Fixes:
- Forces critical `position_watch_interval_sec` to 4 seconds on startup even if an older DB value (8s) survived the deployment.
- Forces `sniper_scan_interval_sec` to 8 seconds.
- Fast Position Watcher heartbeat now updates even when there are no open positions.
- Dashboard shows `IDLE — no open positions` instead of a misleading stale `last ... ago` value when the portfolio is empty.
- User trading/risk settings are preserved; only operational scan cadence is migrated.

PAPER / SHADOW only. LIVE remains locked.
