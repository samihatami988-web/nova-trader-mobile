# NOVA Trader V7.2.3 — Free AI Mode

Hybrid PAPER/SHADOW trading system with two intelligence paths:

- Meme / Launch: ultra-fast event-driven path, no LLM dependency.
- Major Perpetuals: Hybrid Quant + Multi-Timeframe Candle Intelligence + Free Local Quant AI.
- OpenAI: optional accelerator. If API credits are unavailable, NOVA automatically falls back to FREE_LOCAL and stops repeating failed quota calls.

The Local Quant AI is deterministic software logic, not an external generative model. It combines NOVA's own long/short scores, MTF candle confidence, structure, funding/OI context, volatility and directional edge into LONG / SHORT / WAIT assessments.

Risk controls remain authoritative. Live execution remains hard-locked in this build.
