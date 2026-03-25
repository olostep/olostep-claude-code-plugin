---
name: crawl
description: Autonomously crawl an entire website starting from a URL, following links to discover and scrape pages
argument-hint: <start_url> [max_pages]
---

# Olostep Crawl

Autonomously discover and scrape entire websites by following links from a starting URL.

## Instructions

When the user wants to crawl a website (via `$ARGUMENTS` or in conversation):

1. Use the `mcp__olostep__create_crawl` tool with the starting URL.
2. Default to `max_pages: 10` unless the user specifies otherwise.
3. Default to `markdown` output format unless specified.
4. Inform the user that crawling follows links automatically.

## Parameters
- **start_url**: Starting URL for the crawl (required)
- **max_pages**: Maximum pages to crawl (default: 10)
- **follow_links**: Whether to follow discovered links (default: true)
- **output_format**: `markdown` (default), `html`, `json`, or `text`
- **country**: Country code for geo-targeted crawling (optional)
- **parser**: Specialized parser ID (optional)

## Examples

- `/olostep:crawl https://docs.example.com` — Crawl documentation site (10 pages)
- `/olostep:crawl https://example.com/blog 50` — Crawl up to 50 blog pages
- `/olostep:crawl https://example.com json` — Crawl and get JSON output

## Tips
- Start with a small `max_pages` to test, then increase
- Use on documentation sites, blogs, or product catalogs
- Combine with `/olostep:map` first to see what URLs exist before crawling
- Set `follow_links: false` to only scrape the starting page
