---
name: map
description: Discover every URL on a website — then filter by keyword or pattern to find exactly what you need. Use when you want to see the structure of a site before scraping, find specific sections (docs, blog, API reference), or get a URL list to feed into batch or crawl.
argument-hint: <website_url>
---

# Olostep Map

Discover all URLs on a website and filter them to find exactly the pages you need. This is the reconnaissance step — map the site, then scrape or crawl the relevant pages.

## When to use

- User wants to see what pages exist on a site before scraping
- User wants to find specific sections (docs, blog, API reference, pricing)
- User wants a URL list to feed into batch scrape or crawl
- User wants to audit a site's structure or content coverage

## Instructions

When the user wants to map a website (via `$ARGUMENTS` or in conversation):

1. Use the `mcp__olostep__create_map` tool with the website URL.
2. If the user wants to filter URLs, use `search_query`, `include_url_patterns`, or `exclude_url_patterns`.
3. Use `top_n` to limit results if the site is large.
4. Present the discovered URLs in an organized format.

## Parameters
- **website_url**: Website URL to map (required)
- **search_query**: Filter URLs by keyword, e.g., "blog" (optional)
- **top_n**: Limit number of URLs returned (optional)
- **include_url_patterns**: Glob patterns to include, e.g., `/blog/**` (optional)
- **exclude_url_patterns**: Glob patterns to exclude, e.g., `/admin/**` (optional)

## Real developer workflows

**"Find the right docs pages"**
> "Map https://docs.stripe.com and find all pages related to webhooks"
→ Returns a filtered list of webhook-related doc pages → ready to scrape or batch.

**"Audit a site's structure"**
> "Map our marketing site and show me every URL grouped by section"
→ Returns a complete URL tree organized by path structure.

**"Prepare a batch scrape"**
> "Map this e-commerce site and find all product category pages"
→ Discovers URLs → filter with include patterns → feed the results into `/olostep:batch`.

## Tips
- Use mapping before crawling to understand site structure and target your scrape
- Filter with include/exclude patterns to avoid noise on large sites
- Combine with `/olostep:batch` to scrape discovered URLs at scale
