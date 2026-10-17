# Better OW OCS — gated development plan (v0.1-DRAFT)

Phases are ordered engineering gates, NOT proof of completion or calendar commitments.

| Stage | Scope | Exit evidence |
|---|---|---|
| S0 Governance | Accepted agent workflow, ID registry, task templates, initial ADR and CI strategy | S0 task reviewed, contradictions and blockers tracked |
| S1 Broadcast core | Simulated OBS, Preview/Program, TAKE state machine, dedupe/reconciliation | Timeout, duplicate and manual scene-change negative tests pass |
| S2 Match and graphics | Match CRUD, publish snapshot, Overlay reload and storage | Unpublished changes never leak into Program |
| S3 Media PoC | Three independent OW observer clients; NDI-vs-SRT; OBS scene/latency | Real test logs and a transport/scenes ADR |
| S4 Security and recovery | Roles, authorization, secret handling, backup and failure injection | P0 security/data faults closed, recovery proof |
| S5 Rehearsal and release | Full actual-event rehearsal, operations docs and compatibility matrix | All release-blocking PoCs passed and owner authorizes release |

Initial task: `tasks/S0-001-governance-and-discovery.md`. No business application code, real OBS switching or media development is approved by publishing this plan.

Go vs Node.js, final NDI/SRT choice, OBS scene architecture, hardware minima and latency guarantees are unratified hypotheses, not build requirements. Each phase needs task-specific approval and measured evidence. A merge to `beta` does not imply release to `main`.
