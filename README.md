# NOVA TRADER V6.5 — SELECTIVE ENTRY ROUTER

PAPER / SHADOW ONLY. LIVE execution remains hard-locked.

V6.5 addresses a practical testing problem: if every near-miss signal is rejected, NOVA cannot collect enough forward trades to learn which strategies actually have edge.

## FINAL GATE status
Every Best Signal now shows:
- READY TO ENTER — strict gates pass.
- CONTROLLED ENTRY — PAPER-only strong near-miss, entered at reduced risk.
- BLOCKED — exact reason is displayed.

## Controlled PAPER Entry
The router may soften only two SPOT filters:
- Capital-Shield market-quality floor: down to 62 for a strong signal.
- Capital-Shield liquidity floor: down to $35k for a strong signal.

A controlled entry also requires:
- SCALP_LONG or PUMP_LONG only.
- Signal >= normal threshold + 2.
- Buy pressure >= 55%.
- 5-minute momentum between roughly -2% and +12%.
- No more than 2 controlled entries per hour.
- Reduced risk multiplier (0.50 on top of the existing Governor/Portfolio risk controls).

The following are NEVER bypassed:
- Kill / stop state.
- Stale data.
- Edge Governor pause.
- Token-security rejection / SHADOW requirements.
- Extreme move protection.
- Route quality.
- Portfolio/correlation guard.
- Execution-cost limit.
- Position / cooldown limits.
- Daily, global-equity and Survival guards.

SHADOW remains strict: Controlled Entry is PAPER-only.

## Why this is safer than simply lowering all thresholds
V6.5 creates a small exploration channel for strong near-misses while preserving the hard safety stack. It should produce enough paper trades to measure expectancy without turning the bot into an indiscriminate buyer.

Profit is not guaranteed. The goal is to discover positive edge from forward data while keeping losses bounded.
