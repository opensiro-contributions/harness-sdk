# Strands — snapshot-safe authorization and conditional S3 constructor sufficiency

**Level 2 AI/developer contract · PLAN_ONLY / NO_USEFUL_CHANGE · DRAFT — NOT PUBLISHED.** [Human Issue draft](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/issue.md) · [receipt](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md).
**Final operator decision: NO_GO** — do not implement a new S3 control agent for the current task.

## Functional classification and accepted historical Index

**Accepted Index:** `S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—`; [pinned assessment](https://github.com/opensiro/vsm-harness-index/blob/34e11ec4dd52e1ba3ee0111d8bca73f13918f54f/assessments/st/strands-agents.md), blob `60b16ac6fdbe828d873706786a79e44053ec7446`, reviewed **2026-09-15** at `08ed4cfd3eb42ae9f668595e675d5f196eee7e44` (Profile 0.2.1 / Skills 0.3.1), last successful source check **2026-09-17** at `e7fd22b63f3988997a12fb962144a9663a27d071`; original [HEAD `078cbc216608eefe37fdb8bc5e43e3a02985e088`](https://github.com/strands-agents/harness-sdk/commit/078cbc216608eefe37fdb8bc5e43e3a02985e088) checked **2026-11-19**. Last successful check age **63 days**: source-pinned Index reassessment recommended but does not block provisional plan-only research. Historical grades are not current HEAD classifications.

| VSM function | Observed organizational owner | Inclusion or exclusion |
| --- | --- | --- |
| S1=A | Tool-using agent operational work | Already agent-owned; no mandatory C |
| S2=C | Swarm configurable anti-oscillation / handoff coordination | Already composable; retain |
| S3=— | No first-party whole-system autonomous owner of capacity/priority decisions in accepted scope; Cedar enforces static supplied limits | **P0 NO_GO**: static limit correctness ≠ new agent-controlled S3 |
| S3*=— | Graph `review` nodes can be skipped because of a state bug, but no protected complementary independent auditor is verified | Do not infer S3* from node names/interrupts |
| S4=— | Snapshot restore/handoffs address current execution, not future external adaptation intelligence | No S4 hypothesis |
| S5=— | Policy/identity supplied by parent/application | Preserve legitimate policy authority |

**System-in-focus:** first-party Python and TypeScript SDK, `Agent`, default delegated subagents, `CedarAuthorization`, Swarm/Graph snapshot/resume. No private app policies, maintainer governance, external deployment or uninstalled actor is inside this boundary. Original [Apache-2.0](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/LICENSE.APACHE), [contribution guidelines](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/CONTRIBUTING.md), [AI policy](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/team/AI_USAGE_POLICY.md). Matched fork `opensiro-contributions/harness-sdk` parent verified; initial control **PAUSE/DORMANT**. No new public communication.

## 1. Actual task / negative construction counterfactual

**Operator:** application developer defines `call_count < 3` and expects per-agent rate-limiting across subagent handoffs and snapshot restoration, under the explicitly configured policy. Developer needs a predictable answer to **what is counted before and after restore**, not a new AI manager that chooses policy. [#6289](https://github.com/strands-agents/harness-sdk/issues/6289) reproduces stale in-memory count after `agent.load_snapshot` and warns that always trusting restored agent state could allow repeated tool calls beyond the intended limit in Swarm/Graph/asTool.

**Remove a proposed S3 controller:** native policies and cache-reset/restore semantics can still decide permit/deny, so the same useful result remains possible without an autonomous S3 actor. This rejects the constructive owner counterfactual. A runtime rejecting a tool action is not necessarily owner of resource-allocation decisions.

**P0: REJECTED proposed S3=C autonomous budget manager. P1: existing-native #6289 correctness/contract; P2: NONE.**

## 2. Current first-party source vs existing PR state

| Evidence element | Main at observed SHA | Competing source state |
| --- | --- | --- |
| Python Cedar counter cache | [`WeakKeyDictionary` keyed by Agent, `_counts_for`](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-py/src/strands/vended_interventions/cedar/cedar_authorization.py#L255-L285) loads from `agent.state` only when cache entry absent | [#6278](https://github.com/strands-agents/harness-sdk/issues/6278) CLOSED; [PR #6279](https://github.com/strands-agents/harness-sdk/pull/6279) **MERGED** 2026-11-18 |
| TypeScript Cedar counterpart | [`WeakMap` and reset](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-ts/src/vended-interventions/cedar/cedar.ts#L220-L265) | [PR #6290](https://github.com/strands-agents/harness-sdk/pull/6290) **MERGED** 2026-11-18 with subagent-path tests |
| Mid-life snapshot restore | No refresh of a previously cached per-agent count on loading replacement state in inspected Cedar code | [#6289](https://github.com/strands-agents/harness-sdk/issues/6289) **OPEN**, with three explicit options; none adopted by this case |
| Graph interrupted node recovery | [Graph `_execute_graph`](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-py/src/strands/multiagent/graph.py#L814-L841) clears pending nodes before limit check | [#5341](https://github.com/strands-agents/harness-sdk/issues/5341) **OPEN**; [PR #5342](https://github.com/strands-agents/harness-sdk/pull/5342) and [PR #5496](https://github.com/strands-agents/harness-sdk/pull/5496) **OPEN**, overlap |
| Peer oscillation | [Swarm `should_continue`](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/strands-py/src/strands/multiagent/swarm.py#L197-L235) supports configurable repetition detection | Matches accepted S2=C; no new S3 assertion |

**Verified PR heads at observation**: #6279 `7ef22f010d47c8cca83ed15f1da5e7086a2db48c`; #6290 `0cc3343bb11d5d7f604e8e72eea5d997e86db5af`; #5342 `54f0052cda9233bb7cc6a4327980ffa387093aaf`; #5496 `36504caf3ab5acca93ac85e957c5491c0ce9c669`. Distinguish already merged versus open: **do not treat open fixes as shipped**. Test outcomes reported in upstream PR descriptions are source reports, not tests executed by OpenSiro.

## 3. What a genuinely demanded S3=C future constructor would require

**Not an approved implementation.** If a real operator later needs an agent to choose/revise shared current capacity under a legitimate parent-granted envelope, a future source-native design must include:
1. **Whole-system disturbance signal**: shared run budget/capacity/priority conflict across multiple supported S1 agents, beyond a single static tool-count threshold.
2. **Configurable decision owner**: application can independently compose an autonomous S3 actor with narrowly defined selectable options (rebalance budgets, postpone/stop work, preserve a reserve) and auditable inputs; removing the actor removes the discretionary choice while policy enforcement remains.
3. **Authorized effect**: enforce overall limits and priority decisions at supported Swarm/Graph/subagent execution, not just a local hook; distinguish underlying policy owner from enforcement.
4. **State/version lifecycle**: counters, snapshot restores, handoffs and decisions cannot reset policy or duplicate effects; stale/unauthorized choices reject fail-closed.
5. **Returned feedback**: selected allocation changes actual next scheduled tasks/calls and returns receipt/usage into subsequent controller decisions, with a supported install path in both claimed SDK languages.
6. **Native positive and negative proof**: show materially different operator outcome against smallest static Cedar policy/manual workaround; protect S5 parent control and S2 handoff invariants.

**No evidenced first-party developer-composable S3 owner port or concrete external/user counterfactual supports this full set today.** Adding these would invent an SDK product direction. Therefore NO_GO; no qualified P0 constructor or claim of C sufficiency.

## 4. Priority and native policy decision

**P0:** NO_GO; no new S3. **P1:** allow upstream owners to choose among #6289's reset-then-restore, state-on-every-call or user-restore-only semantics. Treat the issue author's preference as a proposal, not maintainer mandate. Focus on complete per-agent/subagent tool-call accounting, independently test policy leakage across cycles, and fix under original repository rules only if requested. **P2:** NONE. This plan creates no product branch, feature or contribution record.

The Graph review-skip fix is a separate original-owned issue with *two open competing PRs*; choose one through maintainer review. The skipped `review` node is an execution-consistency bug; it does not prove S3* independence or justify another watchdog/agent.

## 5. Optional secondary C path

**NONE**: S3* audit, S4 future adaptation, and S5 policy are not evidenced for a new constructor by these issues. No forced A→C or grade maximization.

## 6. Proposed source-native acceptance matrix (NOT EXECUTED)

| Case | Expected native evidence | Failure / falsification |
| --- | --- | --- |
| AC-01 Snapshot restore correctness | On same Agent, after two calls, restore snapshot with one call; expected subsequent permit/deny follows documented semantics, Python and TS | In-memory count silently overrides explicit chosen restore semantics |
| AC-02 Parent-child isolation | Parent + subagent share handler instance; per-agent counts remain independent as intended by merged #6279 | Child exhausts parent's local limit or state leaks |
| AC-03 Swarm/Graph continuity | Revisit same logical agent across handoff/reset with identical call-count policy; no unintended budget increase | New fix permits more calls by restarting counts |
| AC-04 asTool continuity | Repeated child-as-tool calls under selected `preserve_context` policy; correct counting across calls | Each invocation restarts limit unexpectedly |
| AC-05 Unauthorized or invalid state | Stale snapshot or unauthorized manual mutation cannot silently escalate permitted calls under supported policy; fail closed with clear error/report | Silent success, inconsistent denial, no counter proof |
| AC-06 Independent Graph issue | Interrupt review node, hit execution cap, retry: review node must run or remain visibly pending; compare original PR #5342 vs #5496 | Graph reports complete with review not run |
| AC-07 Hypothetical S3 only | Developer supplies distinct legitimate autonomous manager; different lawful allocation changes later run and yields usage feedback; remove manager to test contrast | Same decisions from deterministic gate: not S3=C |

Run only original-native commands from [CONTRIBUTING](https://github.com/strands-agents/harness-sdk/blob/078cbc216608eefe37fdb8bc5e43e3a02985e088/CONTRIBUTING.md) if a separately authorized Upgrade proceeds: Python focused `strands-py` pytest/hatch and TypeScript unit tests; source-pinned baseline vs proposed fix. None were run for this plan-only decision.

## 7. Evidence / cost / stop

**Evidence owner:** original maintainers own #6289's counter contract and reviews of #5342/#5496; application user owns requirements for parent-vs-tree-wide budget and decision delegation; Index/Skills own any formal function reassessment. Current original reviewed at [`078cbc216608eefe37fdb8bc5e43e3a02985e088`](https://github.com/strands-agents/harness-sdk/commit/078cbc216608eefe37fdb8bc5e43e3a02985e088); accepted 2026-09-15 grading + 2026-09-17 supported check are historical. Re-assessment advisory at >30 days; no automatic grade change.

**Cost comparison:** static native Cedar correction versus hypothetical autonomous S3 manager under same policy correctness, task load and safety: count developer engineering hours, tests, integration, human reviews, per-run overhead and maintenance/regression effort. **NOT_MEASURED.**

**Final decision: NO_GO / NO_USEFUL_CHANGE.** Do not implement a new S3 controller, external PR or issue, contributor claim, Index grade, unreviewed AI patch or S3* gate. Already-merged PRs need no duplicate, open competing PRs remain original-owned. This [AI contract](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/constructor-sufficiency.md), [Human](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/issue.md) and [receipt](https://github.com/opensiro-contributions/harness-sdk/blob/opensiro/meta/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md) share the exact accepted vector/P0/P1/P2.

**Publication:** fork GitHub Issues currently disabled; external/public communication needs separate exact approval and, for fork Issue, enablement. **NOT PUBLISHED**.
