---
name: scientific-probe
description: Specify and interpret one bounded scientific probe after the target, anomaly, alternatives, or replication claim is sufficiently framed. Use for preregistering a discriminating comparison, defining replication success or failure, freezing analysis and stop rules, designing a scoped anomaly probe, or interpreting an Evidence Record; also for 判别实验、复现标准、探针合同、证伪规则. Select DISCOVERY, DISCRIMINATION, or REPLICATION mode. Do not use for broad open-ended sensemaking or research-direction exploration, already-defined implementation, repository simplification, generic literature summaries, or product delivery.
license: MIT
metadata:
  author: hyh31415-maker
  version: "0.2.0"
  suite: lean-scientific-research
  role: epistemic-design
---

# Scientific Probe

## Outcome contract

Reduce the uncertainty that matters for the current scientific decision without collapsing onto the safest familiar explanation or waiting for universal proof.

Sparse, noisy, indirect, or local evidence may justify a scoped working hypothesis and a reversible next probe. It does not justify a stronger claim than its domain, assumptions, and measurement support. Evidence sufficiency is decision-relative: require enough to change the next scientific action, not enough to settle the field.

Freeze only the choices that affect the current inference. Record or defer non-blocking design questions; stop only when an unresolved choice would change this probe, violate a hard constraint, or make its result uninterpretable.

## Boundary and handoff

Use this Skill when a bounded scientific target is ready to become one operational probe: define what would count, freeze inference-relevant choices, preserve them through execution, and interpret the returned evidence.

When `$exploratory-science` is installed, it owns broad frontier sensemaking, hypothesis portfolios, conceptual-model development, and research-direction choice under sparse evidence. It may pass a scoped anomaly, candidate set, or discriminator here when a durable or consequential Probe Contract is useful. Do not invoke both Skills for a quick reversible question. If no broader exploration workflow is available, perform only the minimum candidate expansion needed to make the bounded probe meaningful.

Use `$lean-scientific-computing` when the target computation is defined and the remaining work is data preparation, implementation, simulation, calibration, diagnostics, scientific verification, or repository simplification.

For mixed work, use one sequence:

```text
scientific-probe -> Probe Contract -> lean-scientific-computing
-> Evidence Record -> scientific-probe
```

Handoff only when ownership changes. A trivial calculation may stay here; local coding details may stay with the implementation Skill. If the sibling Skill is unavailable, preserve the boundary locally rather than blocking.

## Choose the inquiry mode

| Mode | Use when | What is fixed |
|---|---|---|
| **DISCOVERY** | A scoped anomaly or search target exists, but the current probe may need bounded adaptation | The current probe mechanics and evidence capture; adaptive branches are logged and remain exploratory |
| **DISCRIMINATION** | Credible alternatives make different predictions | Primary discriminator, analysis rule, decision rule, and stop rule before outcome inspection |
| **REPLICATION** | An existing reported claim is being rerun | Population, exclusions, sample-changing preprocessing, primary statistic, success/failure rule, and stop rule before rerun |

A Probe Contract freezes one probe, not the research program. Changing mode or promoting an exploratory result to confirmatory use requires a new contract.

## Core loop

### 1. Name the scientific target

State the decision, anomaly, unexplained regularity, or search target. In DISCOVERY, progress may be a predictive mechanism, a localized failed assumption, or a better discriminator. Do not substitute a software deliverable for the target.

### 2. Diverge enough to avoid tunnel vision

Start from the framed candidates. Add only the smallest missing alternative needed to avoid one-hypothesis confirmation. Challenge consequential soft assumptions and include a non-default candidate only when it has a coherent mechanism and a distinct consequence.

For each candidate, identify its defining mechanism or assumption, prediction under the planned conditions, evidence that would weaken it, and important assumptions shared with competitors. Group candidates that are observationally equivalent under the current probe.

Do not turn this bounded step into a broad research-direction exercise, force an immature problem into binary hypotheses, or generate decorative novelty.

### 3. Find a real discriminator

Prefer an observation, intervention, statistic, limiting case, counterexample, direction, scale, shape, timing, or budget signature on which credible candidates differ.

Check only what can change interpretability: expected effect versus measurement or numerical resolution; apparatus or positive controls; confounding, leakage, and sample-changing preprocessing; model or observation-operator dependence; and simpler cases that could settle the issue.

If the candidates predict the same observable, redesign the probe rather than scaling a non-discriminating sweep.

### 4. Choose the minimum sufficient probe

Balance expected information gain against implementation, compute, data-acquisition, and interpretive cost. Prefer a hand calculation before a simulation, a synthetic control before real-data scale-up, a box model before a spatial host when the uncertainty is local, and one primary statistic before a dashboard.

Small is not automatically sufficient: increase only the dimension needed for power, resolution, measurement validity, or a decisive control. In DISCOVERY, add at most one orthogonal or adversarial probe when it materially protects against a blind spot.

### 5. Freeze a proportional Probe Contract

Keep the default contract to one screen:

```text
Mode and scientific target:
Current alternatives or search space:
Scope and consequential shared assumptions:
Discriminating prediction or discovery signal:
Probe and controls:
Primary observable and analysis rule:
Decision or branch rule and stop rule:
Required raw evidence and provenance:
Implementation ceiling:
```

Use [references/probe-contract.md](references/probe-contract.md) only for consequential, stochastic, data-dependent, expensive, multi-stage, or post-result-flexible work.

Confirmatory rules must not be revised silently after the outcome. DISCOVERY may branch, but every failed attempt, changed metric, selection rule, and retained result remains visible and exploratory.

### 6. Execute, interpret, and stop

Execute a trivial probe directly or hand non-trivial repository work to `$lean-scientific-computing`. Set only the implementation ceiling needed to prevent premature productization; do not prescribe architecture without a scientific requirement.

Interpret the Evidence Record with explicit labels:

```text
[observed] [derived] [model-dependent] [exploratory] [speculation]
```

For DISCRIMINATION or REPLICATION, report `supports`, `weakens`, `incompatible under assumptions`, `unresolved`, or `invalid probe`. For DISCOVERY, report `candidate generated`, `anomaly localized`, `discriminator improved`, `unresolved`, or `invalid probe`.

If controls fail, the measurement cannot resolve the discriminator, or all current candidates miss the observation, preserve the surprise, mark the probe unresolved or invalid, reopen the smallest relevant assumption set, and create a new exploratory contract. Do not repair the old rule until it looks favorable.

Stop when the current decision is possible, discovery has advanced enough to define the next probe, or the probe is invalid. Name at most one next probe unless the user asks for a research program. Do not continue into unsolicited refactoring, platforms, dashboards, broad sweeps, or literature expansion.

## Evidence discipline

- Never invent data, execution, citations, measurements, or replication.
- Separate supplied or observed facts from assumptions, derivations, model-dependent results, exploratory selection, and speculation.
- A simulated pattern does not prove that the modeled mechanism caused the real observation.
- Keep failed runs, control failures, exclusions, branches, and contract deviations visible.
- Treat safety, privacy, data integrity, mathematical definitions, and explicit user constraints as hard constraints. Treat prevailing interpretations, preferred libraries, existing architecture, and imagined reuse as challengeable assumptions.

Read [references/failure-modes.md](references/failure-modes.md) when safe-answer collapse, premature formalization, post-result analysis, simulation-to-reality claims, leakage, evidence paralysis, or repeated metric changes are live risks. Read files under `evals/` only when revising or evaluating this Skill.

## Completion

Finish when the mode matches the epistemic state, candidates are distinct enough, the probe can change the next scientific action, frozen and adaptive choices are labeled correctly, claims match the evidence, and the work has stopped at the first sufficient result.
