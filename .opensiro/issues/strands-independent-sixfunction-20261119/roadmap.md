# Strands Agents — independent v0.18 six-function Roadmap receipt
## Identity and pins

- Original repository: strands-agents/harness-sdk
- Original HEAD: 794d37c6e3f00e1d4192f3c81672d3da79780d88
- Observed at: 2026-11-19
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/assessments/st/strands-agents.md
- Accepted assessment blob SHA: 60b16ac6fdbe828d873706786a79e44053ec7446
- Accepted review ref: 08ed4cfd3eb42ae9f668595e675d5f196eee7e44
- Accepted reviewed at: 2026-09-15
- System in focus: One developer-configured first-party Strands Python or TypeScript agent runtime, including optional SDK multi-agent Swarm/Graph and harness defaults, plugin/hook, intervention, model routing and session controls; application owner and external provider or maintainer organization are outside the runtime boundary.
- Index commit: c2e43bf4750841277b3e58d8ba80314121734764
- Accepted Index catalog: https://github.com/opensiro/vsm-harness-index/blob/c2e43bf4750841277b3e58d8ba80314121734764/data/catalog.psv ; row 61, harness_id strands-agents, exact original URL and review_ref match.
- Accepted last checked source: e7fd22b63f3988997a12fb962144a9663a27d071 (2026-09-17).
- Historical Profile / Skills methodology: 0.2.1 / 0.3.1; no current regrade.
- Upstream protocol: https://github.com/opensiro/upstream/blob/be03ced5ed5d3b7210762df612dc4b3f452c1a73/docs/ROADMAP_INDEPENDENT_RERUN.md (v0.18.0).
- Receipt contract: proposal-gate
- Accepted VSM vector: S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—
- Target transition: NO_QUALIFIED_C_TARGET
- Scenario basis: HYPOTHETICAL
- Proposal-stage decision: NO_GO
- Research disposition: NO_USEFUL_CHANGE
- Validation state: NOT_RUN
- Result: NO_USEFUL_CHANGE
- External issue: DRAFT — NOT PUBLISHED
- Cost status: NOT_MEASURED

Accepted historical source pin 08ed4cfd3eb42ae9f668595e675d5f196eee7e44 resolves in the original repository; the September assessment is 65 days old and does **not** describe the 2026-11-19 HEAD. This is an independent Upstream construction decision rather than an Index reassessment. Original exact source: https://github.com/strands-agents/harness-sdk/commit/794d37c6e3f00e1d4192f3c81672d3da79780d88.

## Rights and authority

Verified matched fork `opensiro-contributions/harness-sdk`: GitHub fork parent exactly `strands-agents/harness-sdk`; its separate `opensiro/meta` metadata branch read `ACTIVE / ALLOW` under owner activation event `20261119T182226Z--owner-upstream58-active`. Its regular/default product branch is out of scope. License: [Apache-2.0](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/LICENSE.APACHE); [CONTRIBUTING.md](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/CONTRIBUTING.md) requires checking active work and maintainer confirmation before significant code; [AI usage](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/team/AI_USAGE_POLICY.md) requires AI disclosure and human accountability. No original-repository code, remote public Issue, comment or PR is authorized or attempted; fork GitHub Issues are disabled. No presumption of CLA/DCO waiver or a parent/S5 grant.

## Existing work / overlap

**Track A / shipped first-party baseline.** [Agent](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/agent/agent.py) and [Python harness](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/harness-py/src/strands_harness/agent.py) (plus TS equivalents) execute model/tool requests, support limits and optional delegation. [Swarm](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/multiagent/swarm.py) provides handoff, shared context and configurable anti-oscillation; [Graph](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/multiagent/graph.py) provides explicit dependencies, cycles, output return, nested nodes. [Subagent spec](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/multiagent/spec.py) binds child tool/model authority to developer supplied Fixed/Inherit/Open/Choice modes. [Harness intervention resolver](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/harness-py/src/strands_harness/interventions.py) exposes opt-in native human approval, risk screening and Cedar. SDK interventions and hooks are distinct from an autonomous VSM policy owner. [ModelRouter](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/models/routing) is configured client-side routing/fallback, not a demonstrated prospective future adaptation organization.

**Track A / original activity and counterfactuals.** [Merged #6279](https://github.com/strands-agents/harness-sdk/pull/6279) corrected per-agent Cedar call counts (original [#6278](https://github.com/strands-agents/harness-sdk/issues/6278) closed). [Open #6289](https://github.com/strands-agents/harness-sdk/issues/6289) describes reproducible snapshot-restore stale counts and the competing per-agent reset semantics, including Swarm/Graph/as-tool regression. [Open #5631](https://github.com/strands-agents/harness-sdk/issues/5631) is the harness default-invocation-limit request. [Open PR #6286](https://github.com/strands-agents/harness-sdk/pull/6286) adds a **catalog entry** for the existing community spend-ceiling plugin, **not** a merged SDK-wide controller; its author reports parent-tool reservation but documents gaps for default subagent, auxiliary/structured calls and TypeScript. [Open PR #4749](https://github.com/strands-agents/harness-sdk/pull/4749) proposes invocation queue/supersession choices; not shipped. [Open #6369](https://github.com/strands-agents/harness-sdk/issues/6369) proposes richer DecisionModel hook evidence; [open #6354](https://github.com/strands-agents/harness-sdk/issues/6354) highlights router continuation semantics. These are independent original-native work items, not presumed defects in the same VSM function. Simplest alternative is explicit limits, Cedar, optional app queue or spend plugin, direct original bug fix and existing trace hooks.

**Track B / rejected on-top construction.** Considered a first-party optional developer-composable shared current-commitment S3 manager over multiple delegated workers (bounded group budget/capacity, autonomous admit/defer/reassign, enforced before spend, attributed later usage and release). Also screened S3* independent outcome review and S4 forward provider migration using shipped extension hooks/model routing. No source-backed *incremental operator outcome*, distinct authorized decision owner with supported enforce-before-effect and closed return, or verified advantage over the native/manual route was established; mere API or a historical `—` does not qualify any of them for GO.

## Function ownership

- S1 disposition: Historical A; existing model-driven per-agent tool work and tool-result loop ([Agent](https://github.com/strands-agents/harness-sdk/blob/794d37c6e3f00e1d4192f3c81672d3da79780d88/strands-py/src/strands/agent/agent.py)) already supply operational decisions; no new S1 C use case.
- S2 disposition: Historical C; developer-composed Swarm anti-oscillation and Graph dependency routing have actual coordination points; no additional evidenced regulation gap.
- S3 disposition: Historical —; limits and Cedar enforce app-declared quotas but do not independently select whole-organization current capacity/priority among S1 agents. No qualified new decision/effect/return loop against simpler apps/plugin/queue.
- S3* disposition: Historical —; logs, evals, intervention events and reviewer nodes alone do not establish separate complementary audit authority with binding S3 feedback. No independently evidenced audit request.
- S4 disposition: Historical —; ModelRouter and externally updated releases support runtime provider choice, but no source-pinned prospective environmental adaptation owner, trial and later outcome loop needed beyond shipped/router-native work.
- S5 disposition: Historical —; application developer, user and legitimate parent own permissions, goals and budget identity; static Cedar/HITL is enforcement and escalation, not an autonomous S5 policy owner. Omission may be lawful and is not an inferred deficiency.

## Capability priority

- Repository-wide source map: Monorepo README and AGENTS, Python/TS SDK and harness agent/config/delegation, Swarm/Graph, hooks/interventions/Cedar, model routing, background/snapshots, tests and CI, contributor policy, first-party issues and PRs checked at source HEAD. Entire monorepo was not locally executed or exhaustively line-reviewed.
- Priority rationale: Evaluate the smallest plausible cross-agent S3 shared-current-budget construction first, then S3* audit and S4 future-routing alternatives, without treating old vector gaps as requirements; all fail incremental/native-comparator evidence today.
- P0: NONE; scoped NO_GO for an additional on-top VSM function C constructor at this observation, not a verdict against Strands or native fixes.
- P1 dependencies: Native #6289's policy/snapshot owner choice and regression; #5631 harness default limits and #6286 spend-plugin overlap; revisit only if real shared-task outcomes remain unserved.
- P2 optional: NONE; no speculative S3* reviewer, S4 migration agent or S5 grant.
- Proposed C construction: Rejected hypothetical optional group-bounded first-party S3 commitment manager receiving parent-approved resource envelopes, current worker state and a controlled autonomous admit/defer/reassign decision, applying admission before any spend, and returning task-keyed release and usage to that same owner.
- C sufficiency falsifier: If a permitted app queue, static limits/Cedar, existing spend plugin or native #5631 implementation yields the same decisions and results with less integration and risk, or manager cannot securely enforce action and receive later feedback across Python/TS delegated children, there is no independently justified S3=C constructor.
- Proposed validation: Only if independently requested, replay two overlapping delegated tasks under a finite authorized shared budget, compare app-level limits/queue/plugin with an optional policy-bounded adaptive manager, demonstrate at least two lawful distinct decisions changing dispatch and attributed return; test snapshot/reset and TS/Python boundaries and forbidden/expired grants.
- Proposal falsifier: Equal or better operator correctness and matched integration/maintenance cost from native controls, or missing lawful autonomous choice, direct dispatch effect or closed task return, rejects GO. No such test has been run.

## Implementation options

**No implementation now.** For the concrete Cedar restore bug, the original [#6289](https://github.com/strands-agents/harness-sdk/issues/6289) already lists competing native fixes and explains why simply re-reading state on every call can weaken swarm/as-tool limits. A separate S3 controller would not repair that narrower correctness bug. For spend defaults compare original #5631 and existing opt-in integrations; do not reopen #6278 or claim #6286 merged. All future original code requires native tests, maintainer process and exact external-publication authorization.

## Specification and domain alternatives

No material ambiguity in Profile/Skills is evidenced by this case. No new domain-specific assessment fork is warranted. If an operator supplies a concrete team-level resource conflict not coverable by native controls, consider a distinct, explicitly bounded new scenario after checking Index freshness; do not mutate canonical Index grades or interpret parent-supplied policy as a missing S5 agent.

## Cost experiment

Matched comparison is hypothesis only: shared two-child task correctness, unauthorized call count, total spend, cancellation/recovery, Python/TS coverage and human engineering/integration/testing/review/maintenance effort for (A) native limits/Cedar/app queue/plugin and (B) optional composed controller. **NOT_MEASURED**; no savings, tests, released feature or production outcome claimed.

## Delivery and publication

**Terminal source-only Roadmap decision:** `NO_GO / NO_QUALIFIED_C_TARGET` with research `NO_USEFUL_CHANGE`; workflow `DECISION_READY`, native tests `NOT_RUN`, costs `NOT_MEASURED`. This receipt is a proposed case for internal persistence, not a public original/fork Issue, implementation, PR, Index reassessment or maintainer endorsement. Current owner state permits only separate metadata updates. Canonical [Human draft](issue.md) and [AI sufficiency](constructor-sufficiency.md) carry the identical negative decision. Public communication: **NOT_PUBLISHED**. Next permissible action is an internal link-only status PR and read-only native watch when requested.

**Historical comparison performed AFTER independent decision:** earlier [2026-11-19 Cedar/snapshot case](https://github.com/opensiro-contributions/harness-sdk/blob/b984492cda1d6c803298c6a29c3b958eacc4b805/.opensiro/issues/strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md) also reported scoped NO_GO, but at original `078cbc216608eefe37fdb8bc5e43e3a02985e088` and pre-activation fork state `PAUSE/DORMANT`. This fresh case pin `794d37c6e3f00e1d4192f3c81672d3da79780d88` independently screened a broader six-function native-and-on-top surface including #5631, #6286, #4749 and #6369. **NO_GO -> NO_GO**, evidence/current scope differ. Old case, its state and attribution remain unchanged.

## Parallel contribution-on-top review

- Evaluation object: Is a genuinely additional first-party developer-composable VSM C decision/effect/closed-feedback function justified in current Strands SDK/harness beyond shipped controls?
- Existing-work overlap: Python and TS Swarm/Graph, Agent limits, application queue, Cedar/interventions, ModelRouter, native #6289 and #5631, open catalog PR #6286, pending concurrency PR #4749 and observability #6369.
- Our on-top contribution: NONE SELECTED; a minimal autonomous S3 group-commitment controller was screened but fails source-backed incremental value and first-party lawful return proof.
- Incremental benefit: NOT_ESTABLISHED beyond native/manual and optional plugin baselines; no request that merits assigning new current/future/audit authority at this observation.
- Decision scope: Current original `794d37c6e3f00e1d4192f3c81672d3da79780d88`, declared first-party runtime boundary and on-top C hypothesis only; not a judgement on Strands quality, native fixes, optional external agents or all future use cases.
