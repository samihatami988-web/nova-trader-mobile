# NOVA Trader V7.2.2 — OpenAI AI Brain + Diagnostic Recovery

V7.2.2 adds a real OpenAI Responses API analysis layer for major perpetual markets. Meme/launch execution remains event-driven and does not wait for an LLM. AI output is bounded confirmation only; deterministic Risk Guard, Daily Loss Guard, exposure controls, liquidity/security filters, and LIVE hard-lock remain authoritative.

## Required Northflank secret

- `OPENAI_API_KEY` — your OpenAI API key (server-side secret only; never put it in GitHub or index.html)

## Optional environment variables

- `NOVA_OPENAI_AI_ENABLED=true`
- `NOVA_OPENAI_MODEL=gpt-5.6-terra`
- `NOVA_OPENAI_AI_REFRESH_SEC=75`
- `NOVA_OPENAI_AI_CACHE_SEC=180`
- `NOVA_OPENAI_AI_TOP_N=4`
- `NOVA_OPENAI_AI_TIMEOUT_SEC=12`
- `NOVA_OPENAI_AI_MAX_ADJUST=5`
- `NOVA_OPENAI_AI_MIN_CONF=68`
- `NOVA_OPENAI_AI_BLOCK_CONF=88`

## Verification

- `/health` should report `version: 7.2.1`, `openai_ai_enabled: true`, and `openai_ai_configured: true`.
- Authenticated `/api/ai-analysis` exposes AI state, model, counters, and recent structured major-perp assessments.
- Dashboard contains an **OpenAI AI Brain + Diagnostic Recovery** card.

## Safety

PAPER/SHADOW only. Live execution remains hard-locked. AI analysis does not guarantee profit and is designed to fail closed/fallback to the deterministic engine when unavailable.
