---
title: Connect Pixalate to ChatGPT
hidden: false
---
Pixalate works with ChatGPT through a custom connector. You sign in with your Pixalate account
during setup. There is no API key to paste.

The server address is:

```
https://mcp.pixalate.com/mcp
```

## Setup

1. Open Settings, then Connectors.
2. Choose Create, or Add custom connector.
3. Name it pixalate-mcp and paste the server address above.
4. Choose OAuth as the authentication method if you are asked. Do not enter a key or token.
5. Save and connect. A browser window opens for you to sign in with your Pixalate account.

Once connected, enable the Pixalate connector in a conversation and ask your question.

## Check that it worked

Ask:

> What Pixalate reports can I run?

A list of report names means you are connected and your account is enabled.

## Notes for ChatGPT specifically

Depending on your ChatGPT plan, custom connectors may only be available in certain modes or to
workspace administrators. If you cannot see the option to add one, that is a ChatGPT account
question rather than a Pixalate one, and your workspace administrator can enable it.

If you see no Pixalate tools after connecting successfully, your sign in worked but your account
has not been enabled yet. Contact your Pixalate account manager and say which product you need.

## Common questions

**I cannot find where to add a connector**

Custom connectors only appear once developer mode is switched on. Turn it on in settings first, then add the connector and paste the URL.
