# NOVA TRADER V5.6 — MICRO-PUMP SNIPER

PAPER / SHADOW ONLY. LIVE remains hard-locked.

New SNIPER_LONG engine:
- Independent ~8-second discovery scanner for latest Solana boosts/profiles.
- Dedicated sniper score: buy pressure, volume acceleration, early momentum, transaction activity, liquidity, LP/MC ratio, market age and boost.
- Anti-chase gate: avoids entering after the 5-minute move is already too extended.
- Strong Capital Shield requirements remain.
- On-chain security scan on the strongest sniper candidates.
- Only one sniper position by default.
- Sniper position risk multiplier defaults to 0.50 of normal configured risk.
- Existing ~4-second open-position watcher manages sniper exits.

Default sniper gates:
- Score >= 78 (FAST profile uses 72; BALANCED 78; SAFE 84)
- Buy pressure >= 60%
- Volume acceleration >= 52
- 5m move approximately 0.30% to 12%
- Market age <= 360 minutes
- Capital Shield liquidity and market-quality floors still apply

Sniper exits use estimated NET return after execution friction:
- Internal loss cap target ~1.0%
- Fast scratch: ~1.5 minutes and about -0.35% if no follow-through
- Early break-even begins around +0.65%
- Profit lock begins around +0.80%
- Partial TP around +1.0% and +1.8%
- Final sniper TP around +3.0%
- Max hold ~5 minutes
- Immediate momentum-fade exit when buy pressure/momentum collapses

Important:
No scanner or stop can guarantee profit or a fixed exit on a fast meme-token gap. V5.6 combines smaller sniper sizing, stronger liquidity filters, fast monitoring and quick profit protection to reduce tail risk.
