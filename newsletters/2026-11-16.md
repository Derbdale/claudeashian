# Current Discoveries

New items discovered since the last newsletter.

- **Self-hosted Claude Managed Agents generally available (Nov 12, 2026)** — Run the full Managed Agents orchestration service on your own infrastructure rather than Anthropic-hosted servers. Distinct from the earlier self-hosted sandboxes (execution-only) beta. Request access via your Anthropic account team. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **Fable 5.2 / Mythos 5.2 thinking block isolation** — The API silently drops thinking blocks produced by Fable 5.2 or Mythos 5.2 when a conversation switches to any other model; no model outside the 5.2 pair can read those thinking blocks. Use the `thinking-binding-controls-2026-08-01` beta header to detect dropped blocks in multi-model workflows. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **Message Threads API (beta, Nov 2, 2026)** — Keeps conversation state on the server so long conversations send smaller API requests per turn, reducing per-request payload size in extended multi-turn workflows. (Source: https://platform.claude.com/docs/en/release-notes/overview)
- **Claude.ai and Claude Code service outage on November 13, 2026** — Authentication-related disruptions affected claude.ai and Claude Code; the Claude Console and Claude API remained operational throughout. Disruption details not publicly disclosed. (Source: https://businesstoday.in/technology/news/story/claude-ai-outage-anthropic-investigates-login-failures-as-ai-chatbot-and-coding-tools-face-outage-567403-2026-11-13)
