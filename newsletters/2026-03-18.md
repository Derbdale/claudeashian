# Current Discoveries

New items discovered since the last newsletter.

- **Fast mode for Opus 4.6** — Research preview providing up to 2.5x faster output token generation via the `speed` parameter at premium pricing. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **Compaction API** — Server-side context summarization in beta, enabling effectively infinite conversations on Opus 4.6. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **Extended thinking display control** — New `thinking.display: "omitted"` option omits thinking content from responses for faster streaming while preserving signatures for multi-turn continuity. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **Automatic prompt caching** — Single `cache_control` field automatically caches the last cacheable block and moves the cache point forward as conversations grow. No manual breakpoint management required. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **600 media items per 1M context request** — Media limit raised from 100 to 600 images or PDF pages per request when using the 1M token context window. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **Plugin data persistence** — New `${CLAUDE_PLUGIN_DATA}` variable provides persistent storage for plugin state across sessions (v2.1.78). (Source: https://github.com/anthropics/claude-code/releases)
- **StopFailure hook event** — New hook event fires on API errors like rate limits and auth failures, enabling automated error handling (v2.1.78). (Source: https://github.com/anthropics/claude-code/releases)
- **Data residency controls** — New `inference_geo` parameter lets you specify where model inference runs. US-only inference available at 1.1x pricing for models released after February 2026. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **HTTP hook type** — Hooks can now POST event data to URLs with `"type": "http"`, enabling integration with external services and webhooks (v2.1.63). (Source: https://code.claude.com/docs/en/changelog)
- **Claude Agent SDK for Python** — Python SDK for programmatically building autonomous agents with Claude Code's capabilities including file editing, command execution, and complex workflows. (Source: https://github.com/anthropics/claude-agent-sdk-python)
- **Enterprise agent plugins launched** — Anthropic released stock enterprise plugins for finance, legal, HR, and design with new connectors for Gmail, DocuSign, and Clay, allowing agents to pull data from linked systems. (Source: https://techcrunch.com/2026/02/24/anthropic-launches-new-push-for-enterprise-agents-with-plugins-for-finance-engineering-and-design/)
- **Apple Xcode 26.3 Claude Agent SDK integration** — Native integration enables autonomous coding in Xcode with visual SwiftUI Preview testing, project-wide understanding, and MCP access for Claude Code CLI users. (Source: https://www.anthropic.com/news/apple-xcode-claude-agent-sdk)
- **Claude Sonnet 3.7 and Haiku 3.5 retired** — Both models retired February 19, 2026. Claude Haiku 3 deprecation announced with April 19, 2026 retirement date. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **/simplify and /batch bundled commands** — New bundled slash commands for code simplification and batch operations (v2.1.63). (Source: https://code.claude.com/docs/en/changelog)
- **`w` key in /copy writes to file** — Press `w` in the /copy picker to write the selection directly to a file instead of clipboard (v2.1.72). (Source: https://code.claude.com/docs/en/changelog)
- **/reload-plugins command** — Reload all plugins without restarting the session (v2.1.69). (Source: https://code.claude.com/docs/en/changelog)
- **Opus 4.6 effort defaults and ultrathink** — Opus 4.6 defaults to medium effort on Max/Team plans. Use "ultrathink" keyword to trigger high effort for maximum reasoning depth (v2.1.68). (Source: https://code.claude.com/docs/en/changelog)
