---
name: answers
description: Get AI-powered answers with citations from live web data — with optional structured JSON output you can use directly in code. Use when the user needs up-to-date facts, competitive intelligence, pricing comparisons, or web-sourced answers in a specific shape.
argument-hint: <question>
---

# Olostep AI Answers

Ask a question, get an AI-synthesised answer from live web sources — with citations and optional structured JSON output you can paste straight into code. This is the most versatile tool in the Olostep toolkit: instead of scraping individual pages, you describe what you want to know and the shape you want the answer in.

## When to use

- User needs up-to-date facts that training data may not have
- User wants to compare tools, pricing, or features with current data
- User wants structured JSON output from a web question (e.g. `{"name": "", "price": ""}`)
- User wants cited, verifiable answers — not guesses

## Instructions

When the user asks a question they want answered from the web (via `$ARGUMENTS` or in conversation):

1. Use the `mcp__olostep__answers` tool with the user's question as the `task`.
2. If the user wants structured output, pass a JSON schema via the `json` parameter.
3. Present the answer with its citations and sources clearly.

## Parameters
- **task**: The question or task to answer using web data (required)
- **json**: JSON schema or description of desired output shape (optional). Example: `{"name": "", "price": "", "features": []}`

## Real developer workflows

**"What's the current state of X?"**
> "Is Bun production-ready in 2026? I want to replace Node in our API."
→ Returns a structured risk assessment with GitHub activity, production case studies, and community sentiment — all cited.

**"Compare pricing"**
> "Compare Vercel, Netlify, and Render pricing for a Next.js app with 100k monthly visitors"
→ Returns a structured comparison with plan names, prices, and limits from each vendor's current pricing page.

**"Get structured data from the web"**
> "Find the top 5 headless CMS options and return them as JSON with name, pricing, and open-source status"
→ Returns `[{"name": "...", "pricing": "...", "open_source": true}]` with citations.

## Tips
- Use a `json` schema whenever possible — structured output makes results directly usable in code
- Citations include source URLs so the user can verify and explore deeper
- Combine with `/olostep:scrape` for deeper dives into cited sources
