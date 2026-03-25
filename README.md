# Olostep Plugin for Claude Code

Turn any website into clean, LLM-ready markdown or structured data. Olostep integrates powerful web scraping, crawling, search, and AI-powered answers directly into Claude Code.

## Features

- **Scrape** — Extract content from any webpage as markdown, HTML, JSON, or text
- **Search** — Search the web and get structured results
- **Crawl** — Autonomously discover and scrape entire websites
- **Map** — Discover all URLs on a site for analysis
- **Batch** — Scrape up to 10,000 URLs in parallel
- **AI Answers** — Get AI-powered answers with citations and sources

All with automatic JavaScript rendering, anti-bot handling, and proxy rotation built in.

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

After installing, run `/olostep:setup` to configure your API key.

1. Get your free API key at [olostep.com/auth](https://olostep.com/auth)
2. Run `/olostep:setup` and paste your key
3. Start scraping!

## Available Commands

| Command | Description |
|---------|-------------|
| `/olostep:setup` | Configure your Olostep API key |
| `/olostep:scrape` | Extract content from a single webpage |
| `/olostep:search` | Search the web for information |
| `/olostep:crawl` | Crawl an entire website from a start URL |
| `/olostep:map` | Discover all URLs on a website |
| `/olostep:batch` | Batch scrape up to 10,000 URLs |
| `/olostep:answers` | Get AI-powered answers with citations |

## Usage Examples

### Scrape a webpage
```
/olostep:scrape https://example.com
```

### Search the web
```
/olostep:search latest AI frameworks 2026
```

### Crawl a documentation site
```
/olostep:crawl https://docs.example.com 50
```

### Map a website's structure
```
/olostep:map https://example.com
```

### Batch scrape multiple URLs
```
/olostep:batch https://example.com/page1, https://example.com/page2, https://example.com/page3
```

### Get AI-powered answers
```
/olostep:answers What are the pricing plans for [product]?
```

## MCP Tools

You can also use Olostep's tools directly in conversation. Ask Claude to scrape a URL, search the web, gather competitive research, or extract structured data. The following MCP tools are available:

| Tool | Description |
|------|-------------|
| `scrape_website` | Extract content from a single URL (markdown, HTML, JSON, text) |
| `get_webpage_content` | Retrieve a webpage as markdown |
| `search_web` | Search the web with structured results |
| `google_search` | Get Google SERP data |
| `create_crawl` | Autonomously crawl a website |
| `create_map` | Discover all URLs on a site |
| `batch_scrape_urls` | Batch scrape up to 10k URLs |
| `answers` | AI-powered answers with citations |
| `get_website_urls` | Search and retrieve relevant URLs |

## Configuration

The plugin is configured via the MCP server. Environment variables:

| Variable | Required | Description |
|----------|----------|-------------|
| `OLOSTEP_API_KEY` | Yes | Your Olostep API key from [olostep.com/auth](https://olostep.com/auth) |

## Pricing

- **Free tier**: 500 free credits
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
