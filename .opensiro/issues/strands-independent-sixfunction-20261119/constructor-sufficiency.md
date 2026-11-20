# Strands Agents — source-native S3* C-construction technical contract

**Canonical storage:** `opensiro-contributions/harness-sdk@opensiro/meta:.opensiro/issues/strands-independent-sixfunction-20261119/constructor-sufficiency.md`.
**Level 1 / Human decision Issue:** [issue.md](issue.md).
**Canonical decision receipt:** [roadmap.md](roadmap.md); it owns historical vector, P0/P1/P2, verdict and source pins.
**Stage:** PLAN_ONLY, HYPOTHETICAL; **DRAFT — NOT PUBLISHED**; implementation and native tests NOT_RUN. The Human has the sole six-function historical/current matrix; no second table here.

## 1. Function-specific construction boundary and methodology checks

**Source and mode boundary:** Current original [strands-agents/harness-sdk@287896945d2190ebf90adc9e67c0456239681843](https://github.com/strands-agents/harness-sdk/commit/287896945d2190ebf90adc9e67c0456239681843), 2026-11-20, Python SDK installed `Swarm` with developer-provided `Agent` nodes and opt-in `MultiAgentPlugin` hooks; TS SDK/harness parity considered separately, not assumed. System in focus is supported runtime and its application controller; docs, team, GitHub checks and disconnected Evals experiments are adjacent. Accepted pinned [Index assessment](https://github.com/opensiro/vsm-harness-index/blob/5dbb51b2ddad0f29a84e10b4b5009c8989159165/assessments/st/strands-agents.md), blob `60b16ac6fdbe828d873706786a79e44053ec7446`, historical review `08ed4cfd3eb42ae9f668595e675d5f196eee7e44`, 2026-09-15, Profile 0.2.1 / Skills 0.3.1, no current regrade.
**Target transition:** S3*=— -> S3*=C
**Six-function dependencies (S1/S2/S3/S3*/S4/S5):** S1 workers make real claims and tool effects; S2 Swarm regulates peer handoff; parent/application S3 receives audit feedback and lawfully decides whether subsequent work may proceed; S3* requires different access to reality, not another worker summary; S4 external/future analysis is unrelated to this post-run audit; parent S5 grants tool/data/hold authority, never delegated implicitly. Use [roadmap.md](roadmap.md) for the accepted vector and exact priority.
**Function witness:** HYPOTHETICAL operator disturbance: a Swarm worker reports artifact completion despite absent/wrong original output. Separate audit actor independently reads original artifact/file/replay evidence, judges veracity, returns versioned `PASS / CHALLENGE / INCONCLUSIVE` to an authorized app controller that can hold the next affected Swarm node and read back its actual status. A hook is transport/enforcement; the independent auditor owns the S3* judgement and parent owns current control/ultimate permission.
**Counterfactual owner test:** Remove autonomous auditor but leave `SwarmResult`, hooks and GoalLoop: normal trace/worker transcript survives, but no separate adversarial raw-artifact-based S3* discretionary judgement. If identical independent result is available through shipped first-party code, proposal is duplicate.
**Possible methodological negative control:** A routine GoalLoop judge, generic OTel trace or co-located Evals tests are not an independent complementary channel. Parent-controlled S5 is lawful. If raw evidence cannot be independent or is unavailable in supported deployment mode, the claimed S3* owner fails. No change to Profile/Skills is justified.
**Contributor / maintainer priorities:** NOT_STATED for this independent research proposal; no inferred demand, roadmap commitment or consent from PR similarity.

## 2. Source-pinned baseline and parallel native Track A / on-top Track B

**Original native workflow:** [Python Swarm](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/swarm.py) runs nodes, records `SwarmState.results`, node history and status; [hooks](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/hooks/events.py) deliver `AfterMultiAgentInvocationEvent` and `BeforeNodeCallEvent`, including `cancel_node`; [versioned snapshot](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/_snapshot.py) restores state. These are real first-party seams, not an existing independent verifier.
**Closest existing solution:** [GoalLoop](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/vended_plugins/goal/plugin.py) judges same process output/transcript and retries; app may inspect logs/files itself or use an explicit human check. This remains the matched no-plugin baseline.
**Relevant original Issues/PRs:** [PR #1656](https://github.com/strands-agents/harness-sdk/pull/1656) OPEN, head `506853a60cf1688bfc06a7a868b8faed49cb356a`, adds opt-in evaluation OTel telemetry rather than audit ownership/return. [PR #6204](https://github.com/strands-agents/harness-sdk/pull/6204) OPEN, head `2a16c48fe7311c70415ffa0c7dc19b6079649414`, tests harness scenarios outside production audited execution. [Issue #5934](https://github.com/strands-agents/harness-sdk/issues/5934) OPEN deterministic *pre-tool* physical-bounds check. [PR #6046](https://github.com/strands-agents/harness-sdk/pull/6046) MERGED optional background cancellation, only current execution enforcement. Original maintainer intent for adding an S3* construct NOT_STATED.

| C-sufficiency link | Track A / source | Track B minimal additional component | Falsifier |
| --- | --- | --- | --- |
| Separate judgement over operational reality | SHIPPED `SwarmResult` and events; GoalLoop uses operational transcript | Read-only developer-supplied original artifact/replay reader with independent autonomous reviewer/criteria | Reviewer sees only worker's own summary, or first-party already supplies separate equivalent access |
| Attributed feedback and lawful later effect | SHIPPED before-node cancellable hook, app control and snapshots | Immutable task/evidence revisions, `PASS / CHALLENGE / INCONCLUSIVE` receipt, controller-held next step and actual result feedback | Notice never affects later authorized work, or stale/unauthorized result changes a task |

**On-top distinctness:** Telemetry/events alone are not an independent auditor; existing GoalLoop is same operational claim path. An opt-in plugin with **raw evidence and authorized return** is source-grounded and function-specific, without necessarily creating a product feature the maintainers want.
**Source ambiguity / rights blockers:** Access to real artifact bytes, post-commit ordering of `AfterMultiAgentInvocationEvent`, snapshot/task revision lifetime and enforcement across nested Swarm modes still require native test. The application must explicitly supply right to read/hold; missing consent prohibits original publication. Unmeasured value is NOT an architectural blocker.

## 3. Minimal complete S3* first-party C construction

**Required property:** Compose a separate autonomous audit decision owner with complementary raw data and feedback into legitimate subsequent control. A hook, queue or in-band critic alone is not S3*.

| Native component / proposed integration | Existing pinned file/API | Smallest additional source-native construction | Decisive right, effect and return |
| --- | --- | --- | --- |
| `Swarm` observation | [swarm.py](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/swarm.py), [events.py](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/hooks/events.py), [plugin base](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/plugins/multiagent_plugin.py) | Optional developer-installed plugin subscribes completed result and stable task identity, performs read-only raw-evidence sampling | Separate audit actor chooses evidence finding, not worker |
| Controller return / safe next task | [BeforeNodeCallEvent.cancel_node](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/hooks/events.py), [snapshot](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/src/strands/multiagent/_snapshot.py) | Versioned audit finding + application-authorized hold/recheck on next affected node and return of actual outcome | Parent controls effect; auditor's evidence changes later lawful decision |

**Architectural C-sufficiency argument:** Compare three options: (a) add an ordinary reviewer node — rejected because it may only repeat worker claims; (b) use GoalLoop with external validator — plausible app workaround, but it is normally in-process task feedback, not separately owned sampled complementary audit with controller return; (c) use opt-in `MultiAgentPlugin` on Swarm and independent artifact reader/auditor with versioned finding consumed by parent controller — strongest first-party source-native complete proposed S3* composition. Parent supplies legitimate evidence/hold authority; no default access or rollback. Stage is future construction, not shipped grade.
**Explicit non-goals:** No new S3 whole-org manager, S4 provider watcher, S5 authority grant, automatic original Issue/PR, mandatory audit plugin, production runtime changes or manufactured benefit.
**Implementation dependency graph:** P1 pin raw evidence provider/revision + correct hooks and parent rights → optional plugin and separate auditor + subsequent-task hold/recheck (P0) → native false/clean/stale test and TS boundary review. P2 NONE.

## 4. Priorities, optional alternative and stopping rules

**P0 and P1:** P0 is the exact S3* optional first-party Swarm audit/effect/return chain in [roadmap.md](roadmap.md); P1 confirms raw evidence, separate reviewer, lawful controller, hook ordering and snapshot safety, then Python-native tests and TS parity as justified.
**P2:** NONE; do not force other VSM components or a universal audit framework.
**Alternative path:** App can use existing GoalLoop/trace plus manual verification; may be preferred for simpler applications. Parent chooses product adoption irrespective of a feasible source-native C path. The original issue/PR facts do not establish a maintainer product need.
**Stop:** Reject this C if independent artifact access or decision is impossible in the supported mode, returned result never reaches lawful next operation, evidence revisions cannot bind, equivalent first-party S3* ownership/feedback already ships, or parent explicitly prohibits the integration. Absence of cost measurement alone is not NO_GO.

## 5. Future source-native acceptance — derive tests, do not copy a matrix

**Native test commands and entry points:** Proposed Python tests should follow [strands-py/docs/TESTING.md](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/strands-py/docs/TESTING.md) and [CONTRIBUTING.md](https://github.com/strands-agents/harness-sdk/blob/287896945d2190ebf90adc9e67c0456239681843/CONTRIBUTING.md) (`cd strands-py && hatch test` for unit suite); no test command or native case was run in this roadmap.
**Positive functional closure:** Two-node Swarm task where first worker falsely reports file completion; separate auditor inspects original file/replay, makes `CHALLENGE`, app lawfully holds/rechecks second node and receives its outcome. Compare with same baseline inputs without plug-in.
**Independent alternative (where applicable):** Good artifact under identical task passes evidence review and allows second node, distinguishing choice from a static "always block" transport.
**Negative authority and compatibility (where applicable):** Missing or revoked reader role, unavailable auditor, stale revision after snapshot, absent controller permission and unexpected hook failure never emit fictional pass or cause unauthorized next-node effect; first-party normal operation remains available if plugin is explicitly disabled.
**Matched native alternative:** Same task under GoalLoop/ordinary traces with app-level human validation. No claim of superiority until source-native matched experiments.

| Future test — all NOT_RUN | Real native setup / proposed entry | Required effect/feedback | Falsifier |
| --- | --- | --- | --- |
| False completion | New plugin unit test via native Strands Python test runner | Independent evidence CHALLENGE; lawful next node hold + observed return | Only worker text used or no controller effect |
| Valid completion | Same Swarm with real artifact | PASS, no false hold, actual next result recorded | False positive or no return |
| Denied/stale evidence | Snapshot/replay, reader revocation and app permission checks | INCONCLUSIVE/explicit denial, no unauthorized effect | Stale finding applied or failure silently passed |

**NOT_RUN** means no native tests or independent verification, not PASS.

## 6. Proposal verdict, falsification, evidence ownership and handoff

**Proposal-stage decision:** GO
**Research disposition:** NEEDS_EVIDENCE
**Primary falsifier:** The proposed auditor cannot access independent raw evidence or cannot return any finding to authorized subsequent Swarm control; or current shipped first-party code already supplies this exact S3* owner and return.
**Validation state:** NOT_RUN
**Ownership of truth:** Profile owns function semantics; Skills owns method; Index owns historical accepted grades; original maintainers own product choices; [roadmap.md](roadmap.md) owns this case's proposal fields and source pins.
**Cost status:** NOT_MEASURED; no empirical saving/benefit claim.
**Next permitted action:** Future local experimental native test only after appropriate code/rights preflight; original Issue/PR/public fork Issue and implementation require explicit separate exact approval, and PAUSE/STOP remains binding. Old 2026-11-19 scoped NO_GO is historical (same case, different methodology threshold and focus), with new independently sealed S3* first-pass [#7045308538](https://github.com/opensiro/upstream/issues/58#issuecomment-7045308538); separate Cedar S3 case unchanged.
**Human backlink:** [issue.md](issue.md); **case receipt:** [roadmap.md](roadmap.md).
**AI disclosure:** Prepared with AI assistance; no first-party implementation, publication, native tests, measurements or human endorsement represented.
