# Olostep Plugin for Claude Code

Give Claude Code a live connection to the web. Scrape any URL, search the web with cited AI answers, crawl entire doc sites, and extract structured data from any page — all with JavaScript rendering, anti-bot bypass, and residential proxies built in.

## What you can do

- **Scrape** — Read any webpage as clean markdown, HTML, JSON, or text — including JS-rendered SPAs and bot-protected sites
- **Search** — Search the live web and get structured Google SERP results
- **Crawl** — Ingest an entire docs site or blog in one call by following links automatically
- **Map** — Discover every URL on a site before you scrape, so you target exactly what you need
- **Batch** — Scrape up to 10,000 URLs in parallel — products, pricing pages, changelogs, competitor sites
- **AI Answers** — Ask a question, get a cited, structured answer pulled from live web sources
- **Docs-to-Code** — Scrape API docs and write working integration code from the real, current reference
- **Debug Error** — Search live GitHub issues and forums to find the fix for any error
- **Extract Schema** — Turn any webpage into typed JSON matching your interface or database model
- **Migrate Code** — Scrape a migration guide and automatically update your code to the new version
- **Research** — Multi-source web research for tool comparisons, competitive intelligence, and technical decisions

## Installation

### One-Click Install (Claude Code)

Run in Claude Code:

```
/install-plugin olostep
```

### Manual Install

```bash
claude plugin add olostep/olostep-claude-code-plugin
```

## Setup

1. Get your free API key at [olostep.com/auth](https://olostep.com/auth)
2. Run `/olostep:setup` and paste your key
3. Start using any skill below!

## Skills

| Skill | Invoke | What it does |
|---|---|---|
| `setup` | `/olostep:setup` | Configure your Olostep API key and verify the MCP server is running |
| `scrape` | `/olostep:scrape` | Read any webpage as clean markdown — handles JS, bot protection, and geo-targeting |
| `search` | `/olostep:search` | Search the live web and get structured results with titles, URLs, and snippets |
| `crawl` | `/olostep:crawl` | Crawl an entire website from a start URL, following links automatically |
| `map` | `/olostep:map` | Discover all URLs on a site and filter by keyword or pattern |
| `batch` | `/olostep:batch` | Batch scrape up to 10,000 URLs in parallel |
| `answers` | `/olostep:answers` | Get AI-powered answers with citations and optional structured JSON output |
| `docs-to-code` | `/olostep:docs-to-code` | Scrape API docs and write working, up-to-date integration code |
| `debug-error` | `/olostep:debug-error` | Search GitHub issues and forums to find the fix for a real error |
| `extract-schema` | `/olostep:extract-schema` | Turn any webpage into typed JSON matching your schema |
| `migrate-code` | `/olostep:migrate-code` | Scrape a migration guide and automatically update your code |
| `research` | `/olostep:research` | Multi-source web research for tool comparisons and technical decisions |

## Real developer workflows

**"Read the docs and write the integration"**
> "Scrape https://docs.stripe.com/api/payment_intents and write me a TypeScript function to create a payment intent"

**"Fix this error"**
> "I'm getting `Cannot read properties of undefined (reading 'map')` in Next.js 15 — help me fix it"

**"Crawl and learn a new library"**
> "Crawl https://tanstack.com/query/latest/docs and give me a cheat sheet of the key hooks and patterns"

**"Compare competitors before building"**
> "Batch scrape the pricing pages of Vercel, Netlify, and Render — extract plan names, prices, and limits as JSON"

**"Extract structured data"**
> "Scrape this YC directory page and return a JSON array matching my Prisma `Startup` schema"

**"Migrate to a new version"**
> "Scrape the Next.js 15 migration guide and update my layout.tsx"

## MCP Tools

These tools are available directly in conversation once the MCP server is running:

| Tool | Description |
|------|-------------|
| `scrape_website` | Extract content from a single URL (markdown, HTML, JSON, text) |
| `get_webpage_content` | Retrieve a webpage as clean markdown |
| `google_search` | Get structured Google SERP data (organic, knowledge graph, People Also Ask) |
| `answers` | AI-powered answers with citations and optional JSON output shape |
| `create_crawl` | Autonomously crawl a website from a start URL |
| `create_map` | Discover all URLs on a site with include/exclude pattern filtering |
| `batch_scrape_urls` | Scrape up to 10,000 URLs in parallel |
| `get_website_urls` | Find and rank URLs within a specific site by relevance to a query |

## Configuration

| Variable | Required | Description |
|----------|----------|-------------|
| `OLOSTEP_API_KEY` | Yes | Your Olostep API key from [olostep.com/auth](https://olostep.com/auth) |

## Pricing

- **Free tier**: 100 credits/month
- Sign up at [olostep.com/auth](https://olostep.com/auth)
- See full pricing at [olostep.com/pricing](https://olostep.com/pricing)

## Links

- [Olostep Website](https://olostep.com)
- [API Documentation](https://docs.olostep.com)
- [Get API Key](https://olostep.com/auth)
- [MCP Server on npm](https://www.npmjs.com/package/olostep-mcp)
- [GitHub](https://github.com/olostep)

## License

MIT License — see [LICENSE](LICENSE) for details.
