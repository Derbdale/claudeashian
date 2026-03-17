# KUWTC: Send Newsletter

Format CURRENT.md into a designed HTML email, send via Resend API, archive, and commit.

## Trigger

When the user says "send newsletter", "send email", "publish newsletter", or when invoked by cron at 11:00 BST.

## Procedure

### 1. Check git state

Run `git status`. If there are uncommitted changes to files **outside** `newsletters/` and `CURRENT.md`, warn the user and stop.

Run `git diff --cached --stat`. If anything is already staged, warn the user and stop.

### 2. Read and evaluate CURRENT.md

Read CURRENT.md. If it contains only the header and no bullet entries below it, stop — nothing to send.

If there are entries, use your judgment: is this content interesting or substantial enough to warrant sending a newsletter? Consider:
- Is there at least one noteworthy item?
- Would recipients find this valuable?
- A single major announcement is worth sending. Several trivial items may not be.

If not worth sending, stop. Items carry over to tomorrow's evaluation.

### 3. Pre-send validation

Before attempting to send, verify all requirements:

1. Check that `templates/newsletter.html` exists. If not, stop with error: "Missing templates/newsletter.html"
2. Read the `.env` file and extract `RESEND_KEY`. If empty or missing, stop with error: "Missing RESEND_KEY in .env"
3. Read the `.env` file and extract `CLAUDEASHIAN_EMAIL_LIST`. If empty or missing, stop with error: "Missing CLAUDEASHIAN_EMAIL_LIST in .env"
4. Read `CLAUDEASHIAN_FROM_EMAIL` from `.env`. If not set, default to `onboarding@resend.dev`

If using `onboarding@resend.dev` and there are multiple recipients, warn: "Test from-address can only deliver to your Resend signup email. Other recipients may not receive the newsletter."

### 4. Generate subject line

Read the entries in CURRENT.md and generate a dynamic subject line:

```
Keeping up with the Claudeashians: highlight1, highlight2
```

Rules:
- Pick 1-3 of the most notable items as highlights
- Keep the total subject under 78 characters
- The prefix "Keeping up with the Claudeashians: " is 38 chars, leaving ~40 for highlights
- Use short, punchy descriptions (e.g., "Claude 4 released, new MCP tools")

### 5. Render HTML email

1. Read the HTML template from `templates/newsletter.html`
2. Parse each bullet entry from CURRENT.md. Entries follow the format:
   ```
   - **Title** — Description. (Source: URL or description)
   ```
3. Convert each entry to an HTML list item:
   ```html
   <li style="margin-bottom: 16px;"><strong>Title</strong> — Description. <a href="URL" style="color: #6366f1; text-decoration: none;">Source</a></li>
   ```
4. Wrap all items in `<ul style="padding-left: 20px; list-style-type: disc;">...</ul>`
5. In the template, replace:
   - `{{CONTENT}}` with the rendered HTML list
   - `{{SUBJECT}}` with the subject line (without the "Keeping up with the Claudeashians: " prefix — just the highlights)
   - `{{DATE}}` with today's date formatted nicely (e.g., "March 17, 2026")

Store the final HTML string for the next step.

### 6. Send via Resend API

Build and send the email using `curl` and `jq` for safe JSON construction:

```bash
set -a; source .env; set +a

# Build recipient array from comma-separated list
TO_JSON=$(echo "$CLAUDEASHIAN_EMAIL_LIST" | tr ',' '\n' | sed 's/^ *//;s/ *$//' | jq -R . | jq -s .)

# Send the email
HTTP_CODE=$(curl -s -o /tmp/resend_response.json -w "%{http_code}" \
  --max-time 30 --connect-timeout 10 \
  -X POST 'https://api.resend.com/emails' \
  -H "Authorization: Bearer $RESEND_KEY" \
  -H 'Content-Type: application/json' \
  -d "$(jq -n \
    --arg from "${CLAUDEASHIAN_FROM_EMAIL:-onboarding@resend.dev}" \
    --argjson to "$TO_JSON" \
    --arg subject "$SUBJECT" \
    --arg html "$HTML_CONTENT" \
    '{from: $from, to: $to, subject: $subject, html: $html}')")
```

**CRITICAL: Check the HTTP status code before proceeding.**

If `$HTTP_CODE` is `200`:
- Print "Newsletter sent successfully" and the email ID from the response
- Clean up: `rm -f /tmp/resend_response.json`
- Proceed to step 7

If `$HTTP_CODE` is anything else:
- Print the error from `/tmp/resend_response.json`
- Clean up: `rm -f /tmp/resend_response.json`
- **STOP IMMEDIATELY. Do NOT archive CURRENT.md. Do NOT commit.**
- Content that was never delivered must remain in CURRENT.md for the next attempt.

### 7. Archive CURRENT.md

Only reach this step after a confirmed successful send (HTTP 200).

```bash
mkdir -p newsletters/
cp CURRENT.md "newsletters/$(date +%Y-%m-%d).md"
```

Then overwrite CURRENT.md with the fresh header:

```markdown
# Current Discoveries

New items discovered since the last newsletter.
```

### 8. Commit and push

```bash
git add newsletters/ CURRENT.md
git commit -m "newsletter: send and archive $(date +%Y-%m-%d)"
git push origin main
```

If push fails, leave the commit for manual resolution. Do not retry.

## Important

- **NEVER archive CURRENT.md unless the Resend API returned HTTP 200** — archiving after a failed send means content is permanently lost without ever being delivered. This is the most critical rule in this skill.
- **Never use `git add -A` or `git add .`** — only stage `newsletters/` and `CURRENT.md` explicitly
- **Never commit `.env`** — it contains API keys and email addresses
- **Use `jq` to construct the JSON payload** — never interpolate HTML directly into a JSON string. Quotes, angle brackets, and special characters will break it.
- **Subject line max ~78 chars** — keep highlights short and punchy
- **`onboarding@resend.dev` limitation** — this test address can only deliver to your Resend signup email. For multi-recipient delivery, set `CLAUDEASHIAN_FROM_EMAIL` to an address on a verified domain in Resend.
- **If CURRENT.md is empty or content not worth sending** — do nothing. No send, no archive, no commit, no output.
- **If the send fails** — print the error, leave CURRENT.md untouched, and stop. The next run will re-evaluate and try again.
