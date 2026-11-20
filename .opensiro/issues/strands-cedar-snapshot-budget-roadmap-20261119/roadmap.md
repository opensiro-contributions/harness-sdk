# Strands Agents — Capability Roadmap Receipt · Wave 4 neutrality rerun

- Receipt contract: proposal-gate
- Original repository: strands-agents/harness-sdk
- Original HEAD: 3e5217136b80ddcd743099ad5d11a926301c8c04
- Observed at: 2026-11-20
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/0a4ffd542afae11b048918167f7791f26db167bb/assessments/st/strands-agents.md
- Accepted assessment blob SHA: 60b16ac6fdbe828d873706786a79e44053ec7446
- Accepted review ref: 08ed4cfd3eb42ae9f668595e675d5f196eee7e44
- Accepted reviewed at: 2026-09-15
- Accepted last checked at: 2026-09-17
- Index commit: 0a4ffd542afae11b048918167f7791f26db167bb
- Accepted VSM vector: S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—
- Accepted historical six-function vector: S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—
- Accepted Profile version: 0.2.1
- Accepted Skills procedure version: 0.3.1
- System in focus: First-party Strands Python and TypeScript runtime/SDK with Agent, tool interventions, Swarm and Graph; external application-level policy and maintainer governance excluded
- Matching working fork: opensiro-contributions/harness-sdk
- Fork metadata owner control: ALLOW
- Fork metadata attention: ACTIVE
- Repository-wide source map: SDK Python/TypeScript agents, Swarm/Graph, Cedar interventions/hooks, Harness and CLI as entry points; site/docs, original tests, design and contributor policies inspected; separate Evals, CI and external deployments excluded
- Evaluation object: Optional reusable source-native cross-agent current resource-allocation constructor, NOT a correction to Cedar call_count snapshot semantics
- Existing-work overlap: Cedar per-agent limits and #6289 snapshot issue, merged #6279 and #6290; no evidenced shipped model-owned adaptive shared allocation controller
- Our on-top contribution: Hypothetical opt-in supervisor actor plus shared monotonic ledger and fail-closed per-agent intervention to revise cross-agent allocations without changing parent ceilings
- Incremental benefit: An assembled developer could autonomously reprioritize constrained shared capacity between S1 workers using observed usage and enforce decisions on later work
- Decision scope: Architecture constructibility only; not maintainer desirability, deployment, native bug fix, Index regrade or cost claim
- Priority rationale: S3 is first because dynamic cross-agent shared-budget regulation has a source-native intervention/feedback integration path; S2 already C, other functions lack a better bounded first-party construction hypothesis
- Target transition: S3=— -> S3=C
- P1 dependencies: Revisioned durable ledger, concurrency-safe reservations, fail-closed authorization, parent ceiling, child/snapshot/reset semantics, Python/TS parity and native tests
- P2 optional: NONE
- Proposed C construction: Developer-composed model-owned S3 shared-budget supervisor using first-party Agent and intervention hooks; decision writes bounded allocations; per-agent enforcement and aggregate usage feed later supervisor choices
- C sufficiency falsifier: If current first-party APIs already provide equivalent model-owned cross-agent allocation closure, or complete enforcement cannot be achieved inside the supported/legitimate authority boundary, qualification fails
- Scenario basis: HYPOTHETICAL
- Proposal-stage decision: GO
- Research disposition: NEEDS_EVIDENCE
- Proposed validation: Compare native static Cedar control vs opt-in S3 supervisor in a shared-ceiling adversarial concurrency/snapshot replay; require changed allocations, no overspend and feedback-driven next decision
- Validation state: NOT_RUN
- Proposal falsifier: A source-native-only A0 baseline achieves the same dynamic allocation choices and closure without an added S3 construct, or any managed tool route can bypass the revisioned budget gate
- Result: NEEDS_EVIDENCE
- Final operator decision: GO
- External issue: DRAFT — NOT PUBLISHED
- Fork Issue: NOT PUBLISHED — fork Issues disabled and exact approval absent
- Cost status: NOT_MEASURED
- S1 disposition: A existing operational model/tool action loop, NO_TARGET
- S2 disposition: C existing Swarm configured anti-oscillation, NO_TARGET
- S3 disposition: Historical —; current static per-agent enforcement not a discretionary shared allocation owner; P0 proposed C
- S3* disposition: Historical —; same-path logging and named review nodes do not prove independent audit, NO_TARGET for this case
- S4 disposition: Historical —; current-call routing/fallback does not independently establish external prospective adaptation, DEFER
- S5 disposition: Historical —; source application/parent owns global policy and budget ceilings, NO_TARGET

## Identity and pins

Canonical accepted [included Index](https://github.com/opensiro/vsm-harness-index/blob/0a4ffd542afae11b048918167f7791f26db167bb/assessments/st/strands-agents.md) at `0a4ffd542afae11b048918167f7791f26db167bb`, blob `60b16ac6fdbe828d873706786a79e44053ec7446`, review `08ed4cfd3eb42ae9f668595e675d5f196eee7e44` dated 2026-09-15, Profile 0.2.1 and Skills 0.3.1. Catalog identity and review ref match; current original is [main@3e5217136b80](https://github.com/strands-agents/harness-sdk/commit/3e5217136b80ddcd743099ad5d11a926301c8c04), reviewed separately. Six historical grades are NOT changed. Current Profile 0.2.4 was read for autonomy semantics, not substituted for historical grading. [Sealed independent first-pass](https://github.com/opensiro/upstream/issues/58#issuecomment-7042836907) predates any reading of the [historical NO_GO receipt](https://github.com/opensiro-contributions/harness-sdk/blob/b17a07332bffa1b5eecfc0c24da47c721ec1d3a4/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md).

## Rights and authority

Original [Apache-2.0](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/LICENSE.APACHE); [contributor instructions](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/CONTRIBUTING.md) and [AI usage policy](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/team/AI_USAGE_POLICY.md) remain relevant to any future code/publication. This is PLAN_ONLY on a verified true fork of strands-agents/harness-sdk. `opensiro/meta` owner state was re-read as `ACTIVE / ALLOW` before the write. This authorizes internal metadata work, NOT third-party publication, fork public Issues, execution in original, or policy/S5 delegation. Parent/developer fixes total budget and permitted actions; an optional supervisor may only allocate within that envelope. No stakeholder demand or maintainer adoption is inferred (NOT_STATED).

## Existing work / overlap

Track A first party: [Python Cedar](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/vended_interventions/cedar/cedar_authorization.py#L160-L285) and [TypeScript Cedar](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-ts/src/vended-interventions/cedar/cedar.ts#L175-L272) authorize a tool before executing it, persisting call counts in per-agent state but caching in memory. Merged [#6279](https://github.com/strands-agents/harness-sdk/pull/6279) isolates agent counters; merged [#6290](https://github.com/strands-agents/harness-sdk/pull/6290) adds delegated tests. Open [#6289](https://github.com/strands-agents/harness-sdk/issues/6289) identifies the snapshot reset tradeoff; [#6381](https://github.com/strands-agents/harness-sdk/issues/6381) asks TS reset-all parity. Those are genuine native bugs/API issues, not substitute proof of dynamically allocating a pooled budget. [Swarm regulation](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/multiagent/swarm.py#L197-L235), [Graph execution](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/multiagent/graph.py), [Agent lifecycle](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/agent/agent.py), [intervention](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/interventions/handler.py#L29-L108) and [hook events](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/hooks/events.py#L221-L285) provide lower-level supported paths. First-party [model routing](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-ts/src/models/routing/router.ts) is per-request selection, not S3 shared capacity closure. Issues are not assumed shipped; no native tests were run here.

## Function ownership

S1 operational Agent model and tools are first-party; S2 configurable Swarm handoff oscillation limit is already a first-party C construction. S3 Cedar deterministic limits enforce an application-owned rule; they do not select current *cross-agent* priorities. S3* independent complementary audit not shown by Graph node names or ordinary logging. S4 model routing is current-call provider handling, not demonstrated external prospective planning and response. S5 remains with the lawful parent/application policy holder. Adjacent `team/` maintainer decision docs, CI, external Evals and third-party production do not confer S5 on the SDK runtime. These are roadmap dispositions, NOT updated Index grades.

## Capability priority

**P0: S3=— -> S3=C, proposal-stage GO / research NEEDS_EVIDENCE.** Define a shared resource budget across two or more first-party agent operations; unlike Cedar's per-agent threshold, the bounded supervisory agent actively reallocates unused/contested capacity based on observed demand and priority without changing parent ceilings. P1 is an atomic persistent ledger and source-native coverage of child calls/restarts; P2 NONE. S2 already C; no S3* or S4 extra project invented. The constructor is a testable hypothesis, not proven useful or requested by maintainers.

## Parallel contribution-on-top review

| C sufficiency link | Track A: existing first-party path | Track B: smallest on-top construction | Falsifier |
| --- | --- | --- | --- |
| Current whole-system view | Cedar per-agent [call counts](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/vended_interventions/cedar/cedar_authorization.py#L160-L285) and [AfterToolCall event](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/hooks/events.py#L221-L285) | Shared monotonic ledger aggregates by agent, task and budget window independently of agent snapshot state | Native shared ledger already exists with equivalent state |
| Decisive autonomous choice | Static policies and parent configuration; no observed model-owned shared allocation | Developer assembles supervising model/actor that chooses per-agent bounded allocations and priorities using shared usage | Same decision produced with static per-agent policy alone |
| Lawful effect/closure | [BeforeToolCall intervention](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/interventions/handler.py#L29-L108) can deny; Graph/Swarm run multiple agents | Atomic reservation and expiry/lease enforcement on every relevant action; stale revisions fail closed | Bypass, fail-open or overspend under parallel workers |
| Feedback to future regulation | Tool-result hooks and observed denial/usage | Report successful consumption/denial to ledger, recalculate and enforce new limits on subsequent actions | Supervisor choice never affects the next S1 action |
| Parent and recursion | Developer owns Cedar policies and absolute ceilings | No revision can exceed parent maximum or change S5; separate application scope | Supervisor requires unlawful authority to alter parent controls |

Native alternative A0 is to resolve [#6289](https://github.com/strands-agents/harness-sdk/issues/6289) and keep fixed per-agent allowances. That is a valid solution for static count correctness, but cannot by itself disprove architecture constructibility of *dynamic cross-agent* reallocations. The scenario is HYPOTHETICAL; demand, economics and actual portability remain unverified.

## Implementation options

PLAN_ONLY: opt-in source-native `SharedBudgetSupervisor` integration assembled from an Agent, intervention handler, and durable per-application ledger. A developer declares immutable total authority and per-action ceilings; the supervisor receives current usage/capacity metrics and allocates permissible shares. Each worker carries a stable identity for tool access; every paid/risky relevant action reserves budget atomically before effect; denial and result report consumption for the next discretionary decision. No claim that this code presently exists. Reject a generic listener-only design (no binding effect) and pure static policy wrapper (no autonomous S3 choice); reject automatic policy rewriting outside parent constraints. Test both supported Python and TypeScript paths and delegated Swarm/Graph/as_tool/snapshot resets.

## Specification and domain alternatives

No change to Profile/Skills warranted solely by this plan. Current parent-governed static usage is legitimate. Distinct S3* audit and S4 external forecasting variants were considered but excluded without sufficient protected independent audit authority or prospective environment/decision closure. A future negative result would be useful evidence for source-native C constructibility under this SDK boundary, not a defect certificate or maintainer decision.

## Cost experiment

Unrun A/B: A0 fixed native Cedar + source-native snapshot correction; A1 same task with optional supervisor kit; compare correct bounded allocations, downstream completion, overspend, engineering effort, model/latency overhead and review/maintenance cost under identical concurrent and restore workloads. **Cost status: NOT_MEASURED.** No measured benefit asserted.

## Delivery and publication

**Wave 4 source-first GO / NEEDS_EVIDENCE**, recorded independently at [#58](https://github.com/opensiro/upstream/issues/58#issuecomment-7042836907) before historical case review; new plan supersedes old proposal-stage NO_GO only for this **architecture-constructibility re-evaluation**, not original product priority. Historical [2026-11-19 NO_GO](https://github.com/opensiro-contributions/harness-sdk/blob/b17a07332bffa1b5eecfc0c24da47c721ec1d3a4/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md) rejected speculative S3 because the actual bug can be repaired natively without a manager; this remains true for the bug, but current v0.18.0 neutrality disallows making user demand or cheap bug fix a veto to a coherent separate S3=C architecture. The same stable case folder and old immutable Git history are preserved; distinct Strands six-function case remains untouched. Human [issue.md](issue.md), AI [constructor-sufficiency.md](constructor-sufficiency.md) synchronized. Native tests NOT_RUN; cost NOT_MEASURED; no fork/original public Issue, original PR, product code, Index change or maintainer adoption claimed.
