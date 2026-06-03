# Current Discoveries

New items discovered since the last newsletter.

## Features
- **Claude Opus 4.7 launched** — Released April 13, 2026 as the new default on Max and Team Premium. Introduced `xhigh` effort level as the recommended setting for most coding work, with an interactive `/effort` slider. (Source: https://code.claude.com/docs/en/whats-new)
- **Auto mode** — A classifier-based permission system that handles safe actions without interruption and blocks risky ones. Research preview in March 2026, now available on Pro, Bedrock, Vertex, and Foundry for Opus 4.7 and 4.8 (v2.1.83+). (Source: https://code.claude.com/docs/en/whats-new)
- **Computer use in CLI** — Claude can open native apps, click through UI, and verify changes from the terminal. Research preview launched in v2.1.86 (Week 14, March–April 2026). (Source: https://code.claude.com/docs/en/whats-new)
- **Claude Managed Agents** — Sandboxed agent platform with checkpointing and credential scoping, enabling production agents to run in environments you control with MCP access. Announced at Code with Claude 2026. (Source: https://www.infoq.com/news/2026/05/code-with-claude/)
- **Claude Opus 4.8 launched** — Released May 28, 2026. Benchmarks: agentic coding 64.3%→69.2%, reasoning with tools 54.7%→57.9%, computer use 82.8%→83.4%. High-effort defaults, fast mode at 2× standard rate for 2.5× speed. Pricing unchanged from 4.7. (Source: https://9to5mac.com/2026/05/28/anthropic-upgrades-claude-with-new-opus-4-8-model-heres-whats-new/)
- **Dynamic workflows** — Orchestrate dozens to hundreds of subagents from a Claude-written script; trigger with the keyword "ultracode" (violet highlighting). Research preview in v2.1.154. (Source: https://code.claude.com/docs/en/whats-new)
- **Plugin auto-loading from .claude/skills** — Plugins in `.claude/skills` directories load automatically without marketplace requirement. `claude plugin init <name>` scaffolds new plugins with autocomplete (v2.1.157). (Source: https://releasebot.io/updates/anthropic/claude-code)
- **MessageDisplay hook** — New hook event that fires on each message, enabling message transformation before display (v2.1.152). (Source: https://releasebot.io/updates/anthropic/claude-code)
- **Messages API mid-conversation system entries** — Messages API now accepts system entries mid-conversation without disrupting prompt caching, enabling dynamic context injection. (Source: https://9to5mac.com/2026/05/28/anthropic-upgrades-claude-with-new-opus-4-8-model-heres-whats-new/)

## Shortcuts & Commands
- **`claude agents` command** — Opens Agent View: a single screen showing all Claude Code sessions with their state (running, blocked, done). `claude agents --json` outputs the session list for scripting. (Source: https://code.claude.com/docs/en/whats-new)
- **/usage command** — Breaks down what's driving plan limits by skill, subagent, plugin, and MCP server, with per-category cost analysis and streaming reads for large session files (v2.1.145+). (Source: https://code.claude.com/docs/en/whats-new)
- **/ultrareview command** — Dispatches a fleet of cloud bug-hunting agents; findings land back in your CLI or Desktop automatically. Also available as `claude ultrareview` for CI/scripts (v2.1.114). (Source: https://code.claude.com/docs/en/whats-new)
- **/code-review command** — Reports correctness bugs with configurable effort levels. `--fix` applies findings to working tree; `--comment` posts findings as inline GitHub PR comments. Replaces the earlier /simplify command (v2.1.147). (Source: https://releasebot.io/updates/anthropic/claude-code)
- **/goal command** — Keeps Claude working across turns until a specified completion condition holds, replacing the need to re-prompt between steps (v2.1.139). (Source: https://code.claude.com/docs/en/whats-new)
- **Ctrl+T to toggle task list** — New keyboard shortcut to show/hide the active task list within a session. (Source: https://www.decodesfuture.com/articles/claude-shortcuts-keyboard-guide-2026)
- **`claude project purge`** — Cleans up local project state without touching the remote; useful for removing stale session data (v2.1.120). (Source: https://code.claude.com/docs/en/whats-new)
- **`--plugin-dir` / `--plugin-url` flags** — Load plugins from `.zip` archives on disk (`--plugin-dir`) or fetch a plugin archive from a URL (`--plugin-url`) for the current session (v2.1.128). (Source: https://code.claude.com/docs/en/whats-new)
- **/reload-skills command** — Rescans skill directories mid-session to pick up new or edited skill files without restarting (v2.1.152). (Source: https://releasebot.io/updates/anthropic/claude-code)
- **`! <command>` in agents view** — Run background shell commands from the agents view without switching to a terminal (v2.1.154). (Source: https://releasebot.io/updates/anthropic/claude-code)

## News
- **Code with Claude 2026 conference** — Anthropic's developer conference in May 2026 centered on the theme that "infrastructure, rather than intelligence, is now the bottleneck." Announcements included Managed Agents, dynamic workflows, auto mode, and cache hit rates as a key metric (targeting 94%+). (Source: https://www.infoq.com/news/2026/05/code-with-claude/)
- **Claude Design launched** — New Anthropic Labs product for collaborating with Claude to create visual outputs: designs, prototypes, slides, and one-pagers. Launched alongside Opus 4.7. (Source: https://linas.substack.com/p/anthropic-claude-2026-every-launch-guide)
- **Ultraplan research preview** — Draft execution plans from the CLI, review and annotate them in a web editor, then run remotely or pull them back local. First run auto-creates a cloud environment (Week 15, v2.1.92). (Source: https://code.claude.com/docs/en/whats-new)
- **Routines on Claude Code web** — Templated cloud agents that fire on a schedule, GitHub webhook event, or API call, enabling automated recurring workflows without the CLI (Week 16, April 2026). (Source: https://code.claude.com/docs/en/whats-new)
- **Claude Code web redesign** — New sessions sidebar, drag-and-drop layout, and split views. Desktop GUI adds ability to pin assistant messages as chapters with an auto-generated table of contents (Week 17, April 2026). (Source: https://code.claude.com/docs/en/whats-new)
- **Claude Code runs natively on Windows without Git Bash** — Git for Windows no longer required; Claude Code falls back to PowerShell as the shell tool when Bash is absent (v2.1.120, Week 18). (Source: https://code.claude.com/docs/en/whats-new)

## Tips & Tricks
- **Context engineering over prompt engineering** — In 2026, how you structure context matters more than how you phrase prompts. Use structured sections: INSTRUCTIONS, CONTEXT, TASK, OUTPUT FORMAT. A well-structured system prompt ("contract" format with role, success criteria, constraints, output spec) outperforms clever wording. (Source: https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- **Front-load critical information** — Place the most important instructions in the first 10% and last 10% of your prompt. Claude's attention mechanisms weight these sections more heavily than the middle. (Source: https://www.aiforanything.io/blog/claude-prompt-engineering-context-engineering-guide-2026)
- **Context rot degrades recall before the limit** — Even before hitting the hard context limit, Claude's ability to accurately recall earlier information decreases as token count grows (the "context rot" effect). Compact or start fresh proactively, not reactively. (Source: https://context.engineering)
- **Use /compact within a task, /clear between tasks** — `/compact` summarises conversation history while staying on the same task; use `/clear` when switching to a completely different task to avoid cross-task context contamination. (Source: https://code.claude.com/docs/en/whats-new)
- **Rewind menu to compress earlier context** — In the Rewind menu, select "Summarize up to here" to compress older context while keeping recent turns intact, without resetting the whole session (Week 20, v2.1.139). (Source: https://code.claude.com/docs/en/whats-new)

## Integrations
- **Desktop Extensions (.mcpb)** — Packaged MCP servers distributed as `.mcpb` files that install with a double-click, requiring no JSON config editing. Pre-configured bundles that work across Claude Desktop and Claude Code. (Source: https://toolradar.com/blog/claude-desktop-mcp-server-setup)
- **Meta's official Facebook/Instagram ads MCP** — Create campaigns, pull performance breakdowns, manage audiences, and run A/B analysis from the terminal via Claude Code. Launched April 29, 2026. (Source: https://medium.com/@docat0209/7-mcp-servers-every-claude-user-should-know-about-2026-9d17a0f5db73)
- **Google Colab MCP server** — Google Colab shipped its own MCP server in April 2026, enabling Claude to run and iterate on notebooks directly. Part of rapid MCP ecosystem growth (500+ public servers by mid-2026). (Source: https://codersera.com/blog/claude-skills-mcp-servers-practitioner-guide-2026/)
- **`worktree.baseRef` setting** — Controls whether new Claude-managed worktrees branch from the remote default or local `HEAD` (v2.1.128). Useful for monorepo branching strategies. (Source: https://code.claude.com/docs/en/whats-new)
- **Auto mode on Bedrock, Vertex, and Foundry** — Classifier-based auto mode available on major cloud providers for Opus 4.7 and 4.8 with an opt-in flag (v2.1.158). (Source: https://releasebot.io/updates/anthropic/claude-code)
- **OTEL agent tracing** — Agent ID and parent ID now added to OpenTelemetry spans with proper trace parenting; set `OTEL_LOG_TOOL_DETAILS=1` to log tool parameters in telemetry (v2.1.145, v2.1.157). (Source: https://releasebot.io/updates/anthropic/claude-code)
