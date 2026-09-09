---
title: FAQ and troubleshooting
hidden: false
---
## My sign in did not work

Check three things. Your Pixalate account has to be active and its email verified. If you left
the sign in page open for a long time before finishing, it will have expired, so close it and
start again. And if your configuration contains an `Authorization` header, an API key or a
token field, remove them: Pixalate signs you in through the browser, and a leftover credential
field stops that flow from starting.

## Which assistants work with this?

Any client that supports MCP. [The Install page](/docs/connect-your-assistant) lists the ones we know about, with connection steps for each.

If yours supports custom MCP connectors and is not listed, it will very likely work. Tell support@pixalate.com and we will add it.

## I can see one product but not another

Same cause. Access is granted per product, so you have been enabled for part of it. Ask for the
specific product you are missing.

## I connected but I see no Pixalate tools

Check your assistant's mode first. Some clients only expose tools in an agent mode, and in their other modes a correctly connected server shows nothing at all. The install page says which clients work that way.

If you are in the right mode and the list is still empty, your sign in worked and the tools are simply not enabled yet. Tools are enabled per product against your account's entitlements, and until that is done the list comes back empty rather than showing an error.

Contact your Pixalate account manager and say which product you need. Being specific about the product is faster than asking for access generally.

## How far back does the data go

Analytics data is available for a rolling three month window at launch. Older data exists but is
not reachable through the connector, so a longer question returns less than you expect rather
than failing. Ask your account manager if you need a longer history.

## I am being rate limited

Two different limits can stop a request, and they are fixed in different ways.

**The rate limit** caps how many requests you can make in a short window. At launch it is 60 requests a minute per account. You reach it by asking a lot in a short time, usually when an assistant is working through something in several steps. It clears on its own. Wait a moment and carry on.

**Your quota** is the total you can use over a period. It does not clear by waiting, and more of it is a conversation with your account manager rather than something support can change.

If you are not sure which one you have hit, the rate limit comes back within a minute and the quota does not.

## My export has fewer columns than I expected

Columns you are not entitled to are removed before the query runs, so an export contains the
columns your account can see and no others. If a column you expect is missing, it is an
entitlement question for your account manager rather than a problem with the export.

## My export link gives a not found error

On a large export the link is returned as soon as the export starts, while the file is still
being produced. Wait a few seconds and open it again. It is not a failed export.

## Why did I only get some of my rows?

Inline results are paged, and the first page is smaller than the maximum. You get 40 rows unless you ask for more, and you can ask for up to 100 at a time.

Ask for the next page to continue, or ask for more rows per page. If you want the whole set rather than a page of it, ask for an export instead: it has no row ceiling.

## Can I query another client's data

No. Every request is scoped to your own account. There is no client identifier to pass and no
way to reach another account's data.

## My numbers do not match the dashboard

Check the date range and the filters first, since a different window is the usual cause. If they
still differ, email support@pixalate.com with the report, the dates and both numbers. Do not
reconcile it yourself by exporting and recalculating, because that hides the discrepancy rather
than resolving it.

## It stopped working and is asking me to sign in again

That is expected. Sign in is periodic and your client will prompt you. Nothing is wrong.

## Something is wrong and none of this covers it

Email support@pixalate.com with the question you asked, what came back, and the date range
involved. Most issues turn out to be specific to one input rather than general.

If your assistant gave you a trace id, include it. It lets support find the exact call.

## Why does my assistant say a report does not exist

Report availability differs between accounts. Ask what reports are available before assuming a
particular one is there. Your assistant can list them.
