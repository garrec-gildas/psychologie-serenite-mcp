# Psychologie & Sérénité — public MCP server (read-only)

Public, read-only [Model Context Protocol](https://modelcontextprotocol.io) server for the catalogue of [Psychologie & Sérénité](https://psychologieetserenite.com): online psychology self-assessment tests, free blog articles, practical psychology books and the site's services, in French, English, Spanish and Portuguese.

- **Endpoint**: `https://psychologieetserenite.com/mcp` (Streamable HTTP, stateless, POST only)
- **Authentication**: none. No account, no API key.
- **Read-only**: the server never takes test answers, never opens an account, never charges anything and never reads personal data. Tests and purchases happen on the website.
- **Official MCP registry**: `com.psychologieetserenite/catalogue` (see `server.json`)
- **Documentation**: https://psychologieetserenite.com/developer#mcp · **Privacy policy**: https://psychologieetserenite.com/confidentialite · **Contact**: contact@psychologieetserenite.com

## Tools (11)
`list_services` · `describe_service` · `search_tests` · `get_test` · `start_test` (returns the link to take a test) · `get_example_report` · `search_articles` · `get_article` · `search_books` · `get_book` · `search_concepts`

Start with `list_services`, then `describe_service`. Every tool carries a `title` and `readOnlyHint: true`.

## Connect
Optional `?via=<client>` on the URL identifies your client in the publisher's visit statistics (links in responses carry `utm_source=mcp&utm_medium=<client>`).

| Client | Configuration |
|---|---|
| Claude (custom connector) | URL `https://psychologieetserenite.com/mcp` |
| Claude Code | `claude mcp add --transport http psychologie-serenite https://psychologieetserenite.com/mcp?via=claude-code` |
| Cursor | `mcp.json`: `"psychologie-serenite": {"url": "https://psychologieetserenite.com/mcp?via=cursor"}` |
| Codex CLI | `~/.codex/config.toml`: `[mcp_servers.psychologie-serenite]` + `url = "https://psychologieetserenite.com/mcp?via=codex"` |
| Gemini CLI | `gemini extensions install <this repository>` (uses `gemini-extension.json`) |
| Zed | `settings.json`: `"context_servers": {"psychologie-serenite": {"url": "https://psychologieetserenite.com/mcp?via=zed"}}` |
| LM Studio | `mcp.json`: `"psychologie-serenite": {"url": "https://psychologieetserenite.com/mcp?via=lm-studio"}` |

## Content and licence
Blog articles are published under CC-BY 4.0 (cite *Psychologie et Sérénité — Gildas Garrec*). Tests are self-assessment tools, not a diagnosis or medical advice. This repository contains only public metadata and documentation; the server's source code is not published here. No license is declared for this repository.
