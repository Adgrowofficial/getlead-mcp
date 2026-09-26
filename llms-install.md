# Installing the Getlead MCP server

Getlead is a remote MCP server. Nothing needs to be built or run locally.

1. Add a remote (Streamable HTTP) server named `getlead` with the URL `https://mcp.getle.ad/mcp`.
2. No API key is needed to start: `preview_b2b_leads` works without an account.
3. When a tool asks for authorization, the client opens Getlead's OAuth consent page. The user signs in or creates a free account (1,000 leads, no card).
4. For clients without OAuth, the user creates an API key at https://getle.ad/settings/mcp and the client sends `Authorization: Bearer <key>`.

Example config:

```json
{
  "mcpServers": {
    "getlead": { "url": "https://mcp.getle.ad/mcp" }
  }
}
```
