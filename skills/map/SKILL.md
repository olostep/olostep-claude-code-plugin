---
name: map
description: Discover and list all URLs on a website for site analysis and planning
argument-hint: <website_url>
---

# Olostep Map

Discover all URLs on a website. Useful for site analysis, content auditing, and planning what to scrape.

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

## Examples

- `/olostep:map https://example.com` — Discover all URLs on a site
- `/olostep:map https://example.com blog` — Find only blog-related URLs
- `/olostep:map https://docs.example.com` — Map documentation structure

## Tips
- Use mapping before crawling to understand site structure
- Filter with include/exclude patterns for large sites
- Combine with `/olostep:batch` to scrape discovered URLs
