# NOVA TRADER V5.1 ENGINE HOTFIX

Main correction:
- Spot and Perp no longer share the same Market Quality hard gate.

Spot entry gates:
- Pump/Scalp strategy threshold
- Minimum liquidity
- Spot Market Quality floor (default 55)
- On-chain token security when available
- Route Quality
- Portfolio/Correlation limits
- Execution-cost gate

Perp entry gates:
- LONG/SHORT strategy threshold
- Open Interest
- Direction Edge
- Funding
- Volatility
- Primary perp source in SHADOW
- Route Quality
- Portfolio/Correlation limits
- Execution-cost gate

Other fixes:
- Security that has not been scanned is displayed as UNKNOWN, not 50.
- Unknown security is neutral in PAPER mode.
- SHADOW can still require a completed security scan.
- Dashboard wording now uses Market Quality instead of Risk for that score.

FAST remains:
Pump 68 / Scalp 70 / Long 68 / Short 68.
It is intended for quick PAPER testing, not final performance validation.
