# Strands Agents — independent six-function roadmap review (OpenSiro)

**Independent 2026-11-19 result: NO_GO / NO_QUALIFIED_C_TARGET; workflow DECISION_READY, research NO_USEFUL_CHANGE.** No defect, feature implementation or Index regrade is asserted. This is an **unpublished Human Issue draft**, retained only in fork metadata.

**Canonical decision receipt:** [roadmap.md](roadmap.md) · **AI construction contract:** [constructor-sufficiency.md](constructor-sufficiency.md).
**Target transition:** NO_QUALIFIED_C_TARGET
**Proposal-stage decision:** NO_GO
**Research disposition:** NO_USEFUL_CHANGE

## Motivation and provenance

OpenSiro asks whether an additional developer-composable VSM function provides a real user outcome over the host's existing solution, not whether the host has a particular VSM label. The accepted historical [Index assessment](https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/st/strands-agents.md) is `included` (blob `60b16ac6fdbe828d873706786a79e44053ec7446`, Index `c2e43bf4750841277b3e58d8ba80314121734764`, review 08ed4cfd3eb42ae9f668595e675d5f196eee7e44 on 2026-09-15, Profile 0.2.1 / Methodology 0.3.1). The catalog identity, original URL and review commit match. Current original source is independently pinned to [`794d37c6e3f00e1d4192f3c81672d3da79780d88`](https://github.com/strands-agents/harness-sdk/commit/794d37c6e3f00e1d4192f3c81672d3da79780d88). These old labels are *ownership/constructibility states*, not grades of quality; `—` is not automatically a present defect. A means agent-owned, C developer-composable, while the legitimate parent may retain policy rights.

| Function · plain-language role | Historical state | Current original evidence and independent decision |
| --- | --- | --- |
| **S1 · Operations** | A | [SDK Agent](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/agent/agent.py) invokes models/tools and handles returns; no additional C needed. |
| **S2 · Coordination** | C | [Swarm](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/multiagent/swarm.py) anti-oscillation and Graph dependencies provide developer-composable coordination already. |
| **S3 · Current management** | — | Limits, [Cedar](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/vended_interventions/cedar/cedar_authorization.py), and app policy do not prove whole-team autonomous budget ownership; a new manager has no established incremental outcome. |
| **S3* · Independent audit** | — | Hooks/telemetry and intervention results do not establish separate binding complementary operational audit authority. |
| **S4 · Future adaptation** | — | Model routing, release updates and adaptation proposals are not themselves an autonomous future-environment feedback/decision loop. |
| **S5 · Policy and identity** | — | User/application developer legally owns budgets, tools and authority; no extra S5 agent is warranted. |

## Concrete operator outcome

An application has multiple delegated agents under a finite resource limit and needs correct lawful behavior when sessions, subagent handoffs and snapshots interact. Before creating an OpenSiro-owned controller, compare Strands' actual limits, Cedar and native extension points with an application-managed queue or opt-in spend plugin. The original [#6289](https://github.com/strands-agents/harness-sdk/issues/6289) is a real issue about restored Cedar counters; the simplest solution is an original-native semantic choice and regression tests, **not** an autonomous system manager. Original [#5631](https://github.com/strands-agents/harness-sdk/issues/5631) requests harness default limits. [PR #6286](https://github.com/strands-agents/harness-sdk/pull/6286) is an unmerged *catalog-entry* integration for an existing spend-ceiling plugin, not a shipped Strands runtime feature; [PR #4749](https://github.com/strands-agents/harness-sdk/pull/4749) proposes queueing/concurrency choices and is open.

**P0: NO_QUALIFIED_C_TARGET.** A hypothetical S3 group manager would have to choose between two authorized policies from live task/budget state, control dispatch *before spending*, and receive task-keyed usage/completion feedback to revise its next lawful choice. Current evidence does not show a user result beyond ordinary controls or a complete supported port across Python/TS child lifecycles. S3* and S4 alternatives were also screened and did not qualify.

**P1:** resolve or track native #6289 and #5631, compare #6286 and #4749 before any design. **P2:** none. Falsifier for a future GO: demonstrate the native/manual solution fails on a reproducible two-child resource conflict while a parent-bounded first-party decision/dispatch/return loop succeeds with less matched total effort. Such experiments were **NOT_RUN**; cost **NOT_MEASURED**.

## Governance and disposition

The original is Apache-2.0, contributor onboarding requests maintainer confirmation before significant code, and [AI policy](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/team/AI_USAGE_POLICY.md) requires disclosure and human responsibility. Matching OpenSiro fork is ACTIVE/ALLOW for **metadata**, but its public Issues are disabled and original/fork public communication needs independent exact owner approval. No external Issue/PR, fork public Issue, implementation, native test or Index regrade is asserted.

After reaching this new verdict independently, the earlier [narrow Cedar snapshot NO_GO case](https://github.com/opensiro-contributions/harness-sdk/blob/b984492cda1d6c803298c6a29c3b958eacc4b805/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md) was compared: outcome remains NO_GO, but the new source pin and whole-repository six-function scope are different. Old records are preserved. Status is **DECISION_READY / NO_GO**, not pending feature engineering.
