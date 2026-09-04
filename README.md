# EscapeBot for Cursor

Public Cursor plugin for [EscapeBot](https://escape-bot.com). It connects Cursor to the hosted research MCP. **This repository contains no EscapeBot application source.** The server runs at `https://api.escape-bot.com/mcp`.

Research only. EscapeBot does not place trades.

## Install

1. Install **EscapeBot** from the Cursor Marketplace, or add this MCP URL in Cursor Settings → MCP:

```json
{
  "mcpServers": {
    "escapebot": {
      "url": "https://api.escape-bot.com/mcp"
    }
  }
}
```

2. Sign in with an existing EscapeBot account when Cursor opens Connect (OAuth). Billing stays on escape-bot.com. The plugin does not collect payment.

3. Ask things like:
   - What is the Oracle score for NVDA and why?
   - What is EscapeBot fair value for AAPL?
   - Screen profitable large-caps with a high Oracle score

## Auth

Cursor discovers OAuth from the MCP host. No API keys belong in this repo.

Desktop Connect and [Cursor Cloud Agents](https://cursor.com/agents) are separate OAuth clients. Sign in on each surface you use.

## What is in this repo

| Path | Purpose |
| --- | --- |
| `.cursor-plugin/plugin.json` | Marketplace manifest |
| `mcp.json` | Hosted MCP URL |
| `skills/escapebot/SKILL.md` | How the agent should use EscapeBot tools |
| `assets/logo.png` | Plugin logo (same mark as escape-bot.com) |

## License

MIT
