# NOVA TRADER V7.1.3 — PROFIT CORE RESTORE

V7.1.3 keeps the version line moving forward while restoring the trading behavior that performed best in the user's V7.0 PAPER run.

## Locked trading core
- Entry score / strategy thresholds: V7.0.0
- PUMP / SCALP / SNIPER / LAUNCH / PERP strategy logic: V7.0.0
- Micro Profit / protective exit ordering: V7.0.0
- Candle Intelligence: MONITOR ONLY (no score overlay, no hard gate)

## Retained improvements
- Universal CEX + DEX universe
- BTC / ETH / majors / alts / memes
- Perp LONG + SHORT
- V7.1.1 connection-stability and independent Candle worker
- V7.1.2 Global Loss Guard, restricted to risk sizing + cooldown/circuit breaker only
- Existing PAPER/SHADOW database remains compatible
- LIVE execution remains hard-locked

Do not reset PAPER data and do not change DATABASE_URL during deployment.
