# TASK-S0-001 — Read-only foundation discovery

Status: PROPOSED; default target: `beta`.

Goal: inventory actual repo state, inspect AGENTS/PLANS and user-provided architecture source, identify conflicting IDs and unresolved ADR/PoC gates.

In scope: read files/branches, compare current refs, record build/test tools if present, propose a migration for legacy test IDs, propose S0 contract and CI gates, write a review report.

Out of scope: app code, dependencies, production OBS, real stream/recording, branch deletion, unrelated Git changes, auto-merge, deployment.

Acceptance: evidence-backed repo inventory; precise test ID conflict report; no invented build commands or PoC results; explicit next approval request before implementing.
