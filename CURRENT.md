# Current Discoveries

New items discovered since the last newsletter.

- **Claude Opus 4.8 released** — New model with sharper judgement and better independent working. Agentic coding score up from 64.3% to 69.2%; fast mode is 2.5x speed at 3x cheaper than before. Pricing unchanged from Opus 4.7. (Source: https://9to5mac.com/2026/05/28/anthropic-upgrades-claude-with-new-opus-4-8-model-heres-whats-new/)
- **Agent View dashboard** — `claude agents` opens a unified view of all running, blocked, and completed Claude Code sessions. (Source: https://code.claude.com/docs/en/changelog)
- **Dynamic Workflows (ultracode)** — `/workflows` lets Claude orchestrate tens to hundreds of background agents in parallel. The trigger keyword was renamed from `workflow` to `ultracode` (highlighted in violet). (Source: https://code.claude.com/docs/en/changelog)
- **/goal command** — Set a completion condition so Claude works autonomously across turns, with live metrics showing elapsed time, turns, and tokens used. (Source: https://code.claude.com/docs/en/changelog)
- **Skills auto-load from .claude/skills/directories** — Plugins in `.claude/skills/` now load automatically without the marketplace. Use `claude plugin init <name>` to scaffold a new plugin, and `disallowed-tools` frontmatter to restrict which tools a skill exposes. (Source: https://code.claude.com/docs/en/changelog)
- **MCP alwaysLoad option** — Set `alwaysLoad: true` on an MCP server to skip tool-search deferral and have it always fully loaded, useful for frequently-used servers. (Source: https://code.claude.com/docs/en/changelog)
- **Dreaming launched at Code with Claude 2026** — Anthropic's "Dreaming" feature is a scheduled process that reviews past agent sessions, surfaces cross-session patterns, and curates memory stores so agents self-improve over time. Available in research preview. Harvey reported 6x task completion improvement in internal testing. (Source: https://claude.com/blog/new-in-claude-managed-agents)
- **Claude Design launched** — New Anthropic Labs product (shipped alongside Opus 4.7) for collaborating with Claude to create visual outputs: designs, prototypes, slides, and one-pagers. (Source: https://releasebot.io/updates/anthropic)
- **/usage breakdown** — `/usage` now shows a per-category token cost breakdown: skills, subagents, plugins, and per-MCP-server usage. (Source: https://code.claude.com/docs/en/changelog)
- **/scroll-speed command** — Adjust terminal scroll speed with a live preview so you can tune it in real time. (Source: https://code.claude.com/docs/en/changelog)
- **claude ultrareview** — Non-interactive code review command for use in CI or scripts: `claude ultrareview [target]`. Add `--json` for structured output. (Source: https://code.claude.com/docs/en/changelog)
- **Avoid model switching to preserve cache** — Each model has its own prompt cache. Switching models with `/model` means the next request gets zero cache hits even if the conversation content is identical. Stick to one model per session for long tasks. (Source: https://code.claude.com/docs/en/prompt-caching)
- **Prompt cache lifetime is 5 minutes of inactivity** — Anthropic's prompt cache expires after ~5 minutes of inactivity, but each cache hit resets the timer. An active coding session keeps the cache warm indefinitely. (Source: https://www.mager.co/blog/2026-04-29-claude-prompt-caching/)
