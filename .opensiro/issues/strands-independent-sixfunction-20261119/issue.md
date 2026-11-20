# Strands Agents — independently composed S3* artifact audit (OpenSiro Human Issue)

**PLAN_ONLY · GO / NEEDS_EVIDENCE · DRAFT — NOT PUBLISHED.** This is the existing internal fork-local case updated for the 2026-11-20 Wave 4 source-first rerun. It is not a GitHub public Issue.

**One-sentence proposal:** Allow a Strands application to install a separate autonomous evidence auditor on `Swarm` that checks claimed task completion against actual artifacts and returns a versioned finding to the authorized next-step controller.

**Canonical decision receipt:** [roadmap.md](roadmap.md) — single source for source pins, historical assessment vector, priorities, proposal decision and validation.
**Technical companion:** [constructor-sufficiency.md](constructor-sufficiency.md) — source-native hooks, ownership and proposed tests.
**Target transition:** S3*=— -> S3*=C
**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE

## 1. Why OpenSiro and historical baseline

OpenSiro tests whether a composable VSM function can be architecturally constructed for an original harness. This does not imply defect, project need, reduced engineering cost, maintainer agreement or changed grade.

**ACCEPTED HISTORICAL Index (not current HEAD):** [Strands assessment](https://github.com/opensiro/vsm-harness-index/blob/5dbb51b2ddad0f29a84e10b4b5009c8989159165/assessments/st/strands-agents.md) at Index `5dbb51b2ddad0f29a84e10b4b5009c8989159165`, assessment blob `60b16ac6fdbe828d873706786a79e44053ec7446`, original review `08ed4cfd3eb42ae9f668595e675d5f196eee7e44`, 2026-09-15, Profile 0.2.1 / methodology 0.3.1. [Current original 287896945d2190ebf90adc9e67c0456239681843](https://github.com/strands-agents/harness-sdk/commit/287896945d2190ebf90adc9e67c0456239681843) separately pinned (2026-11-20). The accepted original/catalog identity matches. Historical ownership categories are not quality ranks.

**Six functions — one historical/current/priority table:**

| Function · plain-language role | Historical Index | Pinned current source / decision owner, proposed priority |
| --- | --- | --- |
| **S1 · Operations** | A | [Agent](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/agent/agent.py) makes autonomous tool/model decisions; existing operations, NO_TARGET. |
| **S2 · Coordination** | C | [Swarm](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/swarm.py) configurable repeated-handoff regulator supports developer-composable coordination; NO_TARGET. |
| **S3 · Current management** | — | Runtime limits/background cancellation enforce developer constraints, not independent whole-system manager; DEFER due authority and scope. |
| **S3* · Independent audit** | — | [GoalLoop](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/vended_plugins/goal/plugin.py) and traces inspect normal results; independent raw-artifact challenge not proven; **P0** opt-in separate audit actor/feedback. |
| **S4 · Future adaptation** | — | Existing configured provider routing is not forward-looking autonomous environment intelligence; DEFER without a source-specific future scenario. |
| **S5 · Identity/policy** | — | Application owner decides identity/policy; [harness interventions](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/harness-py/src/strands_harness/interventions.py) enforce constraints; NO_TARGET. |

The system-in-focus is the deployed developer-configured first-party Strands Agent/Swarm/Graph and hooks. Docs, team governance, Evals examples and CI do not become runtime S3*/S5 by repository proximity. No deliberate absence is presumed merely from old `—` grades. Maintainer interest: **NOT_STATED**.

## 2. Specific original-native task and construction

**Operator scenario — HYPOTHETICAL.** A worker completes a Strands Swarm turn and claims it generated a requested artifact, but the artifact is absent or wrong. The caller wants an independent reviewer to inspect original tool outputs/files/replay instead of trusting that worker's final answer. Application remains owner of permission to access evidence and hold subsequent work.

**P0:** The application configures an opt-in read-only autonomous audit actor and independent raw evidence provider; a [MultiAgentPlugin](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/plugins/multiagent_plugin.py) samples `SwarmResult` claims via [Swarm state/hooks](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/swarm.py), attaches source/task revisions, returns `PASS/CHALLENGE/INCONCLUSIVE`, and allows the application to hold a later affected node using [BeforeNodeCallEvent](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/hooks/events.py). The owner makes any ultimate approval. A naked extra reviewer node or trace does not qualify as complementary S3*.

**Best existing native alternative:** Use [GoalLoop](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/vended_plugins/goal/plugin.py) / hooks, traces, an application-managed reviewer and explicit human check; this can be sufficient and is the matched baseline, but is not proof that a separate first-party composable audit channel already closes S3*.

## 3. Existing native overlap and minimum missing link

| S3* C requirement | Track A, shipped/pending | Track B, missing construction |
| --- | --- | --- |
| Alternative access to operational reality | Shipped Swarm results/hook events; [PR #1656](https://github.com/strands-agents/harness-sdk/pull/1656) OPEN evaluation telemetry | Independent read-only raw artifact/replay access + distinct autonomous judge/criteria |
| Versioned finding changes later lawful operation | Shipped `BeforeNodeCallEvent.cancel_node` and snapshots; [PR #6204](https://github.com/strands-agents/harness-sdk/pull/6204) OPEN integration tests | Task/evidence revision binding, attributed finding, authorized hold/recheck and actual return |

[Issue #5934](https://github.com/strands-agents/harness-sdk/issues/5934) concerns deterministic *pre-tool* bounds, a different product problem. No parallel PR was assumed merged. Positive claim is architectural constructibility only; no measured benefit or product priority is asserted.

## 4. Priority, acceptance and limits

**P0:** Source-native S3* independent Swarm artifact-audit plugin, not generic central governance. **P1:** raw evidence ownership/access, stale-ID and snapshot safety, native Python verification, then TypeScript parity. **P2:** NONE.

**Future positive:** against identical input, the worker lies about generated artifact; separate auditor checks actual artifact and lawful next task is held/rechecked, with outcome fed back. **Future negatives:** auditor not installed, missing/revoked evidence access, stale finding, policy-denied action, clean correct artifact, feedback failure. A missing auditor is not interpreted as an automatically passing review. **NOT_RUN**; cost **NOT_MEASURED**. Falsifier: no independent evidence/decision, no downstream authorized effect/feedback, or shipped equivalent autonomous audit control.

## 5. Decision and rights

**GO / NEEDS_EVIDENCE** applies only to a complete proposed `S3*=— -> S3*=C` path, not actual runtime C, implementation approval, or an instruction to maintainers to adopt it. The 2026-11-19 scoped NO_GO remains historically attributable: it demanded empirical incremental utility over native S3 limits; the 2026-11-20 post-neutrality independent pass chooses a different S3* object and does not pretend evidence was tested. Separate Cedar budget case unchanged.

License Apache-2.0. [Contributor procedure](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/CONTRIBUTING.md) and [AI policy](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/team/AI_USAGE_POLICY.md) still apply. Fork owner control `ACTIVE/ALLOW` applies to metadata only. No original or public fork Issue/PR/comment, code, Index change, tests or measured savings published. Next permitted work is a disposable native acceptance experiment, then an independently approved product/publication decision.
