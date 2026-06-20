# Current Discoveries

New items discovered since the last newsletter.

- **Workload Identity Federation (WIF) generally available** — Replaces static `sk-ant-...` API keys with short-lived OIDC tokens from your own identity provider (AWS IAM, GCP, Kubernetes, Azure, GitHub Actions, Okta, or any OIDC-compliant issuer). Each workload gets its own service account (`svac_...`) with distinct identity, roles, and audit trail; federation rules (`fdrl_...`) bind external identities to scoped permissions. Token lifetimes are configurable (60–86,400s; default 3,600s), capped at twice the remaining IdP JWT lifetime. Set up via Claude Console "Connect workload" wizard or Admin API. Supports all Claude API endpoints including SDKs and Claude Code. Launched GA June 17, 2026. (Source: https://claude.com/blog/workload-identity-federation)
