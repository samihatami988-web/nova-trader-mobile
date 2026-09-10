# NOVA TRADER V5.3 — SMART PROFIT LOCK

This hotfix was created after a paper trade showed a winner round-tripping into a stop loss.

Core change:
- Exit decisions now use estimated NET close return after simulated execution friction.
- Strategy-specific profit protection prevents meaningful unrealized gains from freely turning into losses.

Profit-lock floors:

SCALP_LONG
- peak >= 1.5% -> protect ~ +0.35%
- peak >= 3%   -> protect ~ +1.25%
- peak >= 5%   -> protect ~ +2.5%
- peak >= 8%   -> dynamic floor, roughly peak - 2.5%

PUMP_LONG
- peak >= 2%  -> protect ~ +0.50%
- peak >= 4%  -> protect ~ +1.25%
- peak >= 8%  -> protect ~ +3%
- peak >= 12% -> protect ~ +5%
- peak >= 20% -> protect ~ +9%
- peak >= 30% -> dynamic wider trail

PERP_LONG / PERP_SHORT
- peak >= 1.5% -> protect ~ +0.30%
- peak >= 3%   -> protect ~ +1%
- peak >= 5%   -> protect ~ +2%
- peak >= 8%   -> protect ~ +4%

Strategy-specific partial take profits:
SCALP: 2% / 3.5% / 5%
PUMP: 6% / 12% / 20%
PERP: 2.5% / 5% / 8%

Important:
These are paper-engine rules, not guaranteed live fill outcomes. Fast gaps and execution friction can still produce a worse realized fill than a trigger.
