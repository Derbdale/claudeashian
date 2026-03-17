# Tips & Tricks

Tips, tricks, context management advice, and prompt techniques for Claude and Claude Code.

- **Context degrades at 60% fill** — Claude's output quality starts degrading at 20-40% of the context window due to attention mechanism weighting. Monitor the status bar fill indicator and compact or start a new session at 60%. (Source: https://institute.sfeir.com/en/claude-code/claude-code-context-management/tips/)
- **Use targeted grep over full file reads** — A targeted search consumes ~200 tokens vs ~3,000 for a full file read. Prefer grep/search over reading entire files. (Source: https://codeagents.app/guides/context-management)
- **Keep CLAUDE.md under 100 lines** — CLAUDE.md loads at the start of every conversation (~800 tokens). Move specific instructions into separate .claude/ files that load on demand. (Source: https://institute.sfeir.com/en/claude-code/claude-code-context-management/tips/)
- **Use thinking keywords for deeper reasoning** — Words like "think", "think hard", "think harder", or "ultrathink" directly impact how much thinking budget is allocated to Claude. (Source: https://www.datacamp.com/tutorial/claude-code-best-practices)
- **Double-escape to fork sessions** — Press Esc+Esc to jump back to earlier points in your conversation and fork Claude Code sessions to reuse well-formed context windows. (Source: https://blog.sshh.io/p/how-i-use-every-claude-code-feature)
- **Include tests for self-checking** — Including tests, screenshots, or expected outputs so Claude can check itself is the single highest-leverage thing you can do. (Source: https://www.datacamp.com/tutorial/claude-code-best-practices)
