# NOVA TRADER V6.0 — ALPHA CORE

PAPER / SHADOW ONLY. LIVE remains hard-locked.

V6.0 unifies:
- Micro-Pump Sniper
- Scalp LONG
- Pump LONG
- Perp LONG / SHORT
- Capital Shield
- Fast Position Watcher
- Adaptive Optimizer
- Portfolio Brain
- Execution Reality Engine
- Token Security
- Daily Guard
- Daily Profit Target Lock

## 10% Daily Target
Default daily target is 10% of start balance.

This is NOT a guaranteed minimum return and NOVA will never force weak trades just to hit the target.

Risk behavior:
- Below ~7% daily combined P&L: normal configured risk.
- Around +7%: new-trade risk is automatically reduced to 50%.
- At approximately +10.25% combined P&L: NOVA closes open paper positions to secure the day.
- Once >=10% is secured/realized: new entries are blocked for the rest of the current runtime/day target state.
- Reset Paper clears the target lock.
- No martingale / no averaging-down recovery logic is used.

## Risk Controls
- Maximum total open-risk budget: ~3% of starting capital.
- Strategy-specific Capital Shield stops.
- Global Equity Guard.
- Daily loss guard.
- Profit Lock / Early Break-even / Scratch Exit.
- Liquidity and market-quality floors.
- Sniper has smaller position risk than normal strategies.

## Dashboard
Still simple:
- Equity / P&L / Win rate / open positions
- NOVA Decision
- Daily Guard
- Daily Profit Target progress
- PAPER / SHADOW
- FAST / BALANCED / SAFE
- Risk / Stop / Max Positions / Leverage
- Best Signals
- Sniper Signals
- Engine Protection
- Recent Results

Important:
A strong trading engine is evaluated by expectancy, drawdown, profit factor, execution quality and robustness—not by promising a fixed daily return.
