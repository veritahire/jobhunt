# Use Job Hunt in other AI tools

Everything runs on one MCP server: **`https://veritahire.com/mcp`** (streamable HTTP, no auth, free).
Add it to your tool, then ask in plain words: *"Find registered nurse jobs within 25 miles of Houston,
TX that pay at least $40 an hour."*

For the full experience (résumé matching, fit ranking, daily alerts), also give your agent the skill in
[`skills/jobhunt/SKILL.md`](../skills/jobhunt/SKILL.md): agents that read Agent Skills load it from their
skills folder; for others, paste it into your project instructions (AGENTS.md, rules, or a system prompt).

## Claude Code

```
/plugin marketplace add veritahire/jobhunt
/plugin install jobhunt@veritahire
```

Or the server alone: `claude mcp add --transport http veritahire-jobs https://veritahire.com/mcp`

## Claude Desktop and claude.ai

Settings → Connectors → find **VeritaHire Jobs** in the directory, or add a custom connector with the URL
`https://veritahire.com/mcp`.

## Codex

In `~/.codex/config.toml`:

```toml
[mcp_servers.veritahire-jobs]
url = "https://veritahire.com/mcp"
```

## Cursor

In `~/.cursor/mcp.json` (or `.cursor/mcp.json` in a project):

```json
{
  "mcpServers": {
    "veritahire-jobs": { "url": "https://veritahire.com/mcp" }
  }
}
```

## VS Code (Copilot agent mode)

In `.vscode/mcp.json`:

```json
{
  "servers": {
    "veritahire-jobs": { "type": "http", "url": "https://veritahire.com/mcp" }
  }
}
```

## Gemini CLI

In `~/.gemini/settings.json`:

```json
{
  "mcpServers": {
    "veritahire-jobs": { "httpUrl": "https://veritahire.com/mcp" }
  }
}
```

## Any other MCP client

Server URL `https://veritahire.com/mcp`, transport streamable HTTP, no authentication. Tools:
`search_live_jobs`, `get_job`, `is_job_still_open`, `save_search`, `report_problem`, plus two for
employers (`benchmark_role`, `request_full_report`). Registry name: `com.veritahire/jobs`.
