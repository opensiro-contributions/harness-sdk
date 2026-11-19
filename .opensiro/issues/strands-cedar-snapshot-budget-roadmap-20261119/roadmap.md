# Strands Agents — Capability Roadmap Receipt

- Original repository: strands-agents/harness-sdk
- Original HEAD: 078cbc216608eefe37fdb8bc5e43e3a02985e088
- Observed at: 2026-11-19
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/34e11ec4dd52e1ba3ee0111d8bca73f13918f54f/assessments/st/strands-agents.md
- Accepted assessment blob SHA: 60b16ac6fdbe828d873706786a79e44053ec7446
- Accepted review ref: 08ed4cfd3eb42ae9f668595e675d5f196eee7e44
- Accepted reviewed at: 2026-09-15
- Accepted last checked at: 2026-09-17
- Accepted last checked ref: e7fd22b63f3988997a12fb962144a9663a27d071
- Index commit: 34e11ec4dd52e1ba3ee0111d8bca73f13918f54f
- Accepted historical six-function vector: S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—
- Accepted Profile version: 0.2.1
- Accepted Skills procedure version: 0.3.1
- System in focus: First-party Strands SDK Python and TypeScript Agent, CedarAuthorization, delegated subagents, Swarm/Graph snapshot lifecycle; outside original maintainer governance and external applications
- Matching working fork: opensiro-contributions/harness-sdk
- Fork default baseline HEAD: a97a1642baf663df93fd239d562e8acd3e27d026
- Fork metadata owner control: PAUSE
- Fork metadata attention: DORMANT
- Result: NO_USEFUL_CHANGE
- Final operator decision: NO_GO
- External issue: DRAFT — NOT PUBLISHED
- Fork Issue: NOT PUBLISHED — fork Issues disabled; separate enablement and exact owner approval required
- Cost status: NOT_MEASURED
- Human draft: https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/issue.md
- AI contract: https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/constructor-sufficiency.md

## Identity and pins

The [accepted Index assessment](https://github.com/opensiro/vsm-harness-index/blob/34e11ec4dd52e1ba3ee0111d8bca73f13918f54f/assessments/st/strands-agents.md) at `34e11ec4dd52e1ba3ee0111d8bca73f13918f54f` has blob `60b16ac6fdbe828d873706786a79e44053ec7446`, review 2026-09-15 at original `08ed4cfd3eb42ae9f668595e675d5f196eee7e44` and successful last check 2026-09-17 at `e7fd22b63f3988997a12fb962144a9663a27d071`. Its six-function vector is `S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—`; this is historical, not a November classification. Current original [HEAD](https://github.com/strands-agents/harness-sdk/commit/078cbc216608eefe37fdb8bc5e43e3a02985e088) inspected 2026-11-19. Review age 65 days, latest successful source check age 63 days: recommend independent source-pinned Index semantic reassessment if confident current grades are necessary, without blocking the plan-only negative decision.

## Rights and authority

[Strands contribution guidelines](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/CONTRIBUTING.md) require checking assigned work and obtaining maintainer confirmation before significant code contributions. [AI usage policy](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/team/AI_USAGE_POLICY.md) requires disclosure, human accountability and human-verified quality. License: [Apache-2.0](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/LICENSE.APACHE). Future external CLA/DCO obligations were not independently confirmed; no external code or message is sent. Original and fork exact parent verified. `opensiro-contributions/harness-sdk` is a true writable fork; its existing default branch had no `.opensiro/`, and `opensiro/meta` was confirmed absent before bootstrap. Initializes **PAUSE/DORMANT**; no owner ALLOW, external publication, ongoing effectful work, or organization authority transfer inferred. Fork GitHub Issues are disabled. The user gave no exact title/body approval for publication.

## Existing work / overlap

[Current Python CedarAuthorization](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-py/src/strands/vended_interventions/cedar/cedar_authorization.py#L255-L285) uses per-agent weak-key in-memory counters that load agent state only on first use. Its TypeScript counterpart uses a [WeakMap](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-ts/src/vended-interventions/cedar/cedar.ts#L220-L262). [Issue #6289](https://github.com/strands-agents/harness-sdk/issues/6289) remains OPEN: restoring a snapshot on an already-seen agent can leave stale in-memory counts, while the naïve state-on-every-call fix may reset limits across Swarm/Graph/asTool transitions. [Merged PR #6279](https://github.com/strands-agents/harness-sdk/pull/6279) separately fixed shared counters between parent and child; [merged PR #6290](https://github.com/strands-agents/harness-sdk/pull/6290) added subagent-path tests/docs. Their merged behavior is already present; do not reopen #6278.

Separately, [Graph issue #5341](https://github.com/strands-agents/harness-sdk/issues/5341) remains OPEN: [current source](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-py/src/strands/multiagent/graph.py#L814-L841) clears interrupted nodes before checking execution limits; the expected review node can be skipped on resume/retry. [PR #5342](https://github.com/strands-agents/harness-sdk/pull/5342) and [PR #5496](https://github.com/strands-agents/harness-sdk/pull/5496) are both OPEN and offer overlapping original-native fixes. A node named `review` or human approval does not on its own establish a protected independent S3* audit function.

[Existing Swarm handoff controls](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-py/src/strands/multiagent/swarm.py#L197-L235) provide configurable repetition/oscillation checks as accepted historical S2=C. PR statuses read from first-party GitHub: #6279 and #6290 merged 2026-11-18, #5342 and #5496 open/unmerged as of observation. No duplicate native feature request needed. No product implementation or independent test was executed in OpenSiro.

## Function ownership

S1=A worker operations and S2=C configurable Swarm coordination already established at accepted review. S3=— because no evidenced whole-system autonomous right to select current cross-agent budget or priorities; Cedar's static developer-supplied policy enforces permitted/denied calls but does not own policy selection. S3*=— because a Graph node named `review` is not proof of independent complementary audit. S4=— no prospective external adaptation closure; S5=— parent/application supplies policy. Current source can differ; no silent reclassification.

## Capability priority

**P0: REJECTED new S3=C autonomous budget manager — NO_GO.** The actual operator need concerns correct restore/accounting under existing policy, not autonomous whole-system resource choice. **P1: existing #6289** owner decides native policy-counter semantics, bounded side-effect and regressions for snapshot/handoff/asTool. **P2: NONE.** Existing Swarm S2=C and S1=A excluded from mandatory duplicate C work. No complete first-party S3 decision-owner/feedback port, accepted user need or useful constructor sufficiency case has been established.

## Implementation options

No proposed S3 controller. Source-native path is to decide the explicit policy semantics in [#6289](https://github.com/strands-agents/harness-sdk/issues/6289) and test under current Python/TS suites, preserving merged #6279/#6290 behavior. Do not substitute unreviewed source changes. Independently, #5341 has open overlapping PRs [#5342](https://github.com/strands-agents/harness-sdk/pull/5342) and [#5496](https://github.com/strands-agents/harness-sdk/pull/5496), so do not create a third duplicate. One future operator request establishing a dynamic whole-system manager can motivate a fresh separate GO/NO_GO study, subject to rights.

## Specification and domain alternatives

No evidenced Profile or Skills ambiguity requires a normative change. A new domain-specific fork could independently test adaptive cross-agent budget selection only with a measurable task and lawful rights; no automatic implementation or maintainer adoption follows. Full conditional construction/falsification analysis is in the [AI companion](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/constructor-sufficiency.md).

## Cost experiment

Matched native Cedar accounting correction versus autonomous S3 manager for identical parent-child budget/snapshot task: measure successful correct decisions, unauthorized call prevention, implementation/integration/review/test person-hours, API/model overhead, ongoing regression/maintenance cost. **Cost status: NOT_MEASURED**. Do not claim OpenSiro cheaper or a shipped new capability.

## Delivery and publication

**Result NO_USEFUL_CHANGE; final operator decision NO_GO.** [Human](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/issue.md) and [AI](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/constructor-sufficiency.md) repeat the same historical vector, P0 rejected, P1 native #6289, P2 none, license/authority and no-publication constraints. Proposed fork Issue title: `Strands Agents — snapshot-safe limits vs new S3 control (OpenSiro plan-only)`; full proposed body is [issue.md](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/issue.md). Fork Issues are **disabled**, so publication is additionally blocked pending explicit platform owner enablement; even then publication requires new **exact current-conversation approval** of destination, full title/body. **External issue: DRAFT — NOT PUBLISHED** (no duplicate external issue is warranted while #6289 and #5341 exist). No product edit, additional contribution record, fork/original Issue, public PR, Index grade, tests or cost evidence claimed. **PAUSE/DORMANT**, not user ALLOW. Research is terminal **NO_GO** until genuinely new source-native evidence.
