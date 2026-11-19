# Strands Agents — AI/developer constructor sufficiency, independent v0.18

**Human roadmap draft:** [issue.md](issue.md) · **Authoritative canonical receipt:** [roadmap.md](roadmap.md).
**Target transition:** NO_QUALIFIED_C_TARGET
**Proposal-stage decision:** NO_GO
**Research disposition:** NO_USEFUL_CHANGE

## System boundary and authority

Scope is the first-party developer-deployed Python/TypeScript Agent plus optional Swarm/Graph, default harness, installed interventions/plugins, sessions and model routers at [original 794d37c6e3f00e1d4192f3c81672d3da79780d88](https://github.com/strands-agents/harness-sdk/commit/794d37c6e3f00e1d4192f3c81672d3da79780d88). A model provider is not an S4 owner; GitHub maintainer org is not in the runtime; application owner retains S5 goals, permissions and budget rights. Accepted six-function baseline and blob provenance are pinned once in [roadmap.md](roadmap.md), not regraded. This independent analysis occurred before reading the older OpenSiro proposal.

## Function-specific sufficiency: first-party Track A versus candidate Track B

| Candidate | Track A: observed first-party path | Track B: minimal extra C path | Why rejected and falsifier |
| --- | --- | --- | --- |
| S1 | Existing Agent model/tool execution and results | New generic operational actor | Duplicates functioning operations; no distinct task. |
| S2 | Swarm transfers and configurable repeat-handoff regulator; Graph nested routing | New independent coordinator | Existing developer-composable S2 already regulates identified disturbance; no uncovered conflict proven. |
| S3 | Per-invocation limits, Cedar counters, developer-supplied queue, multiagent state; #6289 open | Optional, bounded autonomous current-commitment actor choosing admit/defer/reassign with shared state, first-party enforcement before child spend and later usage/release feedback | No demonstrated incremental task over native Cedar/app queue/#5631 or existing community spend plugin; dispatch/return integration not proven. |
| S3* | Interventions/OTel/evals and graph reviewers are configurable observers | Separately authorized adverse-outcome sampling reviewer with binding stop/review return to manager | Native hook test and actual independent audit-right gap not established; a reviewer node/telemetry alone is not independent authority. |
| S4 | Shipped ModelRouter and first-party model support/maintenance issues | Future provider capability watcher that selects adaptation trial and feeds later results | Model fallback and maintainer release decisions do not supply the independently needed future state/owner/experiment; unknown incremental value over router. |
| S5 | Developer/app sets policies, grants and scope; Cedar/HITL enforce/escalate | Autonomous policy/identity owner | Improper transfer of legitimate parent control; no mandate or legitimate new policy choice. |

Read [Python subagent spec](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/multiagent/spec.py), [Graph](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/multiagent/graph.py), [Swarm](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/multiagent/swarm.py), [harness interventions](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/harness-py/src/strands_harness/interventions.py), [agent core](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/agent/agent.py), TypeScript equivalents, repository development/test docs and original issue/PR bodies. Native **#6279 merged** per-agent Cedar fix; **#6289 open** snapshot semantics conflict; **#5631 open** harness defaults; **#6286 open** catalog integration; **#4749 open** concurrency; **#6369 open** decision hook context; **#6354 open** routing continuation. An open PR is not shipped functionality. [AI usage policy](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/team/AI_USAGE_POLICY.md) and [contributors](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/CONTRIBUTING.md) additionally govern external implementation.

## Minimal S3 construction rejected at this time

1. Developer authorizes a finite shared budget and permitted choice set with no rights escalation; it defines parent-approved goals and resource identity.
2. Proposed first-party event port would disclose current worker commitments and available capacity with revision/task IDs to an optional developer-composed S3 actor.
3. Actor would choose **admit / defer / reassign / hold** between at least two lawful options, not merely log a threshold or ask an operator.
4. Native child dispatch would atomically reserve/deny before executing model/tool work, handle cancellation/stale state and respect Cedar/human veto.
5. Later real task termination, usage, error and snapshot recovery would return to the same S3 actor, changing its next lawful decision.

At the pinned source, neither a demonstrated user problem that requires this complete route nor a technically validated first-party port across dynamic child construction and both languages is established. Existing app queues, Cedar quotas and spend plugins are cheaper admissible comparators. Therefore this is **NO_GO**, not a minimal GO; absence of whole-system S3 historical evidence is not a feature request.

## Future acceptance gate and falsification

A genuine new operator task would require the same two-child concurrent workload at same costs and rights with (A) ordinary app queue plus invocation limits/Cedar or available spend plugin and (B) a bounded composed autonomous owner. Proof requires two distinct autonomous lawful decisions with different downstream actions and task-keyed return, no bypass, no snapshotted stale grant, explicit operation denial and cross-SDK coverage. If native route matches correctness and total build/test/review/maintenance effort, or if the proposed authority/effect/feedback path cannot be made first-party, reject construction.

**Experiments:** NOT_RUN. **Savings:** NOT_MEASURED. **Scope:** internal research/draft only, public fork and third-party communication NOT_PUBLISHED; no original code, CI, Index metadata or outside GitHub communication changed.

## Historical comparison after independent decision

The previously persisted [Cedar snapshot case](https://github.com/opensiro-contributions/harness-sdk/blob/b984492cda1d6c803298c6a29c3b958eacc4b805/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md) was NO_GO on an earlier HEAD for a narrower S3 actor tied to #6289. Independent 2026-11-19 v0.18 review of current `794d37c6e3f00e1d4192f3c81672d3da79780d88` likewise yields NO_GO, now explicitly evaluating all six functions, default limits and community/native overlap; this is a new attributed decision, not an overwrite or inherited verdict.
