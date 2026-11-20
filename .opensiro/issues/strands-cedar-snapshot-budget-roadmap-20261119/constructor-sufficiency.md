# Strands Agents — shared-budget S3 constructor sufficiency (Wave 4)

**PLAN_ONLY · proposal-stage GO / NEEDS_EVIDENCE · technical contract; NOT_RUN, NOT_MEASURED; DRAFT — NOT PUBLISHED.**

**Target transition:** S3=— -> S3=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

**Canonical decision receipt:** [roadmap.md](roadmap.md).
**Human Issue (draft only):** [issue.md](issue.md).
**Frozen historical NO_GO:** [2026-11-19 receipt](https://github.com/opensiro-contributions/harness-sdk/blob/b17a07332bffa1b5eecfc0c24da47c721ec1d3a4/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md). Current [original SHA](https://github.com/strands-agents/harness-sdk/commit/3e5217136b80ddcd743099ad5d11a926301c8c04) and [accepted Index](https://github.com/opensiro/vsm-harness-index/blob/0a4ffd542afae11b048918167f7791f26db167bb/assessments/st/strands-agents.md) are pinned in the receipt.

## Functional boundary and autonomy test

The in-scope runtime includes Python/TS Strands Agent, Swarm/Graph orchestrators, child agent composition, CedarAuthorization, first-party InterventionHandler and before/after tool events. The budget decision concerns the operating application's shared agent work capacity, not the maintainer's CI, Evals, private provider systems or parent policy administration. Parent decides the total limit and permitted tools; a composed supervised actor may only choose which current S1 receives capacity within that ceiling. It does NOT set its own constitutional policy (not S5) and it is not an independent S3* auditor.

**S3 witness:** disturbance = competing agents consuming a shared budget with changing priorities/observed demand. Decision = change how much usable capacity each current S1 can consume, not just compute an already selected rule. Owner = opt-in supervisor agent composed from first-party Strands API by the developer. Enforcer = fail-closed intervention + versioned shared ledger; feedback = usage/denial and observed subsequent allocation effects returned to supervisor for the next choice. Counterfactual owner test: remove supervisor, retain Cedar and ledger: fixed rules still enforce but the *discretionary redistribution* decision disappears. A notification-only hook is insufficient.

## Track A — shipped first-party primitives and original overlap

- [Agent execution](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/agent/agent.py), [Swarm handoffs](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/multiagent/swarm.py#L197-L235) and [Graph](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/multiagent/graph.py) implement operational dispatch with limits. Existing S2=C anti-oscillation is separate.
- [Python Cedar](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/vended_interventions/cedar/cedar_authorization.py#L160-L285) and [TS Cedar](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-ts/src/vended-interventions/cedar/cedar.ts#L175-L272) enforce static developer-authored policy on each tool call; per-agent cached counts do not constitute a shared autonomous S3 actor.
- [InterventionHandler](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/interventions/handler.py#L29-L108) and [Before/AfterToolCall events](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/hooks/events.py#L221-L285) provide supported native integration surfaces, but any claimed cross-agent global atomic enforcement requires tests.
- [Original #6289](https://github.com/strands-agents/harness-sdk/issues/6289) OPEN explores inconsistent restored snapshot counts; [#6381](https://github.com/strands-agents/harness-sdk/issues/6381) OPEN for TypeScript reset-all parity. [#6279](https://github.com/strands-agents/harness-sdk/pull/6279) and [#6290](https://github.com/strands-agents/harness-sdk/pull/6290) MERGED; their test assertions do not prove a shared-budget S3 loop.
- Best simpler alternative for *the reported defect*: repair Cedar counters and write snapshot, child and repeated node tests. Do this independently of any new S3 proposal.

## Track B — smallest function-complete opt-in kit

1. **Observation:** a first-party intervention uses stable agent/work-item IDs and emits tool-call authorization, consumption and denial events to a concurrency-safe shared ledger. Snapshot restores must not reset global spending. Parent's total ceiling cannot be rewritten by the supervisor.
2. **Decision ownership:** a developer-assembled first-party supervisor Agent observes aggregate ledger and live capacity/priority inputs and exercises bounded discretion choosing among eligible S1 allocations. The decision and its justification/revision have traceable owner; deterministic framework enforcement alone is not the S3 owner.
3. **Binding closure:** ledger validates revision and atomically reserves action capacity before allowed tool effects, rejecting stale/over-budget actions by default; each managed S1 sees changed capacity at its next tool invocation. Completion/denial modifies the ledger and the supervisor receives later feedback to revise allocations.
4. **Boundary:** explicit registered managed agents/actions, permitted tool effects, parent-approved budget unit and failure mode. Test child construction and permissions inheritance, Graph/Swarm restart, separate Python/TS paths and potential out-of-band tools. If any managed side effect can bypass reservations, the sufficient C chain is not demonstrated.
5. **Construction:** optional reusable source-native kit, not an independently deployed policy authority or unreviewable default service. No product implementation in this PR; native APIs, names and tests are hypotheses until validated.

| Obligation | A0 existing-native capability | B1 proposed C delta | Falsifier |
| --- | --- | --- | --- |
| See current shared resource use | Per-agent Cedar counts in agent state, hooks | Shared append-only usage/reservation ledger | Equivalent native global accounting already exists |
| Decide aggregate priorities | Static per-agent policies, developer configuration | Composed model-owned selection within parent limits | Static rule produces equivalent discretionary reallocation |
| Apply decisions to current S1 | BeforeToolCall supports deny | Atomically enforced versioned allowance across all managed paths | Any stale/parallel managed action overspends |
| Close feedback | Agent observes tool outcomes | Supervisor observes later utilization/denials and changes next allocation | Next S1 choices unaffected or only log-only |
| Preserve parent rights | Cedar and application policy | Strict immutable parent ceiling, non-escalating grants | Actor can change its own S5 envelope |

**Rejected variants:** (i) fix-only #6289 cannot itself be the novel cross-agent discretionary S3 decision; (ii) deterministic static per-agent totals alone are not model-owned dynamic regulation; (iii) logging-only/trace-only has no closure; (iv) an independent S3* audit or S4 forecast without its own supported function evidence is outside this scoped case.

## Planned native evidence, cost and stop conditions

A0 baseline: fixed Cedar policy with #6289 settled in an original-native fashion; B1: budget supervisor on same competing agent workload. Validate over concurrent calls and restarted/snapshotted child agents: fixed global ceiling never exceeded, discretionary allocation actually changes after feedback, new allocation reaches later S1 execution, parent controls remain immutable, no tool bypass or unintended fail-open, both Python and TS supported. Include negative controls (remove supervisor; remove enforcement; crash ledger; stale revision), measure total test/regression effort, runtime latency/LLM costs, and engineering time. **Tests: NOT_RUN. Economics: NOT_MEASURED.** A failed authority/closure test => NO_GO/BLOCKED as supported; an already equivalent shipped first-party S3 path => no material new C.

## Neutrality / provenance and next decision

Independent first pass sealed [before historical comparison](https://github.com/opensiro/upstream/issues/58#issuecomment-7042836907); old [NO_GO](https://github.com/opensiro-contributions/harness-sdk/blob/b17a07332bffa1b5eecfc0c24da47c721ec1d3a4/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md) was product-task-scoped to fixing Cedar's snapshot counts. Wave 4 changes that veto criterion, **not** whether the bug exists or what maintainers should build. The proposed extra architecture remains HYPOTHETICAL, acceptance evidence absent, external public publication forbidden without exact current-chat consent. If implementers do not want this optional feature, that does not falsify the VSM architectural assessment; only function/authority/effect/feedback evidence does.
