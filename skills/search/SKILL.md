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
2. Return the results with their titles, URLs, and descriptions.
3. To limit the sources, pass `include_domains` or `exclude_domains`.
4. If the user needs the content of the results, set `scrape_results` to `true` to get each result page as markdown in the same call.
5. To find pages within one specific site, use `mcp__olostep__create_map` with the site URL and a `search_query`.

## Parameters
- **query**: The search query (required)
- **limit**: Number of results, 1-25
- **include_domains** / **exclude_domains**: Only return, or never return, results from these domains
- **scrape_results**: Set to `true` to also get each result page's content as markdown (uses extra credits per page)

## Examples

- `/olostep:search latest AI frameworks 2026` — Search the web
- `/olostep:search "Next.js caching" include_domains:nextjs.org` — Search one site's pages
- `/olostep:search competitor analysis for [company]` — Research competitors

## Tips
- Use specific, descriptive queries for best results
- Combine with `/olostep:scrape` to get full content from interesting results
- Use `scrape_results` when you need the content of every result, not just the links
