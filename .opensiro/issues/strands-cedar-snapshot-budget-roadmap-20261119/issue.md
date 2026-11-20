# Strands Agents — optional shared-budget S3 constructor (Wave 4, plan only)

**PLAN_ONLY · proposal-stage GO · research NEEDS_EVIDENCE · DRAFT — NOT PUBLISHED.**

**Target transition:** S3=— -> S3=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

**One-sentence outcome:** A developer could assemble an opt-in model-owned manager that redistributes a fixed, parent-authorized shared action budget between running Strands agents and enforces its changing allocations through first-party hooks and interventions.

**Canonical decision receipt:** [roadmap.md](roadmap.md) (exact source and Index pins, priority, decision, test falsifiers).
**Developer technical contract:** [constructor-sufficiency.md](constructor-sufficiency.md).
**Existing case and immutable previous negative decision:** [2026-11-19 receipt](https://github.com/opensiro-contributions/harness-sdk/blob/b17a07332bffa1b5eecfc0c24da47c721ec1d3a4/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md).

## Why OpenSiro and the accepted Index

OpenSiro investigates whether VSM-informed first-party constructors can reduce the work of assembling agent governance; a useful result or savings are not yet established. Historical [accepted Index](https://github.com/opensiro/vsm-harness-index/blob/0a4ffd542afae11b048918167f7791f26db167bb/assessments/st/strands-agents.md) `0a4ffd542afae11b048918167f7791f26db167bb`, assessment blob `60b16ac6fdbe828d873706786a79e44053ec7446`, review `08ed4cfd3eb42ae9f668595e675d5f196eee7e44` on 2026-09-15, Profile 0.2.1, Skills 0.3.1. The source examined now is [original@3e5217136b80](https://github.com/strands-agents/harness-sdk/commit/3e5217136b80ddcd743099ad5d11a926301c8c04), not the 2026-09-15 assessed revision. No silent Index regrade.

| Function / plain-language role | Historical Index state | Current first-party ownership and feedback | Target priority and uncertainty |
| --- | --- | --- | --- |
| **S1 · Operations** | A | [Agent](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/agent/agent.py) autonomously performs tool-using work | NO_TARGET, existing agent-owned operation |
| **S2 · Coordination** | C | [Swarm](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/multiagent/swarm.py#L197-L235) exposes configurable repetitive-handoff attenuation | NO_TARGET, existing composable C |
| **S3 · Current management** | — | [Cedar](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/vended_interventions/cedar/cedar_authorization.py#L160-L285) enforces supplied per-agent counts but does not own shared dynamic allocation decisions | **P0 S3=C**, hypothetical bounded shared-budget supervisor |
| **S3* · Independent audit** | — | Trace/hook and named review do not independently own protected complementary oversight | NO_TARGET, audit independence not proven |
| **S4 · Future adaptation** | — | [Router](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-ts/src/models/routing/router.ts) selects/falls back during invocation, not demonstrated prospective environmental adaptation | DEFER, uncertain need and ownership |
| **S5 · Identity/policy** | — | Application/parent supplies ultimate policy and global budgets; repository `team/` governance is adjacent | NO_TARGET, parent retains reserved authority |

These are six historical function-ownership categories, not maturity/quality ratings. A = agent-owned autonomous closure; C = developer-composable first-party C path; — = no witnessed adequate path at the reviewed boundary. This is not a proposal to build every function.

## Why this differs from the native bug fix

Open [#6289](https://github.com/strands-agents/harness-sdk/issues/6289) covers stale Cedar counts when snapshots restore, and risk that state-only fixes restart budgets across repeated Swarm/Graph/asTool calls. Merged [#6279](https://github.com/strands-agents/harness-sdk/pull/6279) and [#6290](https://github.com/strands-agents/harness-sdk/pull/6290) cover per-agent count isolation and tests. Fixing these is the source-native answer to the reported bug. It is **not** a test of an independently composable, autonomy-bearing whole-system regulator that changes priority-based allocation across agents during ongoing work.

The new P0 is an architectural **HYPOTHESIS**, not evidence that Strands users want AI budget management. The proposed actor observes shared usage from [hook events](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/hooks/events.py#L221-L285), makes bounded discretionary allocations, and passes revisions to [fail-closed interventions](https://github.com/strands-agents/harness-sdk/blob/3e5217136b80ddcd743099ad5d11a926301c8c04/strands-py/src/strands/interventions/handler.py#L29-L108) for subsequent enforcement. A parent fixes the immutable budget ceiling and access envelope. Without the supervisor, the same dynamic priority allocation is not supplied by the static per-agent limits in the inspected code; with a supervisor but without binding enforcement and returned feedback it would not be S3.

## Current comparison and acceptance

**Track A:** native Cedar/intervention configuration and straightforward original [#6289](https://github.com/strands-agents/harness-sdk/issues/6289) repair. **Track B:** first-party extension kit with shared versioned ledger, supervisor agent, atomic per-tool budget reservations, feedback to the supervisor and enforced revised allocations. Parent and S5 remain external. P1 includes snapshot/child/reset concurrency and Python/TS parity tests; P2 NONE.

Proposed tests are **NOT_RUN**. The GO claim is falsified if first-party native code already closes equivalent autonomous shared allocations without a new construct, or if a worker can act outside the ledger and violate the fixed global ceiling. Cost is **NOT_MEASURED**; maintainer interest **NOT_STATED**, product adoption left entirely to original maintainers.

## Comparison with history and publication

Historical [NO_GO](https://github.com/opensiro-contributions/harness-sdk/blob/b17a07332bffa1b5eecfc0c24da47c721ec1d3a4/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md) rested on the fact that the existing bug does not justify a new manager. That remains a valid product-task observation. Under the released v0.18.0 assessment-neutral rule, it is not an architectural veto. The new GO concerns a different autonomously composed resource-allocation outcome and remains unvalidated. See [sealed independent first pass](https://github.com/opensiro/upstream/issues/58#issuecomment-7042836907) and receipt for exact provenance. This is an OpenSiro fork-local **draft only**: no external or fork public Issue/PR, native implementation, Index grade change or third-party commitment.
