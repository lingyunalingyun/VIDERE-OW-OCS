# Branch and release policy v0.1 (review candidate)

Canonical, case-sensitive long-lived refs: `main` stable, `beta` integration/QA, `alpha` risky experimentation. Legacy `Main` and `Beta` stay untouched pending explicit deletion/retirement approval.

- Normal work branches from `beta`; feature/fix/docs/poc PR returns to `beta`.
- Experimental work branches from `alpha`; reviewed experiment PR returns to `alpha`.
- To promote experiment: branch from `beta`, selectively reimplement/cherry-pick only validated parts, then PR to `beta`; never bulk-auto-merge all of `alpha`.
- Stable release: only a separately approved `beta` to `main` PR with CI/test evidence, no P0 defects, required real PoC/rehearsal, licensing and rollback review.
- Hotfix: branch from `main`, explicit approval to patch `main`, then backport into `beta`.
- Never force push/delete branches/merge/release or touch production OBS without scoped authorization.

Owner setting recommendation (not proof of actual configuration): GitHub Settings → Rules → Rulesets: protect `main`/`beta` with PR requirement, no force push or deletion, and **existing** passing CI checks once implemented. Avoid selecting checks that don't exist. Configure appropriate review policy for actual team size and verify enforcement. Branch protection API may be inaccessible (403) via GitHub App; don't assume status.
