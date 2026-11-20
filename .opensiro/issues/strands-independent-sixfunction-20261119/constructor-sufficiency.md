# Strands Agents — source-native S3* constructor sufficiency (AI/developer handoff)

**Human draft:** [issue.md](issue.md). **Authoritative source-pinned receipt:** [roadmap.md](roadmap.md). The historical six-function table is only in Human; no second grade table is reproduced here.
**Target transition:** S3*=— -> S3*=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

## Declaration, owner and experimental object

Original `strands-agents/harness-sdk@287896945d2190ebf90adc9e67c0456239681843`; accepted Index assessment `5dbb51b2ddad0f29a84e10b4b5009c8989159165`, blob `60b16ac6fdbe828d873706786a79e44053ec7446`; old source review `08ed4cfd3eb42ae9f668595e675d5f196eee7e44`. The current repo contains `strands-py`, `strands-ts`, `harness-py`, `harness-ts`, Graph/Swarm and plugin/extensibility surfaces; CI, docs, team and standalone evals are adjacent to installed runtime ownership. Only Python first-party Swarm is proposed as initial executable host.

The **worker's claim** is that a named task yielded a correct artifact. The **usual path** is worker's returned `AgentResult/NodeResult`, `GoalLoop` judgement or trace. The **complementary path** is independently read original output/replay/file bytes, versioned with immutable task and evidence identity, by a separately developer-configured autonomous verifier. The **authorized receiver** is an application controller with rights to hold/recheck the *next* affected task. The **actual feedback** is subsequent node outcome/status returned to the controller and recorded in an audit receipt. The actor is opt-in, cannot invent authority, and cannot modify parent policy or arbitrary files.

## Track A — exact native interfaces and evidence boundary

- [`Swarm`](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/swarm.py) builds `SwarmState.results`, `SwarmResult.node_history`; the 2026-11-20 pinned implementation has a callback before each node, failed-node status, and serialized/resumed swarm state. Never assume `AfterNodeCallEvent` is a secure post-commit snapshot or that the worker's textual assertion proves artifact reality.
- [Python hooks](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/hooks/events.py): `AfterMultiAgentInvocationEvent` is a post-execution observation seam; `BeforeNodeCallEvent.cancel_node` can reject the next node before its execution with a failure result. A developer wrapper may instead explicitly gate the next invocation. Check expected native ordering during tests.
- [`MultiAgentPlugin`](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/plugins/multiagent_plugin.py): developer-installed plugin registers hooks, not a new global scheduler.
- [`take_snapshot/load_snapshot`](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/_snapshot.py): preserve orchestrator identity and sequence, but an audit finding must still have its own task/evidence revision token.
- [`GoalLoop`](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/vended_plugins/goal/plugin.py) runs an internal or caller validator on response/transcript then resumes; not by itself an independent raw-artifact S3* channel.
- [`strands-harness` subagent](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/harness-py/src/strands_harness/tools/subagent.py) forwards child return statuses, not independent validity. [TS events](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-ts/src/multiagent/events.ts) and [TS plugin](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-ts/src/multiagent/plugins.ts) provide parity investigation later.
- Original [PR #1656](https://github.com/strands-agents/harness-sdk/pull/1656) OPEN evaluation telemetry (head `506853a60cf1688bfc06a7a868b8faed49cb356a`), [PR #6204](https://github.com/strands-agents/harness-sdk/pull/6204) OPEN E2E test scenarios (head `2a16c48fe7311c70415ffa0c7dc19b6079649414`), [issue #5934](https://github.com/strands-agents/harness-sdk/issues/5934) OPEN deterministic pre-tool gate, and [merged #6046](https://github.com/strands-agents/harness-sdk/pull/6046) background task cancellation do not show independent first-party sampled audit return. Their completion and competing PR heads must be refreshed again at implementation time.

## Track B — minimal complete composition, not a generic framework

**Proposed source-native intervention (not implemented):**
1. Caller creates regular `Swarm` from supported first-party Python SDK and installs `MultiAgentPlugin` with explicitly provided `auditor_factory`, `artifact_reader`, `audit_policy` and authorized `report_sink`. The names are **illustrative local design options**, not claims they are real Strands APIs.
2. Plugin observes committed completed run/node identity and source result via hooks. It samples based on developer criteria, obtains the requested artifact from a separately authorized provider (not from worker's verbal summary), pins content/source revision, and invokes a **distinct autonomous read-only judge** with evidence and claim. Timeouts/inaccessible evidence yield `INCONCLUSIVE` or the app's explicit hold policy, never implicit pass.
3. It emits a signed/attributable (not necessarily cryptographic) result with `run_id`, `node_id`, `evidence_revision`, claim, cited evidence and `PASS/CHALLENGE/INCONCLUSIVE`. The parent application checks that finding scope, task revision and effect authority are current. No advice is treated as execution authorization by itself.
4. On an affected **subsequent** node, app/plug-in gates with `BeforeNodeCallEvent.cancel_node` (which fails this node) or explicit wrapper; it can request re-verification or authorized human resolution. It reports actual blocked/retried/completed result to the same controller. This closes S3* feedback into *subsequent control*, not merely a dashboard.
5. For snapshot/replay or concurrent runs, invalid/stale `run_id`/`evidence_revision` does not apply. Parent S5 remains outside; no auto-rollback and no changes to already executed tools. Lifecycle must be verified against native hook order before a patch.

**Minimum missing original-native code**, if approved later: opt-in plugin-level evidence fetch and task revision ledger, separate auditor dispatch and structured findings, an authorized next-node gate/return adapter and targeted native tests. Existing Strands hooks and state are reused. No universal 5-port contract or mandatory number of cases.

## Distinctness, feasibility and falsifiers

The native `GoalLoop` judge is part of normal execution of the claimed result, while sampling different raw evidence through separately installed auditor can falsify it. A routine reviewer agent reading only the final result does **not** qualify. PR #1656 transports evaluation telemetry; it does not provide audited independence or intervention; PR #6204 exercises regression tests outside live user tasks. The proposed S3* actor must genuinely judge something the worker report cannot assure and route findings to a legitimate manager. That is why the architectural `GO` is scoped and still `NEEDS_EVIDENCE`; cost advantage or product desirability is unproven. If independent source access, authorized later-operation effect or feedback cannot be implemented in native hooks without illegal rights, downgrade proposal rather than silently adding a new manager.

## Native future acceptance — NOT_RUN

| Hypothetical native test | Same-source baseline / target mechanism | Observable effect and stop criterion |
| --- | --- | --- |
| False artifact completion | One worker falsely reports creation; compare normal `GoalLoop`/trace with new audited `Swarm` plugin | Audit retrieves absent/wrong raw artifact and reports `CHALLENGE`; authorized next task is held/rechecked; next node outcome returned; if only a second summary is read, fail |
| Valid completion | Real correct artifact under same task and permitted provider | Nonblocking `PASS`; no false hold; subsequent task feedback observed |
| Missing/revoked auditor or unavailable evidence | Developer does not install auditor or reader access denied | No fictional S3* actor and no silently successful audit; explicit disabled/inconclusive behavior per chosen application policy |
| Stale/replayed finding | Snapshot resumed at new revision/task ID | Old finding cannot hold or authorize unrelated task; explicit stale/failure state |
| Owner/return failure | Application denies attempted hold or audit sink fails | Fail explicit; no unauthorized effect; accurate subsequent status/no fake completion |

Use actual Strands test tooling and snapshots; no tests, integration runs, costs or numeric benefit were executed or measured in this roadmap.

## P0/P1/P2, comparison and handoff

P0 optional Python first-party Swarm S3* complete evidence/decision/effect/feedback chain. P1 independent evidence provenance, owner contract, hook ordering, replay and TypeScript scope/tests. P2 NONE. Human-facing proposal summary and exact status remain in [issue.md](issue.md), canonical structured fields in [roadmap.md](roadmap.md).

**Historic comparison after independent sealed source pass:** old 2026-11-19 same case concluded `NO_GO / NO_QUALIFIED_C_TARGET`, focused on lacking proved incremental value over first-party S3 budgets and an unspecified S3* reviewer. New 2026-11-20 pass independently identifies a more constrained S3* source-native complete constructor; neutral assessment of proposal feasibility permits `GO + NEEDS_EVIDENCE` without claiming measured demand or owner intent. The [distinct Cedar case](../strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md) remains unchanged. Current maintainer still controls product adoption; no public fork/original issue, PR, review or product change is authorized. Research `NEEDS_EVIDENCE`, validation `NOT_RUN`, publication `NOT_PUBLISHED`.
