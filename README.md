# GroundedKit Marketing Stats Checker (MCP server)

Free, read-only MCP server that checks widely repeated marketing and influencer-marketing statistics against their primary sources.

- **MCP endpoint:** `https://groundedkit.com/mcp` (Streamable HTTP, no auth, no API key)
- **Docs:** https://groundedkit.com/agents/
- **Official MCP Registry name:** `com.groundedkit/marketing-stats`

## Tools

| Tool | What it does |
|---|---|
| `check_stat(text)` | Paste a stat; get the verdict (verified, misquoted, outdated, unsourced), confidence, primary source, what the source actually says, and safe wording. |
| `search_claims(query, verdict?, limit?)` | Search the claim registry. |
| `get_claim(id)` | Full record for one claim (slug or claim URL). |
| `list_verdicts()` | Verdict definitions. |

## Install

```json
{"mcpServers": {"groundedkit": {"type": "http", "url": "https://groundedkit.com/mcp"}}}
```

Claude Code: `claude mcp add --transport http groundedkit https://groundedkit.com/mcp`

## Data

`claims.json` / `claims.csv` (50 claims at this snapshot; the live server is updated more often). Schema in `schema.json`. Also available at https://groundedkit.com/api/claims.json.

## Files

- `worker.js`: the Cloudflare Worker that serves `/mcp` (data embedded at build time).
- `server.json`: MCP Registry metadata.

## License

Code: MIT. Data: CC BY 4.0 (attribute "GroundedKit, groundedkit.com").

Report a wrong stat: hello@groundedkit.com

A project of Organic Media Buying, LLC.
