---
name: research
description: Do thorough, cited web research to help make a decision — compare tools, evaluate competitors, research tech stacks, or assess market data. Use when the user needs a well-sourced answer before making a technical, product, or business decision.
argument-hint: <research question>
---

# Olostep Research

Do thorough, multi-source web research and present findings as structured, actionable intelligence. This is the skill for when you need to make a decision and want real data — cited, current, and structured.

## When to use

- User is choosing between tools, libraries, frameworks, or services
- User wants to understand competitors' features, pricing, positioning, or tech stack
- User is evaluating build vs buy for a component
- User needs market data, adoption stats, or trend information
- User wants to fact-check a technical claim
- User says "help me decide", "what should I use", "compare X vs Y", "is X worth it"

## Instructions

When the user asks a research question (via `$ARGUMENTS` or in conversation):

1. **Quick answer**: Use `mcp__olostep__answers` with a `json` schema for structured, cited results.
2. **Deep dive**: Scrape the most relevant sources with `mcp__olostep__scrape_website` for full detail.
3. **Multi-site comparison**: Use `mcp__olostep__batch_scrape_urls` on competitors' pricing/features/docs pages.
4. **Site-specific research**: Use `mcp__olostep__get_website_urls` to find relevant pages within a specific site.
5. **Synthesise and recommend**: Present findings as a table, structured JSON, or clear recommendation — always end with a recommendation, don't just list facts.

## Real developer workflows

**"Help me pick a tool"**
> "Compare Prisma, Drizzle, and Kysely for a serverless TypeScript API. Which should I use?"
→ `answers` with a structured JSON schema → detailed comparison → clear recommendation based on the user's constraints.

**"Competitive intelligence"**
> "I'm building a Firecrawl alternative. What do Firecrawl, Apify, and Browserbase offer, and where are the gaps?"
→ `answers` for broad overview → batch scrape each competitor's pricing + features pages → gap analysis with actionable insights.

**"Build vs buy"**
> "Should I build my own auth or use Clerk/Auth0/Supabase Auth? B2B SaaS with SSO."
→ `answers` with schema covering cost, SSO support, migration difficulty, vendor lock-in → recommendation.

**"Is this production-ready?"**
> "Is Bun production-ready in 2026? I want to replace Node in our API."
→ Aggregates GitHub activity, open issues, community sentiment, production case studies → structured risk assessment.

**"Vendor evaluation"**
> "Compare Pinecone, Weaviate, Qdrant, and Milvus for a RAG pipeline with 10M documents."
→ `answers` for capabilities overview → batch scrape each vendor's pricing page → comparison with scale requirements.

## Chain with other skills

- **research → scrape**: Get the quick answer, then scrape cited sources for full detail.
- **research → batch**: Compare multiple competitors by batch scraping their key pages.
- **research → docs-to-code**: Research which library to use, then use `/olostep:docs-to-code` to integrate it.
- **research → crawl**: For deep technical research, crawl an entire engineering blog or docs site.

## Tips
- Always use a `json` schema with `answers` — structured output makes comparisons fair and usable
- Always end with a recommendation — users want a decision, not just a list of facts
- For competitive research, scrape actual pricing/features pages — `answers` gives good overviews but may miss fine print
- Share citation URLs so users can verify and explore deeper
