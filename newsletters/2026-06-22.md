# Current Discoveries

New items discovered since the last newsletter.

- **Stream-stall detection threshold extended to 20s** — In v2.1.185 (June 20, 2026), the hint that appears during API silence changed from "No response from API · Retrying in …" to "Waiting for API response · will retry in …", and the silence threshold before the hint appears was extended from 10s to 20s, reducing false-alarm interruptions on slow responses. (Source: https://code.claude.com/docs/en/changelog)
- **`?` key displays shortcuts for your environment** — Press `?` on an empty prompt to show all available keyboard shortcuts for the current terminal and IDE surface, accounting for platform-specific differences. (Source: https://support.claude.com/en/articles/14553413-claude-code-cheatsheet)
- **Ctrl+O opens verbose full transcript view** — Press Ctrl+O to switch to a detailed, full-content transcript of the current session, including complete tool inputs and outputs. (Source: https://support.claude.com/en/articles/14553413-claude-code-cheatsheet)
- **/btw command for side questions** — `/btw <question>` lets you ask Claude a quick side question mid-task without adding it to the main conversation history, so the primary task context stays clean. (Source: https://support.claude.com/en/articles/14553413-claude-code-cheatsheet)
- **`@path` syntax references files directly in your prompt** — Type `@src/auth/session.ts` in your prompt to pin a specific file or directory into context, reducing hallucination and grounding responses in your actual code rather than training data. (Source: https://support.claude.com/en/articles/14553413-claude-code-cheatsheet)
