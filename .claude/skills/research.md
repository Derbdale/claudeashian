# Research Claude News

Discover recent Claude/Claude Code news, features, tips, tricks, shortcuts, and integrations. Update the knowledge base and CURRENT.md, then commit and push.

## Trigger

When the user says "research", "find news", "check for updates", "what's new with Claude", or when invoked by cron.

## Procedure

### 1. Bootstrap

If `knowledge/` directory or any of its category files do not exist, create them:

- `knowledge/features.md` — "# Features" header
- `knowledge/tips.md` — "# Tips & Tricks" header
- `knowledge/shortcuts.md` — "# Shortcuts & Commands" header
- `knowledge/news.md` — "# News" header
- `knowledge/integrations.md` — "# Integrations" header

If `CURRENT.md` does not exist, create it with:

```markdown
# Current Discoveries

New items discovered since the last newsletter.
```

### 2. Check git state

Run `git status`. If there are uncommitted changes to files **outside** `knowledge/` and `CURRENT.md`, warn the user and stop. Do not risk sweeping unrelated changes into the research commit.

### 3. Search sources

Search **all three** source types every run. Vary your search terms and angles each time — don't repeat the same queries. Try different keywords, explore different aspects of Claude (API, CLI, models, pricing, community, workflows, prompt engineering, MCP, SDK).

**Web search:**
Use WebSearch to find recent Claude/Claude Code content. Try angles like:
- "Claude Code new features 2026"
- "Anthropic Claude tips tricks"
- "Claude context management best practices"
- "Claude Code shortcuts commands"
- "Claude MCP server integrations"

Run 3-5 varied searches per session. Follow promising results with WebFetch to read the actual content.

**Anthropic docs:**
Use WebFetch to check these pages for recent updates:
- Anthropic's docs changelog or what's new page
- Claude Code documentation for new features

**GitHub:**
Use WebFetch to check the Claude Code GitHub repo (anthropics/claude-code):
- Recent releases/tags
- Notable recent issues and discussions
- README changes

If any source is unreachable, skip it and continue with the remaining sources.

### 4. Deduplicate and categorise

For each discovery from step 3:

1. Decide which **single** category file it belongs to (best fit):
   - `features.md` — new capabilities, model updates, product launches
   - `tips.md` — usage tips, context management, prompt techniques
   - `shortcuts.md` — keyboard shortcuts, CLI commands, slash commands
   - `news.md` — announcements, blog posts, industry news, partnerships
   - `integrations.md` — MCP servers, IDE plugins, API changes, SDK updates

2. Read that `knowledge/*.md` file using the Read tool

3. Judge whether the core information is already covered:
   - **Duplicate:** The same fact/feature/tip exists, even if phrased differently or from a different source
   - **New:** Genuinely new information, OR substantive new details about an existing topic (e.g., new benchmarks, pricing changes, additional capabilities)

4. If genuinely new, append it to the category file using the Edit tool with this format:
   ```
   - **Short descriptive title** — Brief explanation of the item. (Source: URL or description)
   ```

### 5. Derive CURRENT.md from git diff

This step has a **strict ordering** — follow exactly:

```bash
# 1. Stage only knowledge base changes
git add knowledge/

# 2. Check if anything was actually staged
git diff --cached --stat
```

If nothing was staged (no new discoveries), **stop here** — do not commit or push.

If changes were staged:

```bash
# 3. Get the full diff of staged changes
git diff --cached --no-color
```

Parse the diff output:
- Extract lines starting with `+` (these are additions)
- Exclude lines starting with `+++` (file headers)
- Strip the leading `+` character
- Filter to only the entry lines (lines starting with `- **`)

Append these entries to CURRENT.md using the Edit tool.

### 6. Commit and push

```bash
# Stage CURRENT.md
git add CURRENT.md

# Commit
git commit -m "research: add new items to knowledge base"

# Push to origin
git push origin main
```

If the push fails, leave the commit as-is for manual resolution. Do not retry.

## Important

- **Never use `git add -A` or `git add .`** — only stage `knowledge/` and `CURRENT.md` explicitly
- **Never commit `.env`** — it contains email addresses and is gitignored
- **Vary search angles every run** — try different keywords, explore different aspects of Claude (API, CLI, models, pricing, community, workflows). The goal is to cast a wider net over time, not repeat the same searches.
- **Single category per item** — place each discovery in the single best-fit category. Do not duplicate across files.
- **If zero new items are found** — do nothing. No commit, no push, no output.
- **Dedup rubric** — same core fact = duplicate, even from a different source. New substantive info about an existing topic = new item.
- **Entry format** — always use: `- **Title** — Description. (Source: URL or description)`
- **Git operation order is critical** — write KB files → stage KB → diff staged → write CURRENT.md → stage CURRENT.md → commit → push. Getting this wrong means CURRENT.md will have wrong content.
