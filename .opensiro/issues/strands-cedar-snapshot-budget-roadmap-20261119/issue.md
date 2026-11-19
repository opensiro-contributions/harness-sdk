# Strands Agents — snapshot-safe limits vs new S3 control (OpenSiro plan-only)

**OpenSiro research · PLAN_ONLY / NO_USEFUL_CHANGE · Human Issue DRAFT — NOT PUBLISHED.**  
**Final operator decision: NO_GO — do not construct a new autonomous S3 controller for this evidence.**  
**Full agent/developer contract:** [constructor-sufficiency.md](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/constructor-sufficiency.md). **Receipt:** [roadmap.md](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md).

## 1. Why OpenSiro and central accepted VSM assessment

OpenSiro tests whether reusable VSM-informed organizational specifications can standardize AI-agent harness development and reduce total implementation, integration, testing and maintenance costs. This remains an unmeasured hypothesis; original Strands maintainers are not asked to adopt the VSM model. This case decides whether the current authorization/snapshot incidents justify an additional developer-composable autonomous S3 owner rather than a narrow source-native correction.

> **Historical accepted Index baseline, NOT proposed new grades:** `S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—`. [Immutable Index assessment](https://github.com/opensiro/vsm-harness-index/blob/34e11ec4dd52e1ba3ee0111d8bca73f13918f54f/assessments/st/strands-agents.md); blob `60b16ac6fdbe828d873706786a79e44053ec7446`; canonical review **2026-09-15** at [`08ed4cfd3eb42ae9f668595e675d5f196eee7e44`](https://github.com/strands-agents/harness-sdk/commit/08ed4cfd3eb42ae9f668595e675d5f196eee7e44); supported source check **2026-09-17** at [`e7fd22b63f3988997a12fb962144a9663a27d071`](https://github.com/strands-agents/harness-sdk/commit/e7fd22b63f3988997a12fb962144a9663a27d071); historical Profile **0.2.1** and Skills procedure **0.3.1**.

| Function | Historical state | Why it matters here |
| --- | --- | --- |
| S1 · Operations | **A** | Tool-using agents perform work; no compulsory C extension. |
| S2 · Coordination | **C** | Swarm config provides handoff anti-oscillation; already a C path for this disturbance. |
| S3 · Current whole-system control | **—** | No witnessed agent owner deciding overall budget, priorities and capacities; static Cedar enforcement is not that decision. |
| S3* · Independent audit | **—** | A named review node/approval does not prove a protected complementary audit channel. |
| S4 · Future adaptation | **—** | Dynamic handoff and snapshot restore are not external/future adaptation closure. |
| S5 · Identity / policy | **—** | Application supplies policy; static authorization and human limits are not an autonomous S5 identity decision. |

**Observed original:** [`078cbc216608eefe37fdb8bc5e43e3a02985e088`](https://github.com/strands-agents/harness-sdk/commit/078cbc216608eefe37fdb8bc5e43e3a02985e088), **2026-11-19**. **Accepted Index:** `34e11ec4dd52e1ba3ee0111d8bca73f13918f54f`; historical review age **65 calendar days**, and latest accepted successful source check age **63 days**; an Index-owned semantic reassessment is recommended before confident new grades, not a roadmap stop. **System-in-focus:** supported first-party Python/TypeScript SDK Agent + Swarm/Graph with `CedarAuthorization` and snapshot lifecycle; external maintainer governance and host/application-defined policy decisions excluded. **Matching fork:** [opensiro-contributions/harness-sdk](https://github.com/opensiro-contributions/harness-sdk), correct parent, initialized as **PAUSE/DORMANT**, not permission for product engineering. [Strands contribution guidelines](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/CONTRIBUTING.md) require checking assigned work and obtaining maintainer confirmation before significant code contributions. [AI usage policy](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/team/AI_USAGE_POLICY.md) requires disclosure, human accountability and human-verified quality. License: [Apache-2.0](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/LICENSE.APACHE). Future external CLA/DCO obligations were not independently confirmed; no external code or message is sent.

## 2. Operator need, hypothesis and decision

**Observed user task:** a developer applies a tool call-count limit to an agent, delegates to subagents and restores a snapshot. Calls that should be permitted/denied under the selected per-agent or cross-delegation policy must stay consistent. A stale in-memory counter after restore can wrongly deny a tool; an apparent fix can also allow more tool calls than intended across repeated Swarm/Graph executions. The complaint is documented in [#6289](https://github.com/strands-agents/harness-sdk/issues/6289).

**Proposed P0 S3 autonomous budget manager: REJECTED.** The current issue asks to define correct *existing policy-counter semantics* across restore, not for an autonomous controller selecting/rationalizing whole-system capacity or priorities. A deterministic, source-native fix with regression tests is the simpler operator path. A policy limit is enforcement, not the organization-level S3 right.

**Best native option:** reuse [#6289](https://github.com/strands-agents/harness-sdk/issues/6289)'s three identified alternatives. Its author favors explicit reset-then-restore; this is an **issue proposal**, not a maintainer-approved choice. Preserve limits in repeated Swarm/Graph/asTool calls, and write tests before adopting any strategy. No speculative new S3 API.

## 3. First-party existing work vs gap

| Native feature / issue | Status at observation | Meaning |
| --- | --- | --- |
| [Cedar counters](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-py/src/strands/vended_interventions/cedar/cedar_authorization.py#L255-L285) | **SHIPPED** per-agent `WeakKeyDictionary` with one-time state load, and TypeScript `WeakMap` | Counters enforce supplied policies; no independent agent-selected whole-system S3 decision |
| [#6278](https://github.com/strands-agents/harness-sdk/issues/6278), [PR #6279](https://github.com/strands-agents/harness-sdk/pull/6279) | **ISSUE CLOSED; PR MERGED 2026-11-18** | Previously shared parent/child counts were fixed; do not duplicate |
| [PR #6290](https://github.com/strands-agents/harness-sdk/pull/6290) | **MERGED 2026-11-18** | Subagent-path regression tests/doc were added |
| [#6289](https://github.com/strands-agents/harness-sdk/issues/6289) | **OPEN** | Source-native decision needed: restore semantics must not weaken enforcement across reused agents |
| [#5341](https://github.com/strands-agents/harness-sdk/issues/5341), [PR #5342](https://github.com/strands-agents/harness-sdk/pull/5342), [PR #5496](https://github.com/strands-agents/harness-sdk/pull/5496) | **ISSUE OPEN; TWO OVERLAPPING PRs OPEN** | Separate Graph interrupt/resume bug; reuse competing native fixes rather than duplicate |
| [Swarm handoff regulation](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-py/src/strands/multiagent/swarm.py#L197-L235) | **SHIPPED/configurable** | Existing S2=C historical line of evidence, not a new S3 controller |

[Current Python CedarAuthorization](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-py/src/strands/vended_interventions/cedar/cedar_authorization.py#L255-L285) uses per-agent weak-key in-memory counters that load agent state only on first use. Its TypeScript counterpart uses a [WeakMap](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-ts/src/vended-interventions/cedar/cedar.ts#L220-L262). [Issue #6289](https://github.com/strands-agents/harness-sdk/issues/6289) remains OPEN: restoring a snapshot on an already-seen agent can leave stale in-memory counts, while the naïve state-on-every-call fix may reset limits across Swarm/Graph/asTool transitions. [Merged PR #6279](https://github.com/strands-agents/harness-sdk/pull/6279) separately fixed shared counters between parent and child; [merged PR #6290](https://github.com/strands-agents/harness-sdk/pull/6290) added subagent-path tests/docs. Their merged behavior is already present; do not reopen #6278. Separately, [Graph issue #5341](https://github.com/strands-agents/harness-sdk/issues/5341) remains OPEN: [current source](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-py/src/strands/multiagent/graph.py#L814-L841) clears interrupted nodes before checking execution limits; the expected review node can be skipped on resume/retry. [PR #5342](https://github.com/strands-agents/harness-sdk/pull/5342) and [PR #5496](https://github.com/strands-agents/harness-sdk/pull/5496) are both OPEN and offer overlapping original-native fixes. A node named `review` or human approval does not on its own establish a protected independent S3* audit function.

## 4. P0 / P1 / P2 and minimum sufficiency

| Priority | User-facing objective | Decision |
| --- | --- | --- |
| **P0: new S3=C constructor** | Developers compose an autonomous whole-system budget decision actor that chooses lawful capacity/priority changes and returns feedback into later runs | **NO_GO**: no distinct operator need, rights/owner, decision port or measurable extra outcome beyond static policy correctness |
| **P1: native Cedar restore correctness** | Calls after snapshot restore reflect an explicitly chosen policy without accidental denial or silently restarted rate limits in Swarm, Graph or asTool | Reuse [#6289](https://github.com/strands-agents/harness-sdk/issues/6289), maintainer decision and focused existing test suites; **no new OpenSiro PR** |
| **P2: optional secondary function** | Not evidenced | **NONE** |

**C sufficiency (negative):** current code supplies policy enforcement plus event transport but no legitimate developer-composed S3 autonomous decision actor, selectable whole-system alternatives, enforceable application-wide budget revision or returned control-feedback closure. Merely fixing counter caching cannot establish S3=C. Full conditional adequacy/negative acceptance is in the [AI/developer contract](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/constructor-sufficiency.md). Current S1=A and S2=C are excluded from mandatory extra C work.

## 5. Proposed native acceptance and stop conditions

**Native tests not executed by OpenSiro.** For the source-owned P1 repair, reproduce same-agent mid-life `load_snapshot`, per-agent parent/child isolation, two handoffs returning to an agent, repeated `as_tool` calls and Graph reset. Verify accepted calls, denied calls, persistent per-agent state, and that no reset accidentally expands permissions. Compare the three #6289 choices under identical cases. A total-tree budget is not automatically implied by per-agent limits: require a separate policy contract first.

A *future* S3=C hypothesis would require an actual operator needing dynamic whole-system budget choices, an authenticated independent developer-composed autonomous decision owner, supported first-party decision/feedback APIs, enforced cross-agent effects and native positive, unauthorized, stale-context and no-owner cases. If only counters and policies remain, **STOP**: do not add an S3 agent.

## 6. Independent paths

- **Original-native:** #6289 is the correct decision; #5341 already has PRs #5342/#5496. Respect maintainer review and existing work; no new external Issue/PR/comment.
- **Normative feedback:** no VSM Profile or Skills methodology defect established; do not change semantics merely to classify Cedar differently.
- **Domain-scoped fork:** optional only on a later independently evidenced agent-owned whole-system budget requirement; not part of this NO_GO decision.

## 7. Cost hypothesis

Matched experiment: one workflow with parent+child agents, snapshot restore and repeated calls, same correctness/policy constraints. Measure effort to fix/test Cedar natively versus adding autonomous S3 decision machinery: implementation, integration, human review, test runs, latency, token spend, maintenance and policy failures. **Cost: NOT_MEASURED**; no claim VSM is cheaper or already adopted.

## 8. Decision, rights and handoff

**Result: NO_USEFUL_CHANGE. Final operator decision: NO_GO.** Do **not** implement a speculative S3 controller, duplicate existing PRs, change Index grade or publish outside OpenSiro. The native #6289 correctness issue is genuine but remains an original-owned decision. [AI contract](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/constructor-sufficiency.md) and [receipt](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md) repeat the same baseline and priorities.

**Publication: NOT PUBLISHED.** The [verified fork](https://github.com/opensiro-contributions/harness-sdk) currently has GitHub Issues **disabled**; enabling them requires a separate owner/provider decision. Even after enabling, posting this fork Issue requires **exact current-conversation approval of target, title and full body**. Original issues and PRs remain original-owned; no duplicate original Issue is appropriate. No product changes or tests executed.

**AI disclosure:** Drafted using AI assistance and inspected first-party public evidence. No independent human verification, native test execution or cost savings is claimed.
