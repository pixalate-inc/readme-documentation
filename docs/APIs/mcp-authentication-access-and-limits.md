---
title: Authentication, access and limits
hidden: false
---
## How signing in works

Pixalate uses OAuth. You add a URL to your client, your client sends you to the Pixalate sign in
page in a browser, and you approve access there. Your client stores the credential it gets back.

You are never asked to paste an API key or a token into your client. If a set of instructions
tells you to, they are out of date.

You sign in again periodically. Your client will prompt you when that happens, and it is not a
sign that anything is wrong.

## Access is granted per product

Connecting successfully and having access are two separate things. A new account can sign in
and see an empty tool list, because tools are enabled per product against your entitlements.

If you see no tools, or you can see one product and not another, contact your Pixalate account
manager and say which product you need. Being specific is faster than asking for everything.

## What your account can reach

Every request is scoped to your own account. You do not pass a client identifier, and there is
no way to query another client's data.

Which reports, metrics and dimensions you can reach depends on your entitlements, and they
differ between accounts. Rather than assuming a fixed list, ask your assistant what is available
before you start. It will tell you what your account can actually see.

Columns you are not entitled to are removed before a query runs, including for exports, so an
export cannot contain a column your account is not entitled to.

## Result sizes

Results come back inline for ordinary questions, a page at a time. You get 40 rows unless you
ask for more, and you can ask for up to 100 at a time. Ask for the next page to continue.

When you want a whole result set rather than a page of it, ask for an export. You get back a
download link covering the full set, and the row limit above does not apply to it.

For a large export, the link is returned immediately while the file is still being produced.
If you follow it the instant you receive it you may get a not found error. Wait a few seconds
and try again rather than assuming the export failed.

## Data availability

Analytics data is available for a rolling window rather than indefinitely. At launch that window
is three months. Older data exists but is not reachable through this connector, so a question
phrased over a longer period will return less than you expect rather than failing outright.

If you need a longer history, that is a conversation with your account manager rather than a
setting you can change.

## Rate limits

You can make up to 60 requests per minute per account. That ceiling is shared across all
Pixalate tools rather than counted per tool.

Only actual tool calls count toward it. Connecting, signing in, and seeing which tools are
available do not, so browsing what you can do never uses any of it up.

If you go past the limit, your assistant receives an error telling it how long to wait, and it
will normally pause and retry on its own without you doing anything. If you see it happening
repeatedly, look at the shape of the question rather than the limit: asking about a long list of
items one at a time is the usual cause, because each item is a separate call.

## Rate limits and quota are different things

These are two separate controls and they fail in different ways, so it is worth knowing which
one you have hit.

Your **rate limit** is about speed: 60 calls per minute. Hitting it is temporary, it clears
within a minute, and nothing is used up.

Your **quota** is about volume over your billing month. It is consumed by the data you actually
receive rather than by the number of requests you make, so one broad query can consume more than
several narrow ones. When it is exhausted it stays exhausted until your next period or until
your allowance is increased.

In short: a rate limit means slow down, and a quota message means you have used your allowance.
Waiting fixes the first and does not fix the second.

## Usage and pricing

Usage is measured and charged per your agreement. Check your specific allowance with your
account manager.

*Reviewer note, not for publication: pricing is not decided and this section deliberately
carries no figures. It needs replacing with the agreed model before launch.*
