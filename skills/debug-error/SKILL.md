---
name: debug-error
description: Search the live web for a specific error message and find the real fix — from GitHub issues, StackOverflow, or framework docs. Use when the user pastes a stack trace, says their code is failing, or needs to fix a bug that requires current information.
argument-hint: <error message or description>
---

# Olostep Debug Error

Turn obscure error messages into working fixes by searching the live web and reading the actual solutions from GitHub issues, StackOverflow, or official docs.

## When to use

- User pastes a stack trace or terminal error and asks "how do I fix this?"
- User is facing a bug with a specific library version
- User asks if there's an open GitHub issue for a bug they found
- User is stuck and standard debugging hasn't worked

## Instructions

When the user shares an error (via `$ARGUMENTS` or in conversation):

1. Extract the core error message, framework, and version (if applicable) from the user's context.
2. Use `mcp__olostep__answers` with a targeted query to search the live web for the error.
   *Example: "How to fix [exact error message] in [Framework] v[Version]?"*
3. If the answer cites a specific GitHub issue or StackOverflow thread, use `mcp__olostep__scrape_website` on that URL to read the full discussion and find the accepted solution or workaround.
4. Explain the root cause based on the scraped context.
5. Provide the exact code fix or terminal commands the user needs to resolve the issue.

## Real developer workflows

**"Fix a weird build error"**
> "I'm getting 'Next.js 14 Error: x is not defined' when running npm run build. Help me fix it."
→ Searches for the error → finds a GitHub issue → scrapes the issue to find the workaround → applies fix.

**"Find out if a bug is a known issue"**
> "My Supabase auth listener is firing twice on login. Is this a known bug?"
→ Searches the Supabase repo for the bug → returns the status and any community workarounds.

**"Resolve dependency conflicts"**
> "npm ERR! ERESOLVE unable to resolve dependency tree for React 19 and Framer Motion"
→ Searches for the specific compatibility issue → scrapes the relevant PR or discussion → advises on the correct version or flag.

**"Framework-specific runtime error"**
> "TypeError: Cannot destructure property 'params' of 'undefined' in my Next.js 15 page component"
→ Searches → finds this is a breaking change in Next.js 15 where params are now async → provides the exact refactor needed.

## Tips
- Always prioritize scraping GitHub issues or official framework discussions — they have the most reliable solutions
- Don't just paste the scraped text; translate the solution directly into a fix for the user's specific codebase
- If an issue is marked as "open" with no fix, tell the user and suggest the most upvoted workaround
