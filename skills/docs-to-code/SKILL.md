---
name: docs-to-code
description: Scrape API documentation or library docs and write working, up-to-date integration code from them. Use when the user wants to integrate a third-party API, learn a new library, generate SDK usage examples, or write code based on a docs URL.
argument-hint: <docs_url> [what to build]
---

# Olostep Docs-to-Code

Turn any documentation URL into working, tested code. Scrape the real docs, understand the API surface, and write the integration. The result is code that works on the first try because it's based on what the docs actually say right now.

## When to use

- User wants to integrate a third-party API and shares (or mentions) a docs URL
- User says "write me code using [library]" — especially if it's new, niche, or recently updated
- User wants examples for a library that shipped a new major version
- User wants to generate a typed client, SDK wrapper, or helper from an API reference
- User says "read the docs and write the code" or "use the latest docs"

## Instructions

When the user provides a docs URL and a coding goal (via `$ARGUMENTS` or in conversation):

1. **Scrape the docs page**: Use `mcp__olostep__scrape_website` with `output_format: markdown`, `wait_before_scraping: 2000`.
2. **If docs span multiple pages**: Use `mcp__olostep__get_website_urls` or `mcp__olostep__create_map` to find sub-pages (auth, endpoints, types, errors), then scrape the relevant ones.
3. **For entire doc sites**: Use `mcp__olostep__create_crawl` with `max_pages: 15` to ingest a full docs section.
4. **Parse the API surface**: Extract endpoints, parameters (required vs optional), auth patterns, request/response shapes, error codes.
5. **Write the code**: Use exactly what's in the docs. Include correct imports, auth setup, TypeScript types derived from the docs' response shapes, and error handling for documented error codes.
6. **Cite the source**: Link to the doc page you scraped so the user can verify.

## Real developer workflows

**"Integrate this API"**
> "Scrape https://docs.resend.com/api-reference/emails/send-email and write a Next.js API route that sends a welcome email"
→ Scrape the endpoint docs → extract auth header, payload shape, response → write a typed handler.

**"Generate a typed client"**
> "Scrape the Anthropic messages API docs and write me a fully typed TypeScript client with streaming support"
→ Scrape API reference → extract endpoints, input/output types → generate a client class with methods for each endpoint.

**"Learn a library and write examples"**
> "Crawl https://docs.upstash.com/redis and generate 5 practical examples for a Next.js app"
→ Crawl 10–15 docs pages → extract commands and patterns → write 5 focused, working examples.

**"Write the auth flow"**
> "Scrape the Clerk docs for Next.js App Router and write the complete auth setup: middleware, sign-in page, protected routes"
→ Scrape 3–4 relevant docs pages → write each piece with correct imports and configuration.

## Chain with other skills

- **map → scrape → code**: Map a docs site to find the right pages → scrape the specific reference pages → write code from them.
- **search → scrape → code**: Don't have the docs URL? Use `/olostep:search` to find it, then scrape and code.
- **crawl → code**: For full library learning, crawl the entire docs section → synthesise into working examples.

## Tips
- For large APIs, use `/olostep:map` first to find the exact reference pages, then scrape those specifically
- Prefer specific reference pages over overview/guide pages — they have the exact parameters and types
- If auth is unclear from the endpoint docs, scrape the authentication/quickstart page separately
- Always include error handling based on documented error codes
- Link to the scraped doc page so the user can verify the code matches
