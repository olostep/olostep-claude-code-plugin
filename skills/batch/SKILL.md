---
name: batch
description: Scrape up to 10,000 URLs in a single batch operation using Olostep
argument-hint: <url1,url2,...>
---

# Olostep Batch Scrape

Scrape up to 10,000 URLs at once with Olostep's batch processing API. Perfect for large-scale data extraction.

## Instructions

When the user wants to batch scrape multiple URLs (via `$ARGUMENTS` or in conversation):

1. Collect the list of URLs from the user.
2. Use the `mcp__olostep__batch_scrape_urls` tool with the URL array.
3. Default to `markdown` output format unless specified.
4. Each URL can have an optional `custom_id` for tracking.

## Parameters
- **urls_to_scrape**: Array of `{url, custom_id?}` objects (1–10,000 URLs, required)
- **output_format**: `markdown` (default), `html`, `json`, or `text`
- **country**: Country code for geo-targeted scraping (optional)
- **wait_before_scraping**: Milliseconds to wait per URL (0-10000, optional)
- **parser**: Specialized parser ID (optional)

## Examples

- `/olostep:batch https://example.com/page1, https://example.com/page2` — Batch scrape 2 URLs
- `/olostep:batch` then provide a list of URLs — Interactive batch scraping
- Use with `/olostep:map` first to discover URLs, then batch scrape them

## Tips
- Combine with `/olostep:map` to discover URLs first, then batch scrape
- Use `custom_id` to label URLs for easier result tracking
- Support up to 10,000 URLs per batch
- All URLs are processed in parallel for maximum speed
