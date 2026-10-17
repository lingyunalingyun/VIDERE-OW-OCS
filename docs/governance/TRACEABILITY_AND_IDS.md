# Requirement, ADR and test IDs — conflict registry v0.1

Known source finding: the user-supplied architecture audit repeats legacy TC identifiers with different meanings. In fault matrix TC-10 covers UI refresh/crash and TC-11 control-service termination; in requirement tracing TC-10 covers cross-source synchronization and TC-11 message authorization. These are distinct scenarios. The source is NOT silently corrected.

Until an approved migration map exists, write `legacy:fault/TC-10`, `legacy:trace/TC-10` etc. Do not use ambiguous old labels as automation keys.

Proposed stable namespaces:
- `REQ-<DOMAIN>-NNN` business requirement
- `NFR-<DOMAIN>-NNN` nonfunctional requirement
- `TC-<DOMAIN>-NNN` test case
- `POC-NNN` real-world concept verification
- `ADR-NNN` ratified architecture decision
- `TASK-SN-NNN` approved task
- `RISK-NNN` risk record

Keep legacy-to-new mapping, owner, decision status, execution status, version and evidence pointer. Test results: NOT_RUN / BLOCKED / FAIL / PASS. A design accepted in principle is not an executed test.
