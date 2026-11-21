# Current Discoveries

New items discovered since the last newsletter.

## Features

- **Claude Code v2.1.330** — Released November 20, 2026. Enterprise sign-in (`claude auth login`) now applies org settings and uses the org's configured cloud provider or gateway. New **Easel** built-in mod: draws charts automatically in responses and under MCP metrics results on Pro/Max/Team/Enterprise plans (macOS and Linux, toggleable in `/config`). `CLAUDE_CODE_FULL_SIGN_IN_LINK=1` env var prints the full sign-in link instead of a short URL. Recurring `/loop` runs and scheduled tasks maximum extended from 7 days to 30 days. Security: more `rm` commands targeting root, home, or working folder now require approval; `deniedMcpServers` name entries now block only the named connector rather than all connectors at a URL. 98 bug fixes. (Source: https://code.claude.com/docs/en/changelog)

## Integrations

- **Linked billing on Claude Platform (beta)** — Third-party platforms can bill end-customers' Claude API usage without receiving the customer's API key. Customers link their Claude Platform organization via a hosted flow, set monthly per-platform spend limits, and view usage in the Console. Platforms see usage per linked customer; requests run in the platform's org so some customer-side settings (IP allowlists, encryption keys, data retention) don't apply. Launch partners include Asana, Linear, Ramp, Railway, and Tines. Launched November 17, 2026. (Source: https://releasebot.io/updates/anthropic/claude-developer-platform)

## Shortcuts

- **`/tasks` command** — Lists all scheduled tasks, recurring `/loop` wakeups, the active goal, and forked sessions in a single view. Press `x` on a row to stop one. Introduced in Claude Code v2.1.329 (November 19, 2026). (Source: https://code.claude.com/docs/en/changelog)
