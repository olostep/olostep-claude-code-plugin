---
name: scrape
description: Read any webpage as clean markdown, HTML, JSON, or text — including JavaScript-rendered SPAs, bot-protected sites, and pages behind Cloudflare. Use when the user shares a URL and wants to read it, extract content from it, use it as coding context, or turn a page into data.
argument-hint: <url> [format]
---

# Olostep Scrape

Extract clean, LLM-ready content from any URL — including JavaScript-heavy SPAs, bot-protected sites, and geo-restricted pages. Olostep runs a full browser with residential proxies and anti-bot bypass built in, so you get the exact content a real user sees.

## When to use

- User shares a URL and wants to read its content
- User wants to use a webpage as context for coding
- User wants content from a JavaScript-rendered SPA or bot-protected site
- User needs geo-targeted content (e.g. pricing from a specific country)

## Instructions

When the user provides a URL (via `$ARGUMENTS` or in conversation):

1. Use the `mcp__olostep__scrape_website` tool to scrape the URL.
2. Default to `markdown` format unless the user specifies otherwise (html, json, text).
3. If the page has dynamic content, use `wait_before_scraping: 2000`.
4. If the user needs geo-targeted content, ask for a country code (e.g., US, GB, CA).

## Parameters
- **url**: The webpage URL to scrape (required)
- **output_format**: `markdown` (default), `html`, `json`, or `text`
- **country**: Country code for geo-targeted scraping (optional)
- **wait_before_scraping**: Milliseconds to wait for JS rendering (0-10000, optional)
- **parser**: Specialized parser ID like `@olostep/amazon-product` (optional)

## Real developer workflows

**"Read this page for me"**
> "Scrape https://docs.stripe.com/api/payment_intents and summarise the API"
→ Returns clean markdown of the full page content, ready to use as coding context.

**"Get content from a protected site"**
> "Scrape this Cloudflare-protected changelog page"
→ Olostep's browser and proxies handle the protection automatically.

**"Get geo-specific pricing"**
> "Scrape this SaaS pricing page as seen from the UK"
→ Uses `country: GB` to return the UK-specific pricing.

## Tips
- For JavaScript-heavy sites (SPAs), use `wait_before_scraping: 2000`
- Use specialized parsers for popular platforms (Amazon, LinkedIn, etc.)
- Combine with other skills: scrape docs then write code, scrape an error thread then fix the bug
