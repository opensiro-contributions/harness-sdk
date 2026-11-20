# Strands Agents — S3* independent artifact audit (Opensiro roadmap)

**PLAN_ONLY · proposal-stage GO · research NEEDS_EVIDENCE · DRAFT — NOT PUBLISHED**

**One-sentence proposal:** Add an opt-in, source-native Strands Swarm complementary audit plugin that lets a separately authorized autonomous reviewer inspect original task artifacts and pass a challenge finding into the application's lawful next-step control.

**Canonical decision receipt:** [roadmap.md](roadmap.md), the single structured authority for historical Index vector, six function dispositions, chosen transition, P0/P1/P2 and publication state.
**Technical companion:** [constructor-sufficiency.md](constructor-sufficiency.md), for exact Swarm hooks, distinct audit decision rights and future acceptance.
**Working fork:** `opensiro-contributions/harness-sdk@opensiro/meta`, verified parent `strands-agents/harness-sdk` and `ACTIVE / ALLOW` metadata rights.
**Case:** `.opensiro/issues/strands-independent-sixfunction-20261119/`; same historical case revised after independent new first-pass, with prior result retained in Git history.

## 1. Why Opensiro and central accepted VSM assessment

Opensiro tests whether source-specific VSM functions can be composed on top of a real AI harness. Its proposed construction feasibility is not a feature request, quality certification, cost-reduction measurement or maintainer approval.

### Central starting point — accepted Index, not the target

**ACCEPTED HISTORICAL INDEX — not current grades, not a quality score:** `S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—`.

[Included Strands assessment](https://github.com/opensiro/vsm-harness-index/blob/5dbb51b2ddad0f29a84e10b4b5009c8989159165/assessments/st/strands-agents.md) at Index `5dbb51b2ddad0f29a84e10b4b5009c8989159165` (assessment blob `60b16ac6fdbe828d873706786a79e44053ec7446`, `review_ref=08ed4cfd3eb42ae9f668595e675d5f196eee7e44`, `reviewed_at=2026-09-15`, Profile 0.2.1 / Skills methodology 0.3.1); matching catalog row 61 and resolved historical original ref. Current original [`287896945d2190ebf90adc9e67c0456239681843`](https://github.com/strands-agents/harness-sdk/commit/287896945d2190ebf90adc9e67c0456239681843) is a separately pinned 2026-11-20 observation. The states are **ownership categories, not quality ranks**: `A` autonomous ownership, `C` developer-composable autonomous function, `—` no established path at the *historically reviewed boundary*; no `—` forces construction.

**Repository-wide audit:** Inspected current monorepo README/AGENTS, `strands-py`/`strands-ts`, `harness-py`/`harness-ts`, Swarm/Graph, hooks, agent goal-loop/interventions, model routing, snapshots, delegation/background tasks, supporting tests/CI, docs and contributor policy, plus related original PR heads and issue text. System in focus is the developer-installed agent + optional Swarm/Graph; team governance, site/Evals examples and dev CI are adjacent, not silently credited as in-runtime S3*/S5.

| Function / plain-language role | Historical state | Current source-backed owner/closure | Candidate / uncertainty and priority |
| --- | --- | --- | --- |
| **S1 · Operations** | A | [Agent](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/agent/agent.py) autonomously chooses model/tool work and receives results | NO_TARGET; existing operations |
| **S2 · Coordination** | C | [Swarm](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/swarm.py) configurable repetitive-handoff regulation | NO_TARGET; existing composable anti-oscillation |
| **S3 · Current management** | — | App-defined limits and cancellation constrain activity; whole-system budget/priority authority not established | DEFER; heavier new rights and scheduling |
| **S3* · Complementary audit** | — | [GoalLoop](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/vended_plugins/goal/plugin.py) and traces follow ordinary work, not independently sourced raw-artifact review | **P0:** optional separate autonomous raw-evidence verifier with returned authorized later-operation hold |
| **S4 · Future intelligence** | — | Configured routing/provider swaps do not establish prospective environment model with S3 feedback | DEFER; no justified external adaptation scenario |
| **S5 · Identity and policy** | — | App developer/parent owns legitimate policy; [harness interventions](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/harness-py/src/strands_harness/interventions.py) enforce configured boundaries | NO_TARGET; no unauthorized local S5 |

**Priority rationale:** S3* can reuse shipped Swarm node history/result and lifecycle callbacks with a narrow read-only complementary actor, while S3 demands larger cross-child resource authority; S4 lacks a supported outside/future experiment; S5 belongs to the parent and S1/S2 have accepted positive witnesses. No invented six-function quota.

**Deliberate exclusions / methodology challenge:** Parent-held S5 is lawful, not a runtime deficiency; a lack of current S4 evidence is not proof the omission was deliberately intended. A current GoalLoop reviewer is not automatically independent S3*. Falsify the S3* plan if only the worker's own report can be accessed or no independent finding changes later work. Maintainer interest: NOT_STATED.

## 2. Selected construction hypothesis and operator outcome

**Target transition:** S3*=— -> S3*=C
**Function-specific disturbance:** HYPOTHETICAL false completion of an artifact-producing Swarm task: worker says it wrote the requested file, but the actual file/tool return shows absence or wrong content.
**Proposed C capability (P0):** A developer may attach an opt-in Python [MultiAgentPlugin](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/plugins/multiagent_plugin.py) to a regular Swarm, configure an autonomous *separate read-only reviewer* with original artifact/replay access, obtain a versioned `PASS / CHALLENGE / INCONCLUSIVE` finding and let the authorized application controller hold/recheck the *next affected* node via [BeforeNodeCallEvent](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/hooks/events.py), with actual outcome returned.
**Best native operator alternative:** Use existing [GoalLoop](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/vended_plugins/goal/plugin.py), tracing/hooks and application/human review; these can be sufficient for a chosen application but do not themselves prove independent raw-evidence ownership at the installed Swarm boundary.
**Expected user benefit:** HYPOTHETICAL ability to detect a wrong artifact against its original data and prevent blind continuation; benefit, incidence and cost are NOT_MEASURED, with no claim of maintainer demand.
**Architectural sufficiency argument:** Shipped Swarm results and hooks provide observation and *subsequent-node* effect seams, but only a distinct authorized evidence provider and autonomous reader can challenge routine claims; a versioned audit and lawful controller feedback complete the proposed S3* path without granting S5 rights. It is a proposed composable C, not shipped C or automatic new Index grade.

## 3. Existing native work versus missing construction

**Track A — native coverage:** [Swarm result/history](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/swarm.py), [plugin hooks](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/plugins/multiagent_plugin.py), [snapshot](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/_snapshot.py) and in-path GoalLoop SHIPPED. [PR #1656](https://github.com/strands-agents/harness-sdk/pull/1656) OPEN at head `506853a60cf1688bfc06a7a868b8faed49cb356a` adds optional evaluation OTel event transport, not audit owner. [PR #6204](https://github.com/strands-agents/harness-sdk/pull/6204) OPEN at head `2a16c48fe7311c70415ffa0c7dc19b6079649414` adds product E2E tests, not installed audit feedback. [Issue #5934](https://github.com/strands-agents/harness-sdk/issues/5934) OPEN asks for deterministic pre-tool argument bounds; [PR #6046](https://github.com/strands-agents/harness-sdk/pull/6046) MERGED adds optional background-task cancellation, unrelated to S3* review ownership.
**Track B — independent on-top C construction:** App configures independent raw-evidence reader + separate autonomous audit actor, sampled stable task IDs and evidence revisions, recorded finding and an application-authorized hold/recheck/feedback path on the following node. No generic mandatory supervisor or side-effect authority.

| C-sufficiency requirement | Already present (A) | Missing (B) |
| --- | --- | --- |
| Audited operational claim and independent contrary access | Swarm `NodeResult`, task history, tracing | Read actual artifact/replay bytes, separate from worker narrative; autonomous independent auditor |
| Legitimate finding and later returned correction | `AfterMultiAgentInvocationEvent`, `BeforeNodeCallEvent.cancel_node`, snapshots | Attributed verdict/revision + application-owned next-task hold or recheck + observed next-node result |

**Distinctness and falsifier:** A GoalLoop validator that reads only the worker transcript is not independently sourced S3*. If current first-party functionality already supplies independent auditor with raw evidence *and* authorized returned next-step feedback, this proposal is duplicate. If no separate evidence or controller effect is possible, the proposed C is insufficient.

## 4. Priorities and minimum sufficient result

- **P0:** Optional first-party Python Swarm S3* raw artifact/replay audit and authorized next-step return, only at developer-declared boundary.
- **P1:** Prove artifact source/revision provenance, independent auditor role and app authority, hook order, snapshots/replay safety, and native tests before considering TS parity.
- **P2:** NONE; no second VSM function or mandatory broad controller.

**Proposed C-sufficiency verdict:** PROPOSED_C_SUFFICIENT at architecture/design level, independent acceptance NOT_RUN, not production proof.

## 5. Proposed acceptance and stop gates

**Future positive test:** One Swarm worker asserts it generated a file, but independent reader sees missing/wrong file; auditor issues CHALLENGE, lawful next node is held or rechecked, and the actual effect is returned to controller. Compare same input to ordinary in-path GoalLoop baseline.
**Future negative test:** No installed auditor, revoked/missing raw-evidence permission, stale task revision, unexpected failure or incorrect worker claim; do not silently treat absent independent evidence as a pass. A valid artifact should avoid false holds.
**Proposed falsifier:** Independent source access, separate judgement, lawful next-step effect or return is absent; or equivalent shipped first-party C already exists.
**Validation state:** NOT_RUN; no native test or economic validation, no guessed pass counts.

## 6. Independent paths

**Original-native contribution:** Proposed later as opt-in Strands Swarm plugin only after source-native tests and maintainer process; no current original code/Issue/PR.
**Profile / Skills:** No demonstrated amendment; S3* reading/return and parent authority already follow [Profile](https://github.com/opensiro/vsm-harness-profile/blob/main/PROFILE.md).
**Domain fork:** NONE proposed; an independent permitted implementation would require fresh owner-rights review.

## 7. Cost hypothesis

Compare normal Strands GoalLoop/trace/human verification with extra autonomous evidence audit against identical false/real artifact workloads; count detection, false holds, integration, review, maintenance and operational spend. **Cost status: NOT_MEASURED**; no empirical ROI.

## 8. Decision / handoff

**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE
**Decision reason / next permitted step:** A complete source-specific first-party S3* actor, independent evidence, lawful downstream hold and returned feedback is architecturally constructible; no product demand or tests are established. Later isolated native acceptance experiment, then maintainer-owned product choice. Historical 2026-11-19 NO_GO from the *same* case (different broader requirement to prove marginal demand, focus on S3 current limits) remains in Git history, and separate Cedar Wave 4 S3 case remains unchanged. First pass [sealed before historical inspection](https://github.com/opensiro/upstream/issues/58#issuecomment-7045308538).
**Agent/developer handoff:** [constructor-sufficiency.md](constructor-sufficiency.md) and [roadmap.md](roadmap.md) are the only current technical/structured companions.
**Rights and publication:** Apache-2.0, [contributors](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/CONTRIBUTING.md) and [AI use policy](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/team/AI_USAGE_POLICY.md) apply. Fork `ACTIVE/ALLOW` is metadata-only, not publication consent. **DRAFT — NOT PUBLISHED**; no original/fork public Issue/PR/comment, product code change, Index regrade or independent task approval.
**AI disclosure:** Prepared with AI assistance; native acceptance NOT_RUN and independent human review not claimed.
