# NOVA TRADER V6.1 — REALTIME PULSE SNIPER

PAPER / SHADOW ONLY. LIVE execution remains hard-locked.

## Why V6.1 exists
An 8-second REST scanner can miss a meme token that pumps and dumps in a few seconds.
V6.1 adds an optional event-driven WebSocket pulse engine while retaining the old scanner as fallback.

## Realtime Pulse logic
Rolling windows:
- 2 seconds: event-frequency burst
- 5 seconds: buy pressure, event count, SOL buy flow
- 10 seconds: unique buyers
- 30 seconds: baseline activity used to measure acceleration

A pulse candidate must pass:
- Pulse score
- Minimum events in 5 seconds
- Minimum buy pressure
- Minimum unique buyers
- Anti-chase price filter
- Existing Capital Shield liquidity and Market Quality
- Token security
- Execution-cost gate
- Portfolio/risk gates

The pulse signal NEVER bypasses Capital Shield.

## Data feed
Optional PumpPortal WebSocket support:
- One WebSocket connection only
- New-token / migration subscriptions
- Dynamic token-trade subscriptions
- Automatic reconnect
- Bounded subscription set
- Existing 8-second Sniper remains active if realtime data is unavailable

Environment:
`PUMPPORTAL_API_KEY`
`PUMPPORTAL_TRADE_STREAM_ENABLED=true`

The trade stream is deliberately OFF by default because the provider meters token-trade events.

## Exit behavior
Realtime entries use the same protected SNIPER_LONG execution:
- Fast Position Watcher
- Capital Shield stop
- Sniper scratch exit
- Early break-even
- Profit lock
- Momentum-fade exit
- Fast partial TP / final TP
- Daily/Global equity guards

## Security
Never commit API keys, wallet private keys, or admin keys to GitHub.
V6.1 does not contain wallet signing or live transaction submission.
