# Features

Claude and Claude Code features, capabilities, and model updates.

- **Claude Opus 4.6 launched** — Released February 5, 2026 with 1M token context window, stronger coding, better planning/debugging, and improved financial analysis. (Source: https://its.northeastern.edu/2026/02/26/anthropics-latest-claude-models-are-here-and-theyre-a-big-leap-forward/)
- **Claude Sonnet 4.6 released** — Launched February 17, 2026 with near-Opus performance on coding and document comprehension, plus improved computer use. (Source: https://releasebot.io/updates/anthropic/claude)
- **1M context window generally available** — Available on Max, Team, and Enterprise plans for Opus 4.6 and Sonnet 4.6 at standard pricing. No beta header required. (Source: https://code.claude.com/docs/en/changelog)
- **Opus 4.6 output tokens increased to 64k** — Default max output tokens raised to 64k, upper bound to 128k for both Opus 4.6 and Sonnet 4.6 (v2.1.77). (Source: https://github.com/anthropics/claude-code/releases)
- **Voice mode in Claude Code** — Push-to-talk via spacebar, customisable keybinding (voice:pushToTalk in keybindings.json), rolling out progressively. (Source: https://pasqualepillitteri.it/en/news/381/claude-code-march-2026-updates)
- **MCP Elicitation support** — MCP servers can now request structured input mid-task via interactive dialog. New Elicitation and ElicitationResult hooks added (v2.1.76). (Source: https://code.claude.com/docs/en/changelog)
- **Worktree sparse checkout** — New worktree.sparsePaths setting for large monorepos to check out only needed directories (v2.1.76). (Source: https://github.com/anthropics/claude-code/releases)
- **Context command improvements** — /context now gives actionable suggestions identifying context-heavy tools, memory bloat, and optimisation tips (v2.1.74). (Source: https://code.claude.com/docs/en/changelog)
- **Custom auto-memory directory** — New autoMemoryDirectory setting to choose where auto-memory files are stored (v2.1.74). (Source: https://code.claude.com/docs/en/changelog)
- **Model overrides setting** — New modelOverrides setting to map model picker entries to custom provider model IDs (v2.1.73). (Source: https://code.claude.com/docs/en/changelog)
- **Fast mode for Opus 4.6** — Research preview providing up to 2.5x faster output token generation via the `speed` parameter at premium pricing. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **Compaction API** — Server-side context summarization in beta, enabling effectively infinite conversations on Opus 4.6. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **Extended thinking display control** — New `thinking.display: "omitted"` option omits thinking content from responses for faster streaming while preserving signatures for multi-turn continuity. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **Automatic prompt caching** — Single `cache_control` field automatically caches the last cacheable block and moves the cache point forward as conversations grow. No manual breakpoint management required. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **600 media items per 1M context request** — Media limit raised from 100 to 600 images or PDF pages per request when using the 1M token context window. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **Plugin data persistence** — New `${CLAUDE_PLUGIN_DATA}` variable provides persistent storage for plugin state across sessions (v2.1.78). (Source: https://github.com/anthropics/claude-code/releases)
- **StopFailure hook event** — New hook event fires on API errors like rate limits and auth failures, enabling automated error handling (v2.1.78). (Source: https://github.com/anthropics/claude-code/releases)
- **Data residency controls** — New `inference_geo` parameter lets you specify where model inference runs. US-only inference available at 1.1x pricing for models released after February 2026. (Source: https://platform.claude.com/docs/en/release-notes/overview)
