---
name: answers
description: Get AI-powered answers with citations and sources from the web using Olostep
argument-hint: <question>
---

# Olostep AI Answers

Search the web and get AI-powered answers with sources and citations. Optionally specify a JSON schema for structured output.

## Instructions

When the user asks a question they want answered from the web (via `$ARGUMENTS` or in conversation):

1. Use the `mcp__olostep__answers` tool with the user's question as the `task`.
2. If the user wants structured output, pass a JSON schema via the `json` parameter.
3. Present the answer with its citations and sources clearly.

## Parameters
- **task**: The question or task to answer using web data (required)
- **json**: JSON schema or description of desired output shape (optional). Example: `{"book_title": "", "author": "", "release_date": ""}`

## Examples

- `/olostep:answers What are the top AI frameworks in 2026?` — Get an AI answer with citations
- `/olostep:answers Find the founders of [company]` — Research with sources
- `/olostep:answers Compare pricing of [product A] vs [product B]` — Comparative analysis
- With structured output: Ask about products and specify `{"name": "", "price": "", "features": []}` as the JSON schema

## Tips
- Great for research questions, competitive analysis, and fact-checking
- Use structured JSON output for consistent, parseable responses
- Citations include source URLs so you can verify information
- Combine with `/olostep:scrape` for deeper dives into cited sources
