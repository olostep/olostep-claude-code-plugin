---
name: extract-schema
description: Turn any webpage into clean, structured JSON matching a TypeScript interface or schema. Use when the user wants to extract products, profiles, articles, or any structured data from a webpage — and get it back as typed, usable JSON.
argument-hint: <url> [schema or description]
---

# Olostep Extract Schema

Turn any unstructured webpage into perfectly formatted JSON or TypeScript objects. Scrape the site, then parse the data to match the user's exact schema.

## When to use

- User provides a URL and a TypeScript interface and says "extract the data to match this shape"
- User wants to populate a database or create seed data from a real website
- User is building a directory or aggregator and needs to scrape profiles, pricing, or features into JSON
- User wants to convert an unstructured blog post or news article into a structured metadata object

## Instructions

When the user provides a URL and a schema (via `$ARGUMENTS` or in conversation):

1. Review the TypeScript interface, JSON schema, or data shape requested by the user.
2. Scrape the target URL using `mcp__olostep__scrape_website` (use `output_format: markdown` — it's optimized for LLM parsing).
3. If scraping multiple pages (like a list of profiles), use `mcp__olostep__batch_scrape_urls`.
4. Parse the extracted markdown and map it strictly to the requested schema.
5. Output the result as a raw JSON code block, or write it directly to a `.json` or `.ts` file if requested.

## Real developer workflows

**"Generate database seed data"**
> "Scrape this YC startup directory page and generate a JSON array matching my Prisma schema: `{ name: string, description: string, batch: string, website: string }`. Write it to seed.json."
→ Scrapes the URL → parses the clean markdown into the exact JSON shape → creates the file.

**"Extract e-commerce products"**
> "Batch scrape these 5 Amazon product URLs and give me an array with title, price, rating, and inStock boolean."
→ Runs a batch scrape → extracts the fields for each product → returns the structured array.

**"Parse article metadata"**
> "Scrape this news article and extract the author, publishDate, mainTopics (array), and a 2-sentence summary."
→ Scrapes the article → extracts the fields → returns the JSON.

**"Build a competitor features table"**
> "Scrape these 3 competitor landing pages and extract: product name, tagline, key features (array), and pricing tier names"
→ Batch scrapes all three → returns a uniform JSON array for comparison.

## Tips
- Markdown format strips out HTML noise, making extraction accurate and cost-efficient
- If data is missing from the page, use `null` or omit the field as defined by the schema — never hallucinate data
- For many URLs, always use `batch_scrape_urls` for speed
- Use `wait_before_scraping: 3000` for e-commerce or directory sites that load data via client-side fetching
