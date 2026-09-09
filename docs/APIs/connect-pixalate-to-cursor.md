---
title: Connect Pixalate to Cursor
hidden: false
---
Cursor reads MCP servers from a JSON configuration file. Add Pixalate to it, reload, and sign in
through the browser when prompted.

## Configuration

Open Settings, then MCP, then Add new global MCP server. That opens `mcp.json`. Add the Pixalate
entry:

```json
{
  "mcpServers": {
    "pixalate-mcp": {
      "url": "https://mcp.pixalate.com/mcp"
    }
  }
}
```

Save the file. Cursor picks up the change and shows Pixalate in the MCP server list. The first
request opens your browser so you can sign in with your Pixalate account.

If you want Pixalate available in one project rather than everywhere, put the same entry in
`.cursor/mcp.json` inside that project instead.

## Check that it worked

Open the chat panel and ask:

> What Pixalate reports can I run?

If you get report names back, you are connected and entitled.

## If Cursor shows the server but no tools

Two different things look similar here. A red or failed indicator next to the server usually
means the connection or sign in did not complete, so try reconnecting. A green indicator with an
empty tool list means you are connected but your Pixalate account has not been enabled yet.
Contact your Pixalate account manager for the second one.

## Do not add a header or a key

Some MCP entries in other tools carry an `Authorization` header or an API key field. Pixalate
does not use one. If you add one, sign in will not start properly. The entry above is complete
as written.

## Common questions

**Should I use the install link or edit the config file?**

Either. The install link writes the same configuration for you. Edit the file directly if you keep your editor config in version control or want to see exactly what was added.
