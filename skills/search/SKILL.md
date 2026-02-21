---
name: search
description: Search the live web and get structured results with titles, URLs, snippets, and rich SERP data. Use when the user needs current information, wants to find a specific page, or needs Google search results programmatically.
argument-hint: <query>
---

# Olostep Search

Search the live web and get structured results — titles, URLs, snippets, knowledge graph data, and "People Also Ask" results. Two tools available: `google_search` for structured Google SERP data, and `get_website_urls` for finding pages within a specific site.

## When to use

- User needs current information from the web
- User wants to find a specific page, article, or resource
- User wants Google SERP results (organic, knowledge graph, People Also Ask)
- User wants to find pages within a specific site (e.g. "find the pricing page on this site")

## Instructions

When the user provides a search query (via `$ARGUMENTS` or in conversation):

1. Use the `mcp__olostep__google_search` tool for Google SERP results.
2. Use `mcp__olostep__get_website_urls` to find pages within a specific site.
3. Return the structured results including titles, URLs, and snippets.
4. If the user needs localized results, use the `country` parameter.

## Parameters
- **query**: The search query (required)
- **country**: Country code for localized results, e.g., `US`, `GB` (default: `US`)

## Real developer workflows

**"Find the right docs page"**
> "Search for the Next.js middleware documentation"
→ Returns the direct URL to the middleware docs, ready to scrape.

**"Get current information"**
> "Search for the latest Tailwind CSS v4 release notes"
→ Returns current results with links to the official announcement.

**"Find pages within a site"**
> "Find all authentication-related pages on the Supabase docs site"
→ Uses `get_website_urls` to return relevant pages ranked by relevance.

## Tips
- Use specific, descriptive queries for best results
- Combine with `/olostep:scrape` to get full content from interesting results
- Use country codes for location-specific search results
