# Current Discoveries

New items discovered since the last newsletter.

- **Anthropic Messages API rewritten in Rust by Claude** — Disclosed October 27, 2026 via the Latent Space podcast. Anthropic migrated its Messages API from a Python monolith to Rust with no Rust developers on the team — Claude wrote most of the code while humans handled design and verification. The rewrite ran in shadow mode against the old Python system before cutover. Result: approximately 40–50% CPU reduction per request and 10–20% faster time to first token. The public API was unchanged. (Source: https://www.latentspace.co/p/anthropic-rust-rewrite)
