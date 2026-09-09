---
title: Tool reference
hidden: false
---
What each Pixalate tool does, what it needs from you, and what it gives back. You do not have to
call these by name. Ask your assistant in plain language and it will choose. The names are here
so you can be specific when you want to be.

Which of these you can see depends on your account. If one is missing, see
[authentication and limits](/docs/mcp-authentication-access-and-limits).

## Analytics

### pix_analytics_describe

**Discovers what your account can actually run.** Report and column availability differs between
accounts, so this is the source of truth rather than a fixed published list. Call it before
anything else.

Ask with no report and you get the reports available to you, each with its default columns. Ask
about one report and you get that report's columns, with their labels, formats and tooltips.

> "What Pixalate reports can I run?"

> "What columns are available on the fraud by seller report?"

There is also a custom mode. Asking about custom columns tells you the full set you can draw on
when you want a report shape that is not one of the presets.

If a report is not available to your account the response says so rather than failing silently.

### pix_analytics_query

**Runs a report for your account.** Either a named report that `describe` returned, or a custom
column selection of your own.

Required: the report and an inclusive date range. Optional: filters, grouping, ordering, and
column overrides. Column names should come from `describe` rather than being guessed, because a
name valid on one account may not exist on another, and an unentitled or unknown column returns
an error rather than being ignored.

> "Run the fraud by seller report for last month"

> "Rank my campaigns by IVT rate for August and show me the worst ten"

**You can ask for detail rows, summary totals, or both.** Both is the default. Summaries give
panel totals and a per-day series; details give the grid rows.

**Inline results are paged, and the default page is smaller than the maximum.** You get 40 rows
unless you ask for more, up to 100 at a time. If a count looks short, that is usually the reason
rather than the data being missing. Ask for the next page, or ask for more rows.

**Ask for an export when you want the whole set.** You get a download link covering everything,
with no row ceiling, using the same report, columns, filters and order as the equivalent detail
query. Paging does not apply to it. On a large export the link arrives before the file is
finished, so wait a few seconds before opening it.

**Check whether any columns were dropped.** If your account is not entitled to one of a report's
default columns, the response tells you which were left out rather than quietly returning a
narrower table. Worth a glance before you conclude a column is missing from the product.

**Every response carries a trace id.** If something looks wrong, quote it to support and they can
find the exact call.

Ordering matters more than it looks on questions like "which was worst". Ask for a ranking so the
sort happens before the rows are cut, rather than asking for rows and then a judgement about
them.

## MRT enrichment

### pix_enrichment_query

**Risk ratings and reputation for one app or domain that you already know.** You choose which
widgets you want, so you pay for the dimensions you asked for rather than a whole profile.

It covers mobile apps, CTV apps and web domains. You give it the kind, the identifier, and the
widgets you want. Identifiers are platform native: a bundle id for a mobile app, a numeric
channel id for a Roku channel, a bare domain like `example.com` for a website.

> "What are the Pixalate risk ratings for com.example.app?"

> "Show me brand safety and invalid traffic for example.com"

**One identifier per call.** There is no multi-id batch, so a question about a list of apps
becomes one call per app. That is worth knowing before pointing it at a long list, because each
call is charged separately.

Cost tracks how much data comes back rather than which widget you asked for. A request that spans
many regions and devices returns many records and costs more than the same widget restricted to
one. Narrowing region and device is the lever.
