# Strands Agents — Wave 4 independent source-first native-specific Roadmap (2026-11-20)

## Identity and pins

- Original repository: strands-agents/harness-sdk
- Original HEAD: 287896945d2190ebf90adc9e67c0456239681843
- Observed at: 2026-11-20
- Accepted Index assessment: https://github.com/opensiro/vsm-harness-index/blob/5dbb51b2ddad0f29a84e10b4b5009c8989159165/assessments/st/strands-agents.md
- Accepted assessment blob SHA: 60b16ac6fdbe828d873706786a79e44053ec7446
- Accepted review ref: 08ed4cfd3eb42ae9f668595e675d5f196eee7e44
- Accepted reviewed at: 2026-09-15
- System in focus: Developer-installed Strands Python/TypeScript Agent runtime, optional first-party Swarm/Graph composition and SDK/harness hook/plugin/feedback paths; app developer owns authorization, policy and ultimate identity. Site, team governance, CI and disconnected Evals experiments are adjacent, not an installed runtime audit owner.
- Index commit: 5dbb51b2ddad0f29a84e10b4b5009c8989159165
- Accepted Index catalog: https://github.com/opensiro/vsm-harness-index/blob/5dbb51b2ddad0f29a84e10b4b5009c8989159165/data/catalog.psv ; row 61, exact original identity and review_ref matched; historic source revision resolves in original.
- Historical Profile / Skills methodology: 0.2.1 / 0.3.1; historical vector remains unchanged, not a current-HEAD regrade.
- Protocol: https://github.com/opensiro/upstream/blob/main/PROTOCOL.md (observed v0.18.1); source-first checkpoint https://github.com/opensiro/upstream/issues/58#issuecomment-7045308538.
- Receipt contract: proposal-gate
- Accepted VSM vector: S1=A · S2=C · S3=— · S3*=— · S4=— · S5=—
- Target transition: S3*=— -> S3*=C
- Scenario basis: HYPOTHETICAL
- Proposal-stage decision: GO
- Research disposition: NEEDS_EVIDENCE
- Validation state: NOT_RUN
- Result: NEEDS_EVIDENCE
- External issue: DRAFT — NOT PUBLISHED
- Cost status: NOT_MEASURED

The accepted 2026-09-15 Index snapshot is historical. The independently investigated 2026-11-20 original main HEAD is [287896945d2190ebf90adc9e67c0456239681843](https://github.com/strands-agents/harness-sdk/commit/287896945d2190ebf90adc9e67c0456239681843). This proposal only examines first-party constructibility and leaves adoption and product priority to the original maintainer. The first-pass decision was [sealed before examining older OpenSiro case records](https://github.com/opensiro/upstream/issues/58#issuecomment-7045308538).

## Rights and authority

Matching public working fork `opensiro-contributions/harness-sdk` has parent `strands-agents/harness-sdk` and separate `opensiro/meta` metadata branch. Live fork state checked `ACTIVE / ALLOW`; later PAUSE/STOP overrides. Original [Apache-2.0 license](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/LICENSE.APACHE), [CONTRIBUTING](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/CONTRIBUTING.md) (request maintainer confirmation before significant work) and [AI policy](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/team/AI_USAGE_POLICY.md) retain their ordinary restrictions. Developer supplies auditor identity, evidence access, protected task IDs and the controller's allowed hold/review authority. An audit plugin cannot grant itself permission, replace S3 management or change S5 policy. No public fork GitHub Issue, original Issue/comment/PR or product code publication was authorized here.

## Existing work / overlap

**Track A, SHIPPED at pinned original.** [Swarm](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/swarm.py) records `SwarmState.results`, `SwarmResult.node_history` and execution status; Python [multi-agent hook events](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/hooks/events.py) expose `AfterMultiAgentInvocationEvent`, and `BeforeNodeCallEvent.cancel_node` prevents an upcoming node, while [snapshot](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/_snapshot.py) restores versioned execution state. [Python MultiAgentPlugin](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/plugins/multiagent_plugin.py) and [TypeScript plugin/event interfaces](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-ts/src/multiagent/plugins.ts) provide supported opt-in extension seams. [GoalLoop](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/vended_plugins/goal/plugin.py) judges the active task using its response/transcript and retries within the ordinary operational path, so its mere presence is not independent S3*. Harness [subagent tool](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/harness-py/src/strands_harness/tools/subagent.py) returns child outcomes but does not separately verify source artifacts. Existing tracing, evaluator examples and developer CI are not established installed complementary audit closure.

**Track A, original issue/PR overlap.** [Open PR #1656](https://github.com/strands-agents/harness-sdk/pull/1656) adds opt-in evaluation OTel events (head `506853a60cf1688bfc06a7a868b8faed49cb356a`, not merged): telemetry transport, not independent decision ownership. [Open PR #6204](https://github.com/strands-agents/harness-sdk/pull/6204) builds Python/TS end-to-end test scenarios (head `2a16c48fe7311c70415ffa0c7dc19b6079649414`), not a deployed task auditor. [Original issue #5934](https://github.com/strands-agents/harness-sdk/issues/5934) proposes deterministic pre-tool argument bounds, not after-run complementary inspection. [Merged PR #6046](https://github.com/strands-agents/harness-sdk/pull/6046) adds optional cancellation of background tasks; cancellation is enforcement, not an S3* verifier. None of these is treated as a maintainer veto, demand proof or an already shipped on-top S3* constructor.

**Track B, minimal distinct source-native construction.** An opt-in `MultiAgentPlugin` attaches to a developer-configured `Swarm`, samples completed `SwarmResult` nodes/outputs by stable run/task identity, invokes a separate developer-supplied autonomous read-only auditor with access to independently obtained raw output/tool/replay evidence and independent audit criteria, compares claimed completion to real artifacts, and emits attributable versioned `PASS / CHALLENGE / INCONCLUSIVE` with cited evidence and affected task identity. The authorized application's controller accepts this advisory finding and can hold/recheck the *next* affected node through `BeforeNodeCallEvent.cancel_node` or an explicit application wrapper; subsequent node status is recorded and returned. Python-first demonstration is minimal; parity/long-lived proof across TypeScript and snapshots remains P1. No extra default subagent, generic mandatory controller or unrelated provider-watcher is implied.

## Function ownership

- S1 disposition: Historical A; [Agent](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/agent/agent.py) model/tool decisions and results are operational S1; existing, no proposed C target.
- S2 disposition: Historical C; [Swarm](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/swarm.py) configurable repetitive-handoff guard and TS analogue regulate peer oscillation; no duplicate S2 constructor.
- S3 disposition: Historical —; Swarm limits, state, [background tasks](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/background_tasks/_background_tasks.py) and cancellation are task execution/constraints, not proof of independent whole-system capacity/priorities ownership. Candidate shared-resource manager deferred due wider rights/changes.
- S3* disposition: Historical —; traces and [GoalLoop](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/vended_plugins/goal/plugin.py) see routine worker path or its transcript; no demonstrated autonomous, independently sourced raw-artifact audit with feedback into authorized later control. Opt-in extra independent auditor is selected P0.
- S4 disposition: Historical —; available [model routing](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/models/routing/__init__.py) and configured provider portability are not a prospective outside/future decision-return organization. No new S4 target selected.
- S5 disposition: Historical —; [harness interventions](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/harness-py/src/strands_harness/interventions.py) enforce application-specified limits and approvals; legitimate developer/parent owns identity and policy, not an inferred autonomous runtime S5.

## Capability priority

- Repository-wide source map: Root README and AGENTS, Python/TS SDKs and harnesses, Swarm/Graph and plugins, goal/steering, background task cancellation, snapshots, model routing, subagents, hooks, site examples, tests/CI and contributor/team policy were inspected as distinct surfaces; not an exhaustive line-by-line audit or product test.
- Priority rationale: S3* offers a narrowly source-specific composable verification boundary using existing Swarm completion and hook surfaces while preserving explicit independent auditor and application owner rights; S3 needs broader capacity/authority semantics, S4 needs future environment evidence, S5 belongs to parent, and S1/S2 already have accepted positive owners. Historical gaps are not demands.
- P0: Propose opt-in first-party Python Swarm S3* raw-artifact audit and authorized next-node hold-return path, with a developer-installed autonomous auditor; no implementation approved.
- P1 dependencies: Prove raw artifact capture/fetch independent of worker's own summary, run/task revision and auditor role separation, deterministic hold/advisory policy and replay/snapshot safety, then assess TypeScript parity and competing original PR evolution.
- P2 optional: NONE; do not add a generic cross-provider strategic agent, new S5 or second controller.
- Proposed C construction: Compose a separate read-only audit actor into Swarm through first-party MultiAgentPlugin hooks; record real independently retrieved evidence, versioned audit decision, authorized application handoff/hold of later affected node, and later actual result feedback to audit/controller. The developer configures criteria, source access, escalation and failure policy.
- C sufficiency falsifier: Auditor reads only routine worker summaries or cannot access independent raw artifacts; its verdict cannot reach any authorized later decision/effect; missing/stale auditor passes silently; or equivalent independently owned review and subsequent control is already provided natively.
- Proposed validation: NOT_RUN — instrument same two-node Swarm with a worker falsely claiming an artifact was produced; compare baseline GoalLoop/tracing with separate raw-artifact audit. Verify changed lawful hold/recheck on next affected step, final feedback, clean-case no false hold, missing/revoked auditor, corrupted evidence, task/snapshot revision mismatch and execution/closure failures; use Strands Python tests first and only then assess TS parity. No guaranteed real-world performance change.
- Proposal falsifier: A matched native implementation already supplies independent auditor, raw evidence and later feedback, or proposed actor cannot make any independent judgement affecting authorized subsequent work, falsifies S3*=C construction.

## Implementation options

This is PLAN_ONLY. Prefer a source-specific opt-in `MultiAgentPlugin` around [Python Swarm](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/swarm.py), its [event callbacks](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/hooks/events.py) and developer-supplied external raw-artifact reader. Test one clear post-run artifact claim before generalizing. Avoid reimplementing PR #1656's telemetry emitter, PR #6204's harness scenario suite, or issue #5934's deterministic pre-tool bounds. Implementation and original communication require separate contributor/legal/publisher gates. A "PASS" finding must not be confused with already implemented S3* ownership.

## Specification and domain alternatives

Current [Profile S3* semantics](https://github.com/opensiro/vsm-harness-profile/blob/main/PROFILE.md) require an independent complementary view of operational reality and findings influencing subsequent control; this hypothesis uses that definition, not a new grade. No Profile/Skills change proposed. Separate external domain fork is optional only with actual owner rights, not part of this run.

## Cost experiment

Compare same worker/false-completion input and acceptance under (A) routine native GoalLoop, trace/hook and app inspection and (B) added autonomous independent evidence auditor + hold-return integration. Record detection, false holds, audit access failures, task feedback and build/integration/review/maintenance cost separately. Expected advantage is HYPOTHETICAL; **cost NOT_MEASURED**, native tests **NOT_RUN**. Maintainer decides if it fits product strategy even when construction is feasible.

## Delivery and publication

**New post-v0.18.0 neutral, v0.18.1 native-specific proposal:** `S3*=— -> S3*=C`; **GO / NEEDS_EVIDENCE** with PLAN_ONLY research, no shipped function, no Index regrade. The owner may reject product adoption despite constructibility. Rights to public original or fork interactions were not granted: `NOT_PUBLISHED`. Canonical [Human draft](issue.md) and [AI contract](constructor-sufficiency.md) display the same target/verdict/research, while this receipt owns the historical vector.

**Historical comparison only after first-pass sealed:** 2026-11-19 v0.18-era same case at original `794d37c6e3f00e1d4192f3c81672d3da79780d88` concluded `NO_GO / NO_QUALIFIED_C_TARGET / NO_USEFUL_CHANGE` chiefly because no demonstrated incremental benefit over native S3 limits/queue and unverified S3* audit need. New review does not assert a new reported demand and does **not** change the distinct [Cedar budget case](../strands-cedar-snapshot-budget-roadmap-20261119/roadmap.md), whose own Wave 4 S3 constructor remains separately attributed. It selects a **different independently proposed S3*** object and applies v0.18.0 neutrality: lack of economic measurement or product-owner priority cannot by itself veto a complete source-native proposed C path. Earlier NO_GO remains in Git history; no retroactive claim of earlier GO. First-pass source-backed finding [#7045308538](https://github.com/opensiro/upstream/issues/58#issuecomment-7045308538) predates consultation of older fork files.

## Parallel contribution-on-top review

- Evaluation object: Can Strands Swarm install a separately authorized composable autonomous S3* artifact-audit path, comparing worker completion claims against independent evidence and returning advisory findings to lawful next-step control, without replacing app/parent governance?
- Existing-work overlap: Shipped Swarm results, hooks, plugins, snapshots, GoalLoop and tracing; unmerged original PR #1656 evaluation telemetry, PR #6204 harness test scenarios, original issue #5934 pre-tool bounds and merged #6046 cancellation are related but not proven equivalent S3* closure.
- Our on-top contribution: Optional developer-configured Python MultiAgentPlugin + separate read-only evidence auditor + versioned findings + authorized hold/recheck return, with raw-artifact provenance and controlled fail-closed behavior.
- Incremental benefit: HYPOTHETICAL ability to challenge false completion using independent artifact evidence and change next lawful action; no observed operator demand, economic advantage or native runtime test asserted.
- Decision scope: Proposal-stage GO for the specific future Strands first-party S3*=C constructor only; no maintainer adoption decision, product change, external publication, Index grade change or status for unrelated cases.
