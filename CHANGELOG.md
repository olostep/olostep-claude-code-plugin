# Changelog

## 1.0.1 (2026-11-22)

### Fixed

- Skills now use the tools the current MCP server exposes (`scrape_website`, `search_web`, `answers`, `batch_scrape_urls`, `get_batch_results`, `create_crawl`, `get_crawl_results`, `create_map`). The search, research, docs-to-code, migrate-code and integrate skills referenced `google_search`, `get_website_urls` and `get_webpage_content`, which the server no longer lists.
- The search skill documents the real `search_web` parameters (`limit`, `include_domains`, `exclude_domains`, `scrape_results`) instead of `country`; the crawl skill drops `follow_links`, which `create_crawl` doesn't accept.
- Batch limit corrected to 100,000 URLs per batch (README, plugin description, batch and integrate skills).
- `KNOWN_MCP_TOOLS` in the integrity tests matches the live server, so stale tool names are caught again.

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
