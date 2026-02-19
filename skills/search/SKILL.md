---
name: search
description: Search the web using Olostep and get structured results with scraped content
argument-hint: <query>
---

# Olostep Search

Search the web and get structured results using Olostep's search API.

## Instructions

When the user provides a search query (via `$ARGUMENTS` or in conversation):

1. Use the `mcp__olostep__search_web` tool to search the web.
2. Return the structured results including titles, URLs, and snippets.
3. If the user needs localized results, use the `country` parameter.
4. For Google-specific SERP data, use `mcp__olostep__google_search`.

## Parameters
- **query**: The search query (required)
- **country**: Country code for localized results, e.g., `US`, `GB` (default: `US`)

## Examples

- `/olostep:search latest AI frameworks 2026` — Search the web
- `/olostep:search "best restaurants in London" country:GB` — Localized search
- `/olostep:search competitor analysis for [company]` — Research competitors

## Tips
- Use specific, descriptive queries for best results
- Combine with `/olostep:scrape` to get full content from interesting results
- Use country codes for location-specific search results
