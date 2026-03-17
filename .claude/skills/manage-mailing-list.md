---
name: manage-mailing-list
description: Add, remove, or list email addresses in the Claudeashian newsletter mailing list.
---

# Manage Mailing List

Manage the Claudeashian newsletter mailing list stored in `.env`.

## Trigger

When the user asks to add, remove, list, or update email addresses in the mailing list.

## Procedure

### Reading the list

1. Read the `.env` file at the project root
2. Find the `CLAUDEASHIAN_EMAIL_LIST=` line
3. Split the value by commas
4. Trim whitespace around each entry
5. Filter out empty strings

If `.env` doesn't exist, copy `.env.example` to `.env` first.

### Adding an email

1. Read the current list (see above)
2. Validate the new address: must contain `@` with a `.` after the `@`
3. Check for duplicates (case-insensitive)
4. If not a duplicate, append to the list
5. Write back (see "Writing" below)

### Removing an email

1. Read the current list
2. Filter out the address (case-insensitive match)
3. Write back

### Listing emails

1. Read the current list
2. Display each address to the user

### Writing back

1. Read the entire `.env` file
2. Replace ONLY the `CLAUDEASHIAN_EMAIL_LIST=` line with the updated comma-separated value (no spaces after commas)
3. Preserve all other lines in `.env` exactly as they are
4. Use the Edit tool to make the change, not Write (to avoid clobbering the file)

## Important

- Never commit `.env` to git
- The `.env` file may contain other variables — always preserve them
- Email comparison is case-insensitive but preserve original casing when writing
