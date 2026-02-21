---
name: setup
description: Get started with Olostep in under a minute — configure your free API key and verify everything works. Use when setting up for the first time or troubleshooting authentication.
disable-model-invocation: true
---

# Olostep Setup

Get the user up and running with Olostep in under a minute. Free API key, quick config, done.

## Steps

1. Ask the user for their Olostep API key. If they don't have one, direct them to sign up at https://olostep.com/auth to get a free API key (100 credits/month included).

2. Once they provide the key, update the MCP server configuration. Add or update the following in the project's `.claude/settings.json` or the user's global Claude Code settings:

```json
{
  "mcpServers": {
    "olostep": {
      "command": "npx",
      "args": ["-y", "olostep-mcp"],
      "env": {
        "OLOSTEP_API_KEY": "<their-api-key>"
      }
    }
  }
}
```

3. Confirm the setup is complete and suggest they try a quick test:
   - `/olostep:scrape https://example.com` to test scraping
   - `/olostep:search latest AI news` to test search
   - `/olostep:answers What is the latest version of React?` to test AI answers

## Notes
- The free tier includes 100 credits/month — plenty to get started
- Get your API key at: https://olostep.com/auth
- Full documentation: https://docs.olostep.com
