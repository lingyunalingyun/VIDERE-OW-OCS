# Better OW OCS — Codex workflow audit v0.1

**Review candidate, 2026-10-17. No production implementation or PoC is claimed.**

## Evidence
- Owner explicitly defined project name and lowercase main/beta/alpha roles.
- GitHub initially exposed main, Main, Beta with same initial SHA, default main, only initial README, no app/CI/agent rules, rulesets endpoint [].
- Branch-protection detail request returned 403. This is an access limitation, not proof of disabled protection.
- User-supplied technical Word audit (v0.1-DRAFT) remains a review candidate with unexecuted P-01 spectator / transport / OBS timing PoCs.

## Findings and remedies
- GOV-001 P0: case-sensitive branch conflict. Create canonical lowercase refs; retain legacy refs until approved retirement.
- GOV-002 P0: TC-10/11 legacy collisions. Use descriptive legacy prefixes; approve globally unique test ID migration before generating test automation.
- GOV-003 P0: absent persistent Codex boundaries. Adopt AGENTS + plans + scoped tasks and independent Git approvals.
- GOV-004 P0: draft design status is not implementation/test PASS. Record commands, environment, evidence, or BLOCKED/NOT_RUN.
- GOV-005 P1: stack/CI not established. Do not invent `npm test`, `go test`, etc. until manifests exist.
- GOV-006 P1: rulesets and review checks not demonstrably enforced. Owner configures and verifies after governance PR.
- GOV-007 P1: licenses / competitive clean-room and live OBS credentials. Strict asset ledger, mock/test environment and explicit production permission.

## Decision
A concise root AGENTS.md plus separate PLANS/tasks/policies offers stable instructions without turning a 15-page architecture Word audit into an unreviewable agent prompt. Regular feature work targets beta, high-risk experiments remain on alpha; no auto-promote. This PR is governance-only and requests review; not approval to implement S1, merge main or publish a live system.

## First Codex task
Read root AGENTS, PLANS, governance docs and TASK-S0-001. Discover actual status and source availability, list conflicts and propose S0 next steps. Do not modify app code or remote state. STOP for human acceptance.

## References
- Original user DOCX: OW_Broadcast_Architecture_Audit_v0.1(1).docx
- Codex: https://developers.openai.com/cookbook/articles/codex_exec_plans
- Codex workflow: https://developers.openai.com/cookbook/examples/codex/iterating-development-workflows-with-codex
- GitHub rules: https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/available-rules-for-rulesets
