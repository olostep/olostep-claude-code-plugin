---
name: crawl
description: Crawl an entire docs site, blog, or knowledge base by following links from a start URL — and return all pages as clean markdown. Use when the user wants to ingest a full documentation site, learn a new library, or build context from a multi-page source.
argument-hint: <start_url> [max_pages]
---

# Olostep Crawl

Autonomously follow links and ingest an entire documentation site, blog, or knowledge base in one call. Every page comes back as clean, LLM-ready markdown.

## When to use

- User wants to learn a new library by reading its entire docs
- User wants to ingest a full docs site as context for coding
- User wants to build a knowledge base from a multi-page source
- User says "crawl this site" or "read all the docs"

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

## Real developer workflows

**"Learn a library from its docs"**
> "Crawl https://tanstack.com/query/latest/docs and give me a cheat sheet of the key hooks and patterns"
→ Crawls 10–15 docs pages → extracts commands and patterns → returns a focused cheat sheet.

**"Ingest docs as coding context"**
> "Crawl the Hono framework docs so you can help me build a REST API with it"
→ Crawls the docs → you now have full, current API knowledge to write accurate code.

**"Build a knowledge base"**
> "Crawl this company's engineering blog and summarise their architecture decisions"
→ Crawls blog posts → extracts key technical decisions → presents a structured summary.

## Tips
- Start with a small `max_pages` to test, then increase
- Combine with `/olostep:map` first to see what URLs exist before crawling
- Great as a first step before writing code — crawl the docs, then code from them
