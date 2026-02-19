# Changelog

## 1.0.0 (2026-02-17)

### Initial Release

- **Plugin structure** with `.claude-plugin/plugin.json` manifest
- **MCP server integration** via `olostep-mcp` npm package
- **7 skills (slash commands)**:
  - `/olostep:setup` — Configure API key
  - `/olostep:scrape` — Scrape single webpage
  - `/olostep:search` — Web search with structured results
  - `/olostep:crawl` — Autonomous website crawling
  - `/olostep:map` — Website URL discovery
  - `/olostep:batch` — Batch scrape up to 10k URLs
  - `/olostep:answers` — AI-powered answers with citations
