---
name: escapebot
description: >-
  Use EscapeBot research tools (Oracle scores, quotes, valuation fair_value,
  analyst data, screener, earnings, news, filings, KPIs, ownership). Trigger
  when the user asks about EscapeBot, Oracle, fair value, or market research.
  Never place trades through EscapeBot.
---

# EscapeBot (research only)

Hosted MCP: `https://api.escape-bot.com/mcp`. Users sign in with an existing EscapeBot account. Do not invent prices or scores; call tools.

## Tool habits

- Oracle: `get_prediction` for the score; always follow with `get_oracle_decision_path` before stating Why.
- Valuation: use **`fair_value`** from `get_valuation` / `batch_valuation`. Served growth: `get_valuation_growth`.
- Quotes: `get_quotes`. Search: `search_symbols`.
- Analyst: `get_analyst_snapshot` first. Street 12-month targets are not stored; use ratings + `get_estimates` + `our_fair_value`.
- Funds: `get_etf_prediction`, `get_etf_holdings`, `get_etf_lookthrough`. Do not DCF the fund wrapper.
- Screener: `get_screener_filter_specs` before `run_screen`.
- Charts: `get_chart` (price, valuation_history, growth_paths) — show, don't tell.
- Errors: `{error, message, status_code}` — handle 401 / 402 / 403 / 429.

## Hard limits

- Research data only — **no order placement**
- Do not display pricing plans, start checkout, or link to subscribe
- 401 = not signed in; 402 = access exhausted; 403 = missing scope; 429 = rate limit
