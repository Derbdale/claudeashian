# Current Discoveries

New items discovered since the last newsletter.

- **Background subagents surface permission prompts in main session** — Background subagents now relay their permission prompts to the main session interface instead of auto-denying them, letting unattended multi-agent runs continue when a permission is needed rather than silently failing (Week 26, v2.1.191–v2.1.193, June 2026). (Source: https://code.claude.com/docs/en/whats-new)
- **`CLAUDE_CODE_DISABLE_MOUSE_CLICKS` env var** — Set `CLAUDE_CODE_DISABLE_MOUSE_CLICKS=1` to disable mouse-click interactions in fullscreen mode while keeping mouse-wheel scroll active; useful for terminal emulators that misinterpret click events in the TUI (v2.1.195, June 26, 2026). (Source: https://github.com/anthropics/claude-code/releases)
- **External plugins require explicit install consent** — Claude Code now requires user confirmation before installing external plugins that aren't already in your configuration, preventing silent third-party plugin installation (v2.1.195, June 26, 2026). (Source: https://github.com/anthropics/claude-code/releases)
- **`.claude/commands/` is now legacy; migrate to `.claude/skills/<name>/SKILL.md`** — The older `.claude/commands/` directory format for custom slash commands is considered legacy (it still works but is no longer the recommended approach). The current standard is `.claude/skills/<name>/SKILL.md`, which supports richer metadata, parameterised invocation, and marketplace distribution. (Source: https://www.datacamp.com/tutorial/claude-code-slash-commands)
