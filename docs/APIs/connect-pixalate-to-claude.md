---
title: Connect Pixalate to Claude
hidden: false
---
You can use Pixalate from Claude on the web, in the desktop app, or in Claude Code. Setup takes
about a minute and you sign in with your Pixalate account. There is no API key to copy and no
token to paste anywhere.

The server address is:

```
https://mcp.pixalate.com/mcp
```

## Claude on the web and Claude Desktop

1. Open Settings, then Connectors.
2. Choose Add custom connector.
3. Name it pixalate-mcp and paste the server address above.
4. Save, then choose Connect.
5. A browser window opens. Sign in with your Pixalate account and approve access.

The window closes on its own. Pixalate now appears in your connector list and its tools are
available in any conversation.

## Claude Code

Run this in a terminal:

```
claude mcp add --transport http pixalate-mcp https://mcp.pixalate.com/mcp
```

The first time Claude Code connects it opens your browser to sign in.

## Check that it worked

Ask Claude:

> What Pixalate reports can I run?

You should get a list of the reports available on your account. If you get an answer with real
report names in it, you are connected and entitled, and you can start asking questions.

## If you see no Pixalate tools

Signing in and having access are two separate steps. Your sign in can succeed while your account
has not yet been enabled for any tools, and the result is an empty tool list rather than an
error message.

If that happens, contact your Pixalate account manager and say which product you are trying to
use. Access is granted per product, so it helps to be specific.

## What your account can see

The tools are scoped to your own account. You do not pass a client identifier and you cannot
query another client's data. Which reports, metrics and dimensions you can reach depends on
your Pixalate entitlements, which is why the first question above is worth asking before
anything else: it tells you what you have rather than making you guess.

## Common questions

**I added the connector but Claude Code cannot see it**

Claude Code is a separate product and connects separately, with its own command. Adding a connector in Claude on the web or the desktop app does not carry across.
