---
name: batch
description: Scrape up to 10,000 URLs in parallel — product pages, competitor sites, job listings, changelogs, or any set of known pages. Use when the user has a list of URLs to extract content from at scale.
argument-hint: <url1,url2,...>
---

# Olostep Batch Scrape

Scrape up to 10,000 URLs in parallel. All URLs are processed concurrently for maximum speed — perfect for comparing competitors, extracting product catalogs, or ingesting multiple doc pages at once.

## When to use

- User has a list of URLs to scrape (product pages, pricing pages, docs, etc.)
- User wants to compare content across multiple sites side-by-side
- User wants to extract data from many pages at scale
- User discovered URLs via `/olostep:map` and wants to scrape them all

## Instructions

When the user wants to batch scrape multiple URLs (via `$ARGUMENTS` or in conversation):

1. Collect the list of URLs from the user.
2. Use the `mcp__olostep__batch_scrape_urls` tool with the URL array.
3. Default to `markdown` output format unless specified.
4. Each URL can have an optional `custom_id` for tracking.
5. **To see actual results** (the batch starts as pending): either pass `wait_for_completion_seconds` (e.g. 60) so the tool returns full results when done, or call `mcp__olostep__get_batch_results` with the returned `batch_id` after a short wait (or retry until status is completed).

## Parameters
- **urls_to_scrape**: Array of `{url, custom_id?}` objects (1–10,000 URLs, required)
- **output_format**: `markdown` (default), `html`, `json`, or `text`
- **wait_for_completion_seconds**: If set (e.g. 60), poll until batch is done and return full results; use 0 to only get `batch_id` and call `get_batch_results` later (optional)
- **country**: Country code for geo-targeted scraping (optional)
- **wait_before_scraping**: Milliseconds to wait per URL (0-10000, optional)
- **parser**: Specialized parser ID (optional)

## Related tool
- **get_batch_results**: Pass the `batch_id` from `batch_scrape_urls` to fetch status and scraped content when the batch is ready.

## Real developer workflows

**"Compare competitor pricing"**
> "Batch scrape the pricing pages of Vercel, Netlify, and Render — extract plan names, prices, and limits"
→ Scrapes all three pricing pages in parallel → returns clean content for side-by-side comparison.

**"Extract a product catalog"**
> "Batch scrape these 50 Amazon product URLs and extract title, price, and rating from each"
→ Processes all 50 URLs concurrently → returns structured data for each product.

**"Ingest multiple doc pages"**
> "Batch scrape these 8 API reference pages so I can write a typed client"
→ Scrapes all pages at once → you have the full API surface to generate code from.

## Tips
- Combine with `/olostep:map` to discover URLs first, then batch scrape the results
- Use `custom_id` to label URLs for easier result tracking
- All URLs are processed in parallel for maximum speed
