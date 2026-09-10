# NOVA TRADER V6.6 — LAUNCH SNIPER / FIRST-SECONDS ENGINE

PAPER / SHADOW platform, with LAUNCH_SNIPER deliberately restricted to PAPER.
LIVE execution remains hard-locked.

## Why Launch Sniper is separate
A newly created Pump.fun coin starts on a bonding curve and can trade immediately. It may not yet have the mature DEX liquidity/security metadata required by the normal SCALP/PUMP router.

Launch Sniper therefore uses an event-native behavioral risk model for the first seconds.

## First-Seconds flow
1. `subscribeNewToken` receives the creation event.
2. NOVA registers creator/ticker history and opens a short metered TokenTrade watch.
3. Rolling 1s/2s/5s windows measure:
   - trade frequency
   - independent buyers
   - Bayesian-smoothed buy pressure
   - SOL buy/sell flow
   - acceleration
   - market-cap movement
   - top-buyer concentration
4. Hard behavioral blocks:
   - creator sell
   - creator spam
   - repeated ticker spam
   - excessive single-wallet concentration
   - fading immediately after creation
   - late chase
5. Entry must pass twice inside ~1.6 seconds.
6. PAPER position is tiny during Edge Governor probation.
7. The same PumpPortal trade events drive the exit engine.

## Default launch gate
- Score >= 74
- >= 3 trades in 2 seconds
- >= 2 independent buyers in 2 seconds
- Smoothed buy pressure >= 68%
- >= 0.15 SOL buy flow in 2 seconds
- Largest buyer <= 65% of short-window buy flow
- Entry age <= 18 seconds
- Market-cap move must not already be an extreme chase

## Position sizing
- Maximum launch position is 0.50% of equity.
- Edge Governor still applies. In PROBATION the actual size is much smaller.
- One Launch position at a time.
- Maximum 4 launch entries/hour by default.
- No martingale.

## PAPER execution realism
The default first-seconds simulator assumes:
- Pump.fun bonding-curve fee: 1.25% per trade.
- Future PumpPortal Local API interface fee proxy: 0.50% per trade.
- Additional simulated slippage, impact and latency.

Because friction is large, tiny gross scalps are not treated as meaningful net profit.

## Event-driven exits
Launch exits can trigger on:
- Creator Sell
- Raw market-cap stop
- Flow reversal
- Scratch / no follow-through
- Net Capital Shield
- Early break-even
- Profit Lock
- Partial TPs
- First-seconds time exit

Default net TP ladder:
- +5%
- +10%
- +18%

These are PAPER model targets, not guaranteed live fills or returns.

## Important
First-seconds memecoin trading is extremely volatile. Event-driven software cannot guarantee a fixed loss cap because a token can gap, lose tradability, or reverse between observable trades.
