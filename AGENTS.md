# Better OW OCS — Codex instructions (v0.1 REVIEW CANDIDATE)

## Mission and safety
- Project: Better Overwatch Observer Control System (Better OW OCS), `lingyunalingyun/Better-Overwatch-OCS`.
- Independently develop a local-first esports observer/broadcast control system. Do not copy code, assets, layouts, fonts or naming conventions from competing projects.
- Do not access game process memory, modify the game client, bypass anti-cheat/protections, or invent a supposedly official game-data API.
- Project is NOT production ready. Do not claim actual OBS/NDI/SRT/Overwatch/hardware tests passed unless those exact tests were run with recorded evidence.

## Grounding and decision hierarchy
1. Explicit human approval and approved individual task contract, limited to its scope.
2. Accepted ADRs and ratified requirement/interface specifications.
3. `PLANS.md`, relevant `tasks/` documents and verified current repository reality.
4. Review drafts are evidence of a proposal, NOT proof of accepted design or implementation.

The source Word audit `OW_Broadcast_Architecture_Audit_v0.1(1).docx` is an unratified review candidate. It has conflicting legacy test numbers (notably TC-10/11). See `docs/governance/TRACEABILITY_AND_IDS.md`. Never silently resolve conflicting IDs or turn A/C/P design labels into test PASS. If the source document is not present in your task environment, explicitly report it as unavailable; do not invent its content.

## Canonical branches
- Exact lowercase refs: `main` stable, `beta` integration, `alpha` high-risk experiments.
- Old `Main` and `Beta` are unrelated, noncanonical refs; never use them as targets.
- Routine code from `beta` via `feature/*`, `fix/*`, `poc/*`, `docs/*` and a reviewed PR back to `beta`.
- Experiments from `alpha`, PR to `alpha`; transfer only reviewed, validated patches into a NEW branch based on `beta`. No wholesale auto-merge.
- A release is a separate approved PR from `beta` to `main`.
- No direct write to `main`, force push, branch deletion, reset of user work, rewrite of shared history, merge, remote push, PR, tag, release or deployment without an explicit authorization covering that operation. Git status must be checked first.

## Standard work protocol
1. DISCOVER: read applicable AGENTS files, existing code, specs, ADR, phase and task. Inventory git status, real commands, dependencies and tests.
2. PLAN: state task ID, goal, approved paths, non-goals, risk, intended files, acceptance criteria and test plan. For cross-module, risky or architecture changes prepare an ExecPlan under `tasks/` and get approval before modifying code.
3. IMPLEMENT: remain within scope. Do not introduce dependencies, change tech stack, production OBS configuration, network settings or architecture without separate review. Preserve unrelated changes.
4. VERIFY: use only build/test commands that actually exist. Record exact command, environment, exit code, logs and limits. `PASS` must be observed; use `FAIL`, `BLOCKED`, `NOT_RUN` accurately. Mock OBS is NOT real OBS.
5. REVIEW: inspect diff, error paths, security, secrets, concurrency, version contracts, tests and migration. No deletion of tests merely to appear green.
6. REPORT & STOP: provide task/branch, changed paths, results, unexecuted tests, risks, git state and required next approval. Do not autonomously begin another phase.

## Hard architecture invariants
- Control plane and media plane stay separate. Business API MUST NOT carry raw audio/video frames.
- Browser/UI never owns authoritative Match or Program state; editing and Program publication are separate.
- TAKE has unique commandId, actor/session, expectedRevision, expiry, deduplication and reconciliation. OBS actual Program is authoritative for its current scene; OBS response is not proof the viewers saw a frame.
- On OBS disconnection/unknown outcome, reconcile actual state before subsequent actions; do not automatically replay expired TAKE commands.
- Overlay loads a published Program snapshot on initial load/reload, never unsaved draft. Restoring a project cannot execute TAKE.
- Media health without frame evidence is UNKNOWN, not HEALTHY. Game spectator synchronization requires real-game measurements.
- MVP does not build a new video codec or multimedia compositor.
- OBS secrets and stream keys stay out of UI, source, exported project files and ordinary logs; authenticate/authorize each control message.

## Verification and handoff
- Use unique requirement/test IDs from `docs/governance/TRACEABILITY_AND_IDS.md`; every blocking requirement traces to tests and evidence.
- Distinguish static/unit/contract/mock-OBS/real-OBS/media-PoC/security/rehearsal tests.
- Never declare release ready without accepted technical decisions and real P0 PoC evidence.
- Final report: task ID and branch; files changed; tests run with command/result; tests NOT_RUN/BLOCKED and why; risks; Git commit/push/PR/merge state; next approval needed.
