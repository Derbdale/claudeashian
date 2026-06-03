# Tips & Tricks

Tips, tricks, context management advice, and prompt techniques for Claude and Claude Code.

- **Context degrades at 60% fill** — Claude's output quality starts degrading at 20-40% of the context window due to attention mechanism weighting. Monitor the status bar fill indicator and compact or start a new session at 60%. (Source: https://institute.sfeir.com/en/claude-code/claude-code-context-management/tips/)
- **Use targeted grep over full file reads** — A targeted search consumes ~200 tokens vs ~3,000 for a full file read. Prefer grep/search over reading entire files. (Source: https://codeagents.app/guides/context-management)
- **Keep CLAUDE.md under 100 lines** — CLAUDE.md loads at the start of every conversation (~800 tokens). Move specific instructions into separate .claude/ files that load on demand. (Source: https://institute.sfeir.com/en/claude-code/claude-code-context-management/tips/)
- **Use thinking keywords for deeper reasoning** — Words like "think", "think hard", "think harder", or "ultrathink" directly impact how much thinking budget is allocated to Claude. (Source: https://www.datacamp.com/tutorial/claude-code-best-practices)
- **Double-escape to fork sessions** — Press Esc+Esc to jump back to earlier points in your conversation and fork Claude Code sessions to reuse well-formed context windows. (Source: https://blog.sshh.io/p/how-i-use-every-claude-code-feature)
- **Include tests for self-checking** — Including tests, screenshots, or expected outputs so Claude can check itself is the single highest-leverage thing you can do. (Source: https://www.datacamp.com/tutorial/claude-code-best-practices)
- **Opus 4.6 effort defaults and ultrathink** — Opus 4.6 defaults to medium effort on Max/Team plans. Use "ultrathink" keyword to trigger high effort for maximum reasoning depth (v2.1.68). (Source: https://code.claude.com/docs/en/changelog)
- **Avoid model switching to preserve cache** — Each model has its own prompt cache. Switching models with `/model` means the next request gets zero cache hits even if the conversation content is identical. Stick to one model per session for long tasks. (Source: https://code.claude.com/docs/en/prompt-caching)
- **Prompt cache lifetime is 5 minutes of inactivity** — Anthropic's prompt cache expires after ~5 minutes of inactivity, but each cache hit resets the timer. An active coding session keeps the cache warm indefinitely. (Source: https://www.mager.co/blog/2026-04-29-claude-prompt-caching/)
