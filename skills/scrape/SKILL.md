---
name: scrape
description: Scrape a single webpage and extract its content as markdown, HTML, JSON, or text using Olostep
argument-hint: <url> [format]
---

# Olostep Scrape

Extract content from a single webpage URL using Olostep's web scraping API with JavaScript rendering and anti-bot handling.

## Instructions

When the user provides a URL (via `$ARGUMENTS` or in conversation):

1. Use the `mcp__olostep__scrape_website` tool to scrape the URL.
2. Default to `markdown` format unless the user specifies otherwise (html, json, text).
3. If the page has dynamic content, suggest using `wait_before_scraping` (e.g., 2000ms).
4. If the user needs geo-targeted content, ask for a country code (e.g., US, GB, CA).

## Parameters
- **url**: The webpage URL to scrape (required)
- **output_format**: `markdown` (default), `html`, `json`, or `text`
- **country**: Country code for geo-targeted scraping (optional)
- **wait_before_scraping**: Milliseconds to wait for JS rendering (0-10000, optional)
- **parser**: Specialized parser ID like `@olostep/amazon-product` (optional)

## Examples

- `/olostep:scrape https://example.com` — Get page content as markdown
- `/olostep:scrape https://example.com/product json` — Get structured JSON
- `/olostep:scrape https://amazon.com/dp/B0... with the amazon-product parser` — Use specialized parser

## Tips
- For JavaScript-heavy sites (SPAs), use `wait_before_scraping: 2000`
- Use specialized parsers for popular platforms (Amazon, LinkedIn, etc.)
- Olostep handles anti-bot protections and proxy rotation automatically
