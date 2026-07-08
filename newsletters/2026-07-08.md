# Current Discoveries

New items discovered since the last newsletter.

- **Grey ⏸ badge for manual permission mode** — Claude Code v2.1.203 (July 7, 2026) adds a persistent grey ⏸ badge to the session footer whenever manual permission mode is active, giving a clear at-a-glance visual indicator of the current permission state alongside the existing Shift+Tab cycling shortcut. (Source: https://releasebot.io/updates/anthropic/claude-code)
- **`claude --worktree [name]`** — Start a new Claude Code session in an isolated git worktree; optionally name the worktree. Add `--tmux` to launch it in its own Tmux window, keeping worktree sessions visually separate from your main session. (Source: https://awesomeclaude.ai/code-cheatsheet)
- **`claude --teleport`** — Move an in-progress cloud (web/remote) session to your local terminal to continue it with full CLI access; mirrors session state from the cloud environment onto your machine. (Source: https://support.claude.com/en/articles/14554000-claude-code-power-user-tips)
- **`/remote-control` command** — Allow your phone or the claude.ai web interface to view and steer a local Claude Code terminal session in real time; pairs with mobile push notifications for away-from-desk supervision. (Source: https://support.claude.com/en/articles/14554000-claude-code-power-user-tips)
- **`/voice` command** — Activate hands-free voice dictation mode for Claude Code; approximately 3× faster than typing for extended input. Customisable push-to-talk keybinding via `voice:pushToTalk` in keybindings.json. (Source: https://support.claude.com/en/articles/14554000-claude-code-power-user-tips)
- **`/statusline` command** — Configure and customise the Claude Code status bar display; supports custom text, colours, and session metadata. Build reusable status-line plugins or use community packages from the marketplace. (Source: https://support.claude.com/en/articles/14554000-claude-code-power-user-tips)
