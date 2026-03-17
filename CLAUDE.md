# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

"Keeping up with the Claudeashians" — a skill-based system that automatically discovers Claude/Claude Code news, features, tips, and tricks, maintains a knowledge base, and sends a daily newsletter digest.

## Architecture

### Three core workflows

1. **Research (runs multiple times/day via cron):** A research agent searches for new Claude-related news, features, commands, use-cases, tips & tricks. Discovered items are checked against the knowledge base to avoid duplicates, then appended to `CURRENT.md`.

2. **Knowledge Base (persistent markdown files):** All learned knowledge is stored as markdown in a `knowledge/` directory. Each item should be deduplicated against existing entries. `CURRENT.md` holds items discovered since the last newsletter was sent.

3. **Newsletter (runs daily at 11:00 BST via cron):** If `CURRENT.md` has enough or important content, it gets formatted into a newsletter template and emailed to the `CLAUDEASHIAN_EMAIL_LIST` environment variable. After sending, content moves from `CURRENT.md` into the permanent knowledge base archive.

### Key files

- `CURRENT.md` — staging area for newly discovered items not yet sent in a newsletter
- `knowledge/` — permanent archive of all past discoveries (the knowledge base)
- Skills live in `.claude/skills/` as SKILL.md files

### Environment variables

Configuration lives in a `.env` file at the project root (gitignored). See `.env.example` for expected variables.

- `CLAUDEASHIAN_EMAIL_LIST` — comma-separated email addresses for newsletter delivery

To load env vars in a skill or script, read `.env` directly or use `set -a; source .env; set +a` in shell contexts.
