# Integrations

MCP servers, IDE integrations, API updates, and SDK changes for Claude.

- **MCP Tool Search lazy loading** — Enables lazy loading for MCP servers, reducing context usage by up to 95%. Run all MCP servers without worrying about context limits. (Source: https://claudefa.st/blog/tools/mcp-extensions/best-addons)
- **PostCompact hook** — New hook that fires after compaction completes, enabling post-compaction automation (v2.1.76). (Source: https://code.claude.com/docs/en/changelog)
- **allowRead sandbox setting** — New sandbox filesystem setting to re-allow read access within denyRead regions for more granular permissions (v2.1.77). (Source: https://github.com/anthropics/claude-code/releases)
- **HTTP hook type** — Hooks can now POST event data to URLs with `"type": "http"`, enabling integration with external services and webhooks (v2.1.63). (Source: https://code.claude.com/docs/en/changelog)
- **Claude Agent SDK for Python** — Python SDK for programmatically building autonomous agents with Claude Code's capabilities including file editing, command execution, and complex workflows. (Source: https://github.com/anthropics/claude-agent-sdk-python)
