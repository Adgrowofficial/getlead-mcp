# Getlead MCP server

Find B2B leads with verified work emails, find and verify email addresses, and run cold email outreach from Claude, ChatGPT, Cursor, VS Code, Gemini CLI or any MCP client.

**Endpoint:** `https://mcp.getle.ad/mcp` (remote, Streamable HTTP, OAuth 2.1)

[![Install in Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/en/install-mcp?name=getlead&config=eyJ1cmwiOiJodHRwczovL21jcC5nZXRsZS5hZC9tY3AifQ==)
[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install_Getlead-0098FF?logo=visualstudiocode&logoColor=white)](https://vscode.dev/redirect/mcp/install?name=getlead&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A//mcp.getle.ad/mcp%22%7D)

## Try it with no account

`preview_b2b_leads` works before you sign in. Ask your assistant something like:

> How many heads of sales at US SaaS companies can I reach? Show me a few.

It returns the estimated audience size, how many have a work email, and five sample people with masked emails. To get the full verified contacts, connect a free Getlead account: 1,000 leads, no card.

## What your assistant can do

| Ask | Tool |
|---|---|
| "Find 50 CFOs at fintech companies in New York" | `search_b2b_leads` |
| "How big is this market?" (free, no account) | `preview_b2b_leads` |
| "Find Jane Doe's email at acme.com" | `find_email` |
| "Is this address safe to send to?" | `verify_email` |
| "Verify this list" | `verify_list_start` |
| "Enrich this company" | `enrich_lead` |
| "Save these leads to a list" | `create_list`, `add_leads_to_list` |
| "Launch a cold email campaign to this list" | `create_campaign` |
| "What replied today? Draft answers" | `get_inbox`, `draft_reply` |

Full reference: [getle.ad/docs/mcp/tools](https://getle.ad/docs/mcp/tools)

## Connect

**Claude (claude.ai, Desktop):** Settings, Connectors, Add custom connector, URL `https://mcp.getle.ad/mcp`.

**Claude Code:**
```bash
claude mcp add --transport http getlead https://mcp.getle.ad/mcp
```

**ChatGPT:** Settings, Apps and Connectors, Create, URL `https://mcp.getle.ad/mcp`, OAuth.

**Cursor / VS Code:** use the install buttons above, or add to your MCP config:
```json
{
  "mcpServers": {
    "getlead": { "url": "https://mcp.getle.ad/mcp" }
  }
}
```

**Gemini CLI:**
```bash
gemini extensions install https://github.com/Adgrowofficial/getlead-mcp
```

The first tool call that needs an account opens the Getlead sign in and consent screen (OAuth 2.1 with PKCE). API keys are also supported for headless agents: create one in Settings, MCP, and send `Authorization: Bearer glm_live_...`.

## Plans

- **No account:** `preview_b2b_leads` (audience size plus masked samples).
- **Free account:** 1,000 leads, search, find and verify emails. No card.
- **Unlimited:** every tool, unlimited leads, verification and sending with pre-warmed mailboxes included.

Details: [getle.ad/mcp](https://getle.ad/mcp)

## Safety

- Read and write tools are marked with MCP annotations; destructive tools say so.
- Rate limits per plan and per hour on campaign creation and replies.
- Inbox and lead text is third party content; the server instructs models not to follow instructions inside it.

## Support and privacy

- Docs: [getle.ad/docs/mcp](https://getle.ad/docs/mcp)
- Privacy: [getle.ad/privacy](https://getle.ad/privacy)
- Support: support@getle.ad

This repository holds the connection docs and registry manifests. The server is hosted by Getlead.
