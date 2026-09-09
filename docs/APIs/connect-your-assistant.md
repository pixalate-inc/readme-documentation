---
title: Connect your assistant
hidden: false
---
Pixalate works with any assistant that supports remote MCP servers over Streamable HTTP. The
setup is the same everywhere: one address, no key, and a browser sign in the first time.

```
https://mcp.pixalate.com/mcp
```

Name the server `pixalate-mcp`. There is nothing else to configure. If a client asks for an API
key, a token, or an `Authorization` header, leave those fields empty: Pixalate signs you in
through the browser, and a credential left in the configuration stops that from starting.

The steps for each client below come from that vendor's own documentation, linked in every row.

## Clients with a full guide

These have their own page with the exact menu path.

| Client | Guide |
|---|---|
| Claude, web and desktop | [Connect Pixalate to Claude](/docs/connect-pixalate-to-claude) |
| ChatGPT | [Connect Pixalate to ChatGPT](/docs/connect-pixalate-to-chatgpt) |
| Cursor | [Connect Pixalate to Cursor](/docs/connect-pixalate-to-cursor) |

## Every client

### Added in the app itself

No configuration file. You add Pixalate from inside the app and sign in.

| Client | How you add it |
|---|---|
| [ChatGPT](https://developers.openai.com/api/docs/guides/developer-mode)<br>[our guide](/docs/connect-pixalate-to-chatgpt) | Turn on developer mode in settings, add a custom app, and paste the URL. |
| [Claude, web and desktop](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp)<br>[our guide](/docs/connect-pixalate-to-claude)<br>[Claude Desktop config file (mcp-remote bridge)](https://github.com/geelen/mcp-remote) | Add a custom connector in settings and paste the URL. On desktop you can also add the server to your config file through the `mcp-remote` bridge. |
| [Gemini app](https://support.google.com/gemini/answer/17209137) | Open Connected Apps in settings, add a custom app, and paste the URL. |
| [Microsoft Copilot Studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/mcp-add-existing-server-to-agent) | Add an MCP tool to one of your agents and paste the URL. |
| [Mistral Le Chat](https://docs.mistral.ai/le-chat/knowledge-integrations/connectors/mcp-connectors) | Add a custom MCP connector in settings and paste the URL. Your admin enables it. |
| [Notion AI](https://www.notion.com/help/mcp-connections-for-custom-agents) | Add a custom MCP in settings and paste the URL. Business or Enterprise, and your admin enables it. |
| [Perplexity](https://www.perplexity.ai/help-center/en/articles/13915507-adding-custom-remote-connectors) | Add a custom connector in settings and paste the URL. Enterprise, and your admin enables it. |
| [Raycast](https://manual.raycast.com/ai/model-context-protocol) | Install an MCP server in settings and paste the URL. Needs Pro. |
| [Replit Agent](https://docs.replit.com/build/connect-via-mcp) | Add an MCP server in settings and paste the URL. |
| [Zapier](https://help.zapier.com/hc/en-us/articles/38777069364109-Connect-remote-MCP-servers-to-Zapier-using-MCP-Client) | Add an MCP Client connection and paste the URL. Currently in beta. |

### Added by editing a configuration file

The address is the same everywhere. What differs is the key it goes under, and putting a correct address under the wrong key is the most common reason a setup does not connect.

| Client | How you add it | Configuration key |
|---|---|---|
| [Amazon Q Developer](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-mcp-config-CLI.html) | Add the server to `mcp.json`. | `mcpServers > type: http + url` |
| [Amp](https://ampcode.com/docs/customize/mcp) | Add it with a single command. | `CLI / amp.mcpServers > url` |
| [Claude Code](https://code.claude.com/docs/en/mcp) | Add it with a single command. | `CLI: --transport http` |
| [Cline](https://docs.cline.bot/mcp/connecting-to-a-remote-server) | Open the Remote Servers tab in settings and paste the URL. | `mcpServers > type: streamableHttp + url` |
| [Codex CLI](https://learn.chatgpt.com/docs/extend/mcp?surface=cli) | Add it with a single command. | `[mcp_servers.<name>] url` |
| [Continue](https://docs.continue.dev/customize/deep-dives/mcp) | Add the server to `config.yaml`. | `mcpServers[] > type: streamable-http + url` |
| [Cursor](https://cursor.com/docs/mcp)<br>[our guide](/docs/connect-pixalate-to-cursor) | Use the one-click install link, or add the server to your config file. | `mcpServers > url` |
| [Gemini CLI](https://geminicli.com/docs/tools/mcp-server/) | Add it with a single command. | `mcpServers > httpUrl` |
| [GitHub Copilot in VS Code](https://docs.github.com/en/copilot/how-tos/provide-context/use-mcp-in-your-ide/set-up-the-github-mcp-server?tool=vscode) | Add the server to `.vscode/mcp.json`. Tools appear in Agent mode. | `servers > type: http + url` |
| [Goose](https://goose-docs.ai/docs/getting-started/using-extensions/) | Run `goose configure` and add the server. | `extensions > type: streamable_http + uri` |
| [JetBrains AI Assistant](https://www.jetbrains.com/help/ai-assistant/configure-an-mcp-server.html) | Add an HTTP server in settings and paste the URL. | `mcpServers > url` |
| [Kiro](https://kiro.dev/docs/mcp/configuration/) | Add the server to `mcp.json`. | `mcpServers > url` |
| [Visual Studio Code](https://code.visualstudio.com/docs/agents/reference/mcp-configuration) | Add the server to `mcp.json`. | `servers > type: http + url` |
| [Warp](https://docs.warp.dev/agent-platform/capabilities/mcp/) | Paste the server JSON in settings. | `<name> > url` |
| [Windsurf](https://docs.devin.ai/desktop/cascade/mcp) | Add the server to your config file. | `mcpServers > serverUrl` |
| [Zed](https://zed.dev/docs/ai/mcp) | Add the server to `settings.json`. | `context_servers > url` |

### Questions about a specific client

**ChatGPT: I cannot find where to add a connector**

Custom connectors only appear once developer mode is switched on. Turn it on in settings first, then add the connector and paste the URL.

**Claude, web and desktop: I added the connector but Claude Code cannot see it**

Claude Code is a separate product and connects separately, with its own command. Adding a connector in Claude on the web or the desktop app does not carry across.

**Cursor: Should I use the install link or edit the config file?**

Either. The install link writes the same configuration for you. Edit the file directly if you keep your editor config in version control or want to see exactly what was added.

**GitHub Copilot in VS Code: I use GitHub Copilot and the tools do not appear**

GitHub Copilot only exposes MCP tools in Agent mode. Switch the Copilot chat view to Agent mode and the tools appear. In Ask or Edit mode they will not, and nothing about the configuration is wrong.

**In Agent mode and still nothing?** [I connected but I see no Pixalate tools](/docs/mcp-faq-and-troubleshooting#i-connected-but-i-see-no-pixalate-tools)

## The configuration shapes

Most clients want the address under a key. Three shapes cover nearly all of them:

Most editors, using `url`:

```json
{
  "mcpServers": {
    "pixalate-mcp": {
      "url": "https://mcp.pixalate.com/mcp"
    }
  }
}
```

VS Code and GitHub Copilot, note `servers` rather than `mcpServers`, and the explicit type:

```json
{
  "servers": {
    "pixalate-mcp": {
      "type": "http",
      "url": "https://mcp.pixalate.com/mcp"
    }
  }
}
```

Windsurf, note `serverUrl` rather than `url`:

```json
{
  "mcpServers": {
    "pixalate-mcp": {
      "serverUrl": "https://mcp.pixalate.com/mcp"
    }
  }
}
```

Check the table above for your client's exact key. Copying the address into the wrong key is the
most common reason a correct setup does not connect.

## A note on three clients

JetBrains AI Assistant, Cline and Continue document Streamable HTTP support but do not document
an OAuth sign in flow. Pixalate requires one. If the browser sign in does not start on those
clients, a local bridge is the documented workaround, and the vendor pages linked above cover it.

## If your client is not listed

It will still work if it supports remote MCP servers over Streamable HTTP. Give it the address
above, choose OAuth if it asks how to authenticate, and leave any key or token field empty. If
it offers a choice of transport, choose Streamable HTTP rather than SSE.

## Check that it worked

Ask your assistant:

> What Pixalate reports can I run?

If you get report names back, you are connected and your account is enabled. An empty tool list
after a successful sign in means your account has not been enabled yet, which your Pixalate
account manager can arrange.

*Reviewer note, not for publication: the client tables above are generated from the shared
source, `mcp-site/src/clients.json`, by `_gen_clients.py`. Do not hand-edit them. Send changes to
the website agent, who owns that file, and regenerate.*

*Sourcing: every client in the shared source is currently unverified, meaning nobody has tested
the connection against a live client. Rather than repeating the agreed sentence in 28 table
rows, it is stated once above the tables and each row links the vendor documentation it came
from. Confirm with the website agent that this satisfies the identical-surfaces requirement,
since their cards carry it per client.*
