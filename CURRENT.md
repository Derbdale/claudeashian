# Current Discoveries

New items discovered since the last newsletter.

- **Claude API version 2026-10-21 breaking changes** — New default API version with significant breaking changes: temperature, top_p, and top_k parameters removed from the Messages API (requests including them return 400). Authentication migrated to Bearer header; the old X-Api-Key header still accepted for direct calls but not for proxies. Request size limits raised from 32 MB to 128 MB. Text Completions API removed from TypeScript, Go, Java, and Ruby SDKs and the CLI. SDK major releases targeting this version: Python 2.0.0, TypeScript 1.0.0, C# 13.0.0, Go 2.0.0, Java 3.0.0, PHP 1.0.0, Ruby 2.0.0, CLI 2.0.0. A beta Usage and Cost Analytics API launched for per-dimension organization-level token and cost reporting. (Source: https://apidog.com/blog/claude-api-version-2026-10-21/)
